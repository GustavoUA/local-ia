# tu_ia_local

*Creado por **SecTF Lab***

Interfaz web para instalar y hablar con un modelo de IA (LLM) que corre en tu propio equipo,
usando [Ollama](https://ollama.com) como motor.

## Cómo funciona

Un navegador no puede ejecutar PowerShell ni instalar programas por sí solo. Por eso este
proyecto tiene dos partes:

- **`server.js`**: un pequeño servidor Node que corre en tu PC. Es el único que ejecuta
  comandos (PowerShell/`ollama`) y habla con la API local de Ollama (`http://localhost:11434`).
- **`public/`**: la web (HTML/CSS/JS) que ves en el navegador. Le pide cosas al servidor
  mediante peticiones fetch, nunca ejecuta comandos directamente.

## Requisitos

- Windows 10/11 con `winget` (viene de serie en Windows moderno).
- No hace falta tener Node.js ni Ollama instalados de antemano: el asistente los comprueba
  y los instala él solo si faltan.

## Para usuarios finales (sin conocimientos técnicos): "Asistente de IA"

Este es el modo pensado para desplegar en una empresa a usuarios que no deben ver nunca
una ventana de cmd/PowerShell.

Doble clic en **`Asistente de IA.vbs`**. Se abre una ventanita sencilla que:

1. Comprueba si Node.js está instalado. Si falta, muestra el motivo y un botón
   **"Instalar"**; al pulsarlo lo instala en segundo plano (no hace falta hacer nada más).
2. Comprueba si la IA local (Ollama) está instalada. Igual: si falta, un botón
   **"Instalar"** lo resuelve solo.
3. Si ya está todo listo, abre el navegador directamente en la pantalla de **elegir IA**,
   sin menús ni pasos de por medio — el usuario solo tiene que pulsar el modelo que quiera
   usar y empezar a escribir.

La primera vez que se instala algo, Windows pedirá confirmación una vez con su cuadro de
diálogo nativo de seguridad ("¿Permitir que esta app haga cambios?") — no es una ventana de
consola, es el permiso estándar de Windows para instalar programas, y es inevitable sin
desplegar Node/Ollama por GPO o Intune de antemano. Si tu empresa quiere cero interrupciones
para el usuario, lo ideal es que TI pre-instale Node.js y Ollama en los equipos por esa vía;
el asistente entonces pasará directo al paso 3.

Para que quede como una app de verdad (icono propio, sin extensión `.vbs` visible), puedes
convertirlo en un acceso directo: clic derecho sobre `Asistente de IA.vbs` → *Crear acceso
directo* → clic derecho sobre el acceso directo → *Propiedades* → *Cambiar icono*. Ese
acceso directo es lo que se distribuye a los equipos (por ejemplo, copiándolo al escritorio
o al menú de inicio de todos los usuarios).

### Convertirlo en un .exe de verdad (opcional)

Si tu política de empresa bloquea los `.vbs`, puedes compilar `lanzador.ps1` a un `.exe` real
con el módulo gratuito [ps2exe](https://github.com/MScholtes/PS2EXE), una sola vez, desde un
equipo de desarrollo:

```powershell
Install-Module ps2exe -Scope CurrentUser
Invoke-ps2exe .\lanzador.ps1 .\AsistenteIA.exe -noConsole -icon .\icono.ico -title "Asistente de IA"
```

El `.exe` resultante se comporta igual que el `.vbs`: ninguna consola visible, solo la
ventanita del asistente. Cópialo junto a `server.js` y la carpeta `public/` para distribuirlo.

## Para uso técnico / desarrollo

Si tú mismo sabes manejar PowerShell y solo quieres arrancar el servidor a mano:

Doble clic en **`iniciar.bat`** (o, desde PowerShell, `./iniciar.ps1`). Comprueba Node,
instala dependencias con `npm install` si hace falta, y arranca el servidor mostrando el
registro en una ventana de consola normal.

## Uso

1. Pulsa **"Abrir panel de control"**.
2. **Opción 1 — Instalar IA localmente**: comprueba si Ollama está instalado y activo, y si no,
   lo instala (en Windows, lanza `winget install Ollama.Ollama` vía PowerShell y muestra el
   progreso en pantalla).
3. **Opción 2 — Iniciar conversación**: lista los modelos ya descargados en tu equipo (vía
   `ollama list`/API) para elegir uno, y además te ofrece una lista de modelos recomendados
   (Qwen 2.5, DeepSeek-R1, Llama 3.2, Gemma 2, en varios tamaños) para descargar con un clic si
   aún no tienes ninguno.
4. Al elegir un modelo se abre el chat, que habla en streaming con `ollama` a través del
   servidor local.

## Notas

- Si Ollama no está corriendo, en Windows suele bastar con abrir la aplicación Ollama una vez
  (se queda en segundo plano). Si prefieres la consola: `ollama serve`.
- Puedes editar la lista de modelos sugeridos en `server.js` (constante `MODELOS_SUGERIDOS`)
  para añadir o quitar cualquier modelo de la librería de Ollama.
- Todo el tráfico de chat se queda en tu máquina: la web solo habla con `localhost`.
