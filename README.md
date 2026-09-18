# Local AI — SecTF Labs

**Local AI** es un asistente de inteligencia artificial diseñado para ejecutarse localmente en Windows utilizando **Ollama** como motor de modelos LLM.

El objetivo del proyecto es simplificar al máximo el uso de inteligencia artificial local: instalar la aplicación, seleccionar un modelo y comenzar a utilizarla desde una interfaz web sencilla.

Desarrollado por **SecTF Labs**.

---

## Instalación

Ya no es necesario descargar el código fuente, descomprimir archivos ni ejecutar manualmente diferentes scripts.

### 1. Descargar Local AI

Accede a la sección **Releases** del repositorio:

https://github.com/GustavoUA/local-ia

Descarga:

`Local-AI-Setup-1.0.0.exe`

### 2. Ejecutar el instalador

Haz doble clic sobre:

`Local-AI-Setup-1.0.0.exe`

El asistente instalará Local AI y creará automáticamente los accesos directos necesarios.

### 3. Ejecutar Local AI

Una vez terminada la instalación, ejecuta:

**Local AI**

desde el escritorio o desde el menú Inicio de Windows.

---

## ¿Qué diferencia hay entre Ollama y Local AI?

Ollama proporciona el motor necesario para ejecutar modelos de inteligencia artificial localmente.

**Local AI utiliza Ollama como motor, pero añade una capa orientada a simplificar su utilización.**

En lugar de trabajar directamente con comandos y configuraciones, Local AI proporciona una interfaz desde la que gestionar y utilizar los modelos.

```text
Usuario
   │
   ▼
Local AI
   │
   ├── Interfaz Web
   │
   ├── Backend Node.js
   │
   └── Gestión del asistente
          │
          ▼
       Ollama
          │
          ▼
       Modelo LLM
```

---

## ✨ Características

- 🧠 Inteligencia artificial ejecutada localmente.
- 🔒 Las conversaciones se procesan en el propio equipo.
- 🌐 Interfaz web sencilla.
- 🤖 Compatible con modelos disponibles mediante Ollama.
- 📦 Instalador para Windows.
- 🖥️ Acceso directo desde Windows.
- ⚙️ Backend desarrollado con Node.js y Express.
- 🚀 Proyecto orientado a simplificar el uso de IA local.

---

## 🔐 Privacidad

Una de las principales ventajas de Local AI es que el modelo puede ejecutarse en el propio ordenador.

Las consultas realizadas al modelo no necesitan enviarse a servicios de inteligencia artificial externos para generar una respuesta.

Esto permite disponer de un entorno de IA local especialmente interesante para:

- Desarrollo.
- Laboratorios.
- Formación.
- Experimentación con LLM.
- Entornos donde la privacidad de la información sea importante.

> La privacidad final también dependerá de las configuraciones, modelos y servicios adicionales que el usuario decida utilizar.

---

## 🖥️ Requisitos

Actualmente Local AI está diseñado para:

- Windows 10/11 de 64 bits.
- Ollama.
- Hardware suficiente para ejecutar el modelo seleccionado.

Los requisitos de RAM, almacenamiento, CPU y GPU dependerán principalmente del modelo que se quiera ejecutar.

---

## 📦 Instalador

A partir de la versión **1.0.0**, Local AI puede distribuirse mediante un instalador para Windows:

`Local-AI-Setup-1.0.0.exe`

El instalador se encarga de desplegar los componentes de Local AI y crear los accesos directos correspondientes.

Esto permite pasar de una instalación basada en archivos y scripts a una experiencia mucho más cercana a una aplicación convencional de Windows:

```text
Descargar
    ↓
Local-AI-Setup.exe
    ↓
Instalar
    ↓
Local AI
    ↓
IA ejecutándose localmente
```

---

## 🛠️ Tecnologías utilizadas

- Ollama
- Node.js
- Express
- JavaScript
- HTML5
- CSS3
- PowerShell
- Inno Setup
- Windows

---

## 📁 Código fuente

El código fuente está disponible en este repositorio para poder estudiar, modificar y mejorar el proyecto.

Los archivos principales incluyen el backend de Local AI, la interfaz web, los scripts de lanzamiento y la configuración necesaria para generar el instalador de Windows.

---

## 🗺️ Roadmap

El proyecto continuará evolucionando con el objetivo de reducir todavía más la configuración necesaria para utilizar IA local.

Entre las mejoras previstas:

- Detección automática de Ollama.
- Instalación asistida de dependencias.
- Inicio automático del servicio necesario.
- Detección de modelos instalados.
- Instalación de modelos desde la interfaz.
- Recomendación de modelos según el hardware.
- Mejor gestión del estado de descarga de modelos.
- Actualizaciones de Local AI.
- Simplificación progresiva del proceso de instalación.

El objetivo final es sencillo:

> **Descargar → Instalar → Ejecutar → Utilizar IA local.**

---

## 👨‍💻 Proyecto

**Local AI**

Desarrollado por **SecTF Labs**

GitHub:  
https://github.com/GustavoUA/local-ia

---

## ⚠️ Estado del proyecto

Local AI es un proyecto en desarrollo.

La aplicación puede cambiar significativamente entre versiones y algunas funcionalidades pueden requerir configuración adicional dependiendo del sistema, la versión de Ollama y el modelo utilizado.

Se recomienda consultar las notas de cada versión antes de actualizar.

---

## ⭐ Colaboración

Si el proyecto te resulta útil, puedes apoyarlo dejando una ⭐ en GitHub.

También son bienvenidos los reportes de errores, propuestas de mejora y contribuciones al proyecto.

**SecTF Labs — Simplificando la tecnología sin renunciar al control local.**

pasado unos 2 o 3 minutos "refresque" la ventana web, aparecerá la IA descargada

Seleccionela y podrá iniciar la conversación.

