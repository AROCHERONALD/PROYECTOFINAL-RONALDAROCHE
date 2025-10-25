# PROYECTOFINAL-RONALDAROCHE

link del videO explicativo de nuestro proyecto: https://drive.google.com/file/d/1CY9wojcBRWEB5BUM1eXz6L6QxXWSTxRN/view?usp=sharing

Descripción del proyecto

El objetivo de mi proyecto fue modernizar mi aplicación de Android utilizando n8n como un servidor de inteligencia artificial que maneja la lógica de negocio.1. Integración Principal: App Móvil $\rightarrow$ Agente de IALa aplicación móvil envía las solicitudes al flujo de n8n usando un Webhook, lo cual me permitió:Lenguaje Natural: Enviar la interacción del usuario como texto (prompt), no solo como datos predefinidos.Respuesta Instantánea: El flujo devuelve una confirmación inmediata a la aplicación a través del nodo Responder al Webhook.2. El Corazón del Flujo: El Agente InteligenteEl núcleo es el Agente de IA que utiliza el modelo de OpenAI:NodoFunción ClaveAgente de IACerebro Central. Analiza el texto del usuario y decide qué acción tomar (si el usuario completó un reto, necesita guardar algo, etc.).Registrar_en_sheetHerramienta de Registro. Es llamado por el Agente para guardar automáticamente la Fecha, el Usuario y el Reto extraídos del texto en un Google Sheet.Bucle (Loop)La herramienta (Registrar_en_sheet) está conectada de vuelta al Agente. Esto asegura que el Agente reciba la confirmación de que la tarea fue exitosa antes de enviar la respuesta al usuario.
Instrucciones de instalación
	1.	Clonar o descargar el proyecto:
	•	Descarga el archivo .zip y extráelo en tu computadora.
	2.	Instalar dependencias:
	•	Asegúrate de tener instalado Node.js y npm.
	•	Instala n8n globalmente con:

npm install n8n -g
3.	Configurar variables de entorno:
	•	Crea un archivo .env con las credenciales necesarias:

GOOGLE_SHEETS_CREDENTIALS=<tu_credencial_json>
TELEGRAM_API_KEY=<tu_token_bot>
GMAIL_CLIENT_ID=<tu_id_cliente>
GMAIL_CLIENT_SECRET=<tu_secreto_cliente>

Explicación de la integración con n8n

El flujo mostrado en la imagen automatiza el proceso mediante los siguientes nodos:
	1.	Webhook Reto Personal:
Recibe datos enviados desde una aplicación o formulario externo.
	2.	Google Sheets – Guardar Reto:
Añade la información del reto recibido a una hoja de cálculo.
	3.	Telegram – Notificar Reto:
Envía un mensaje automático al grupo o usuario de Telegram confirmando el nuevo reto.
	4.	Gmail – Confirmación Reto:
Crea un borrador de correo de confirmación con los datos registrados.
	5.	Cron – Enviar Resumen Semanal:
Programa una ejecución semanal para generar un resumen.
	6.	Google Sheets – Leer Retos:
Recupera los datos acumulados de la hoja.
	7.	Gmail – Enviar Resumen Semanal:
Genera y envía el resumen automatizado a los destinatarios.

Requisitos y dependencias
	•	Software necesario:
	•	Node.js v18 o superior
	•	npm v9 o superior
	•	n8n (última versión estable)
	•	Integraciones externas:
	•	Cuenta de Google con acceso a Google Sheets y Gmail API habilitadas
	•	Bot de Telegram creado y token configurado
