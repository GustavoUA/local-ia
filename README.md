TU_IA_LOCAL
Creado por SecTF Lab
Interfaz web para instalar y hablar con un modelo de IA (LLM) que corre en tu propio equipo,
usando Ollama como motor.
Cómo funciona
Un navegador no puede ejecutar PowerShell ni instalar programas por sí solo. Por eso este
proyecto tiene dos partes:
`server.js`: un pequeño servidor Node que corre en tu PC. Es el único que ejecuta
comandos (PowerShell/`ollama`) y habla con la API local de Ollama (`http://localhost:11434`).
`public/`: la web (HTML/CSS/JS) que ves en el navegador. Le pide cosas al servidor
mediante peticiones fetch, nunca ejecuta comandos directamente.
Requisitos
Windows 10/11 con `winget` (viene de serie en Windows moderno).
No hace falta tener Node.js ni Ollama instalados de antemano: el asistente los comprueba
y los instala él solo si faltan.
Para usuarios finales (sin conocimientos técnicos): "Asistente de IA"
Descomprimimos el .Zip que hemos descargado.
accedemos a la ruta Asistente IA
ejecutamos el .exe que se encuentra en el interior "Asistente IA.exe"

El asistente instalará NODE.JS y ollama, una vez instalado aparecerá una ventana web
esta ventana es local no lo ve nadie mas que el usuario que lo usa, el siguiente paso es
"iniciar Servicio de Ollama", posterior a ello se le habilitará una lista de asistente IA
debe elegir el mas adecuado para usted, denle a "descargar" y espere unos minutos
pasado unos 2 o 3 minutos "refresque" la ventana web, aparecerá la IA descargada
Seleccionela y podrá iniciar la conversación.
