🚀 Proyecto de Automatización con n8n y Google Sheets

Este repositorio contiene la evidencia correspondiente a las Partes A y B del proyecto de automatización utilizando n8n y Google Sheets.

📂 Estructura del Repositorio
├── workflow.json      # Archivo exportado desde n8n (Parte A)
└── README.md          # Documentación del proyecto

🧩 Parte A: Workflow de n8n
📘 Descripción General

Este flujo fue diseñado para automatizar un proceso mediante n8n, utilizando nodos que permiten integrar distintas herramientas y ejecutar tareas de forma automática.

⚙️ Funcionamiento del Workflow

Inicio del Flujo: Se activa mediante un nodo Webhook

Procesamiento: Los nodos ejecutan las acciones configuradas  atravez de la informacion captada por el el webhook como el client id y el mensaje se extrae del data sheet la info del cliente 
se pasa por el LLM(OpenAI) para que revise el mensaje y lo coloque en la etapa adecuada y actualize el sheet en campo nota

Salida: El flujo finaliza actualizando el sheet donde est la informacion del cliente.

📁 Puedes revisar la configuración completa importando el archivo workflow.json en tu instancia de n8n.

📊 Parte B: Solución en Google Sheets

El proyecto también incluye una hoja de cálculo en Google Sheets que complementa el flujo de automatización.

📎 Enlace a la hoja de Google Sheets: https://docs.google.com/spreadsheets/d/18an-T5SRVuGo3nUEyzhoDolcu7-ajj98obpC0tVTGCc/edit?usp=sharing
👉 Abrir solución en Google Sheets

🧠 Tecnologías Utilizadas

n8n
 – Plataforma de automatización de flujos de trabajo.

Google Sheets
 – Herramienta para procesamiento y análisis de datos en la nube.

GitHub
 / GitLab
 – Control de versiones y publicación del proyecto.

🧑‍💻 Autor

Ivan Salazar
Desarrollador Full Stack | Especialista en Integraciones y Automatización
📧ivanandres26@hotmail.es
