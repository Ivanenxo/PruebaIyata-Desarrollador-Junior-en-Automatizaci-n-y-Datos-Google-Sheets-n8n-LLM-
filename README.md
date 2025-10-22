🚀 Proyecto de Automatización con n8n y Google Sheets

Este repositorio contiene la evidencia correspondiente a las Partes A y B del proyecto de automatización, utilizando n8n para la orquestación de procesos y Google Sheets como fuente y destino de datos.

📂 Estructura del Repositorio
├── workflow.json      # Archivo exportado desde n8n (Parte A)
└── README.md          # Documentación del proyecto

🧩 Parte A: Workflow de n8n
📘 Descripción General

Este flujo fue diseñado para automatizar la gestión de clientes y reservas mediante n8n, integrando Google Sheets y OpenAI.
El proceso permite recibir mensajes de clientes, analizarlos con un modelo de lenguaje y actualizar automáticamente su estado o etapa en la hoja de cálculo puedes reservar, cancelar y mostrar interes.

⚙️ Funcionamiento del Workflow

Inicio del flujo:
El flujo se activa mediante un nodo Webhook, el cual recibe solicitudes POST desde una API externa o formulario.

Procesamiento:

A través del Webhook, se recibe información como el ClientID y el mensaje del cliente.

Se consulta en el Google Sheet la información del cliente correspondiente al ClientID.

El mensaje se envía a un modelo LLM de OpenAI, que analiza el contenido y clasifica al cliente en una de las siguientes etapas:
Nuevo, Atendiendo, Interesado, Reservado o Cancelado.

Finalmente, el flujo actualiza automáticamente el campo “Nota” o “Etapa” del cliente dentro del Google Sheet.

Salida:
El flujo concluye actualizando el registro correspondiente en la hoja de cálculo, reflejando la nueva etapa o nota del cliente.

📁 Puedes revisar la configuración completa importando el archivo workflow.json en tu instancia de n8n.

⚙️ Configuración del Workflow

Credenciales necesarias:

Google API:
Guía de configuración 👉 [Configurar credenciales OAuth para Google Sheets](https://docs.n8n.io/integrations/builtin/credentials/google/oauth-single-service/?utm_source=n8n_app&utm_medium=credential_settings&utm_campaign=create_new_credentials_modal#video)

OpenAI API:
Guía de configuración 👉 [Configurar nodo OpenAI en n8n](https://docs.n8n.io/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.lmchatopenai/?utm_source=n8n_app&utm_medium=node_settings_modal-credential_link&utm_campaign=%40n8n%2Fn8n-nodes-langchain.lmChatOpenAi)

Hoja de Google Sheets utilizada:
Una vez configuradas las credenciales, crea o importa la siguiente hoja de datos:
📄 [Plantilla de Google Sheets](https://docs.google.com/spreadsheets/d/12AQuAQ5rz1XstTzo7hWGqayQvCjHmxvAef16RnpOrYI/edit?usp=sharing)

Prueba del flujo:
Con el Webhook activado, envía una solicitud POST al endpoint generado con el siguiente cuerpo JSON:

{
  "ClientID": "1",
  "Message": "Hola, estoy interesado en reservar un espacio hoy"
}


Si todo está correctamente configurado, el flujo actualizará automáticamente la fila del cliente con el ClientID correspondiente en la hoja seleccionada, mostrando la nueva etapa o nota.

📊 Parte B: Solución en Google Sheets

El proyecto incluye una hoja de cálculo en Google Sheets que almacena la información de los clientes y sus etapas.
Esta hoja sirve como base de datos dinámica, actualizada por el flujo de n8n.

📎 Enlace a la hoja de Google Sheets:
👉 [Abrir solución en Google Sheets](https://docs.google.com/spreadsheets/d/18an-T5SRVuGo3nUEyzhoDolcu7-ajj98obpC0tVTGCc/edit?usp=sharing)

🧠 Tecnologías Utilizadas

n8n
: Plataforma de automatización de flujos de trabajo sin código.

Google Sheets
: Herramienta en la nube para gestión y análisis de datos.

OpenAI API
: Inteligencia artificial para análisis semántico y clasificación automática.

GitHub / GitLab: Control de versiones y publicación del proyecto.

👨‍💻 Autor

Ivan Salazar
Desarrollador Full Stack | Especialista en Integraciones y Automatización
📧 ivanandres26@hotmail.es
