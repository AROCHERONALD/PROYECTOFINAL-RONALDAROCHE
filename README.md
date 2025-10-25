# PROYECTOFINAL-RONALDAROCHE
link del viode explicativo de nuestro proyecto: https://drive.google.com/file/d/1CY9wojcBRWEB5BUM1eXz6L6QxXWSTxRN/view?usp=sharing

Descripción del proyecto

Este proyecto automatiza el registro, notificación y resumen de retos personales utilizando la herramienta n8n para integrar servicios externos como Google Sheets, Telegram y Gmail. El flujo permite que, al recibir un reto a través de un Webhook, la información se almacene automáticamente en una hoja de cálculo, se envíe una notificación inmediata por Telegram y se genere un correo de confirmación. Además, semanalmente se genera y envía un resumen automatizado con todos los retos registrados.

Instrucciones de instalación 1. Clonar o descargar el proyecto: • Descarga el archivo .zip y extráelo en tu computadora. 2. Instalar dependencias: • Asegúrate de tener instalado Node.js y npm. • Instala n8n globalmente con:

npm install n8n -g 3. Configurar variables de entorno: • Crea un archivo .env con las credenciales necesarias:

GOOGLE_SHEETS_CREDENTIALS=<tu_credencial_json> TELEGRAM_API_KEY=<tu_token_bot> GMAIL_CLIENT_ID=<tu_id_cliente> GMAIL_CLIENT_SECRET=<tu_secreto_cliente>

Explicación de la integración con n8n

El flujo mostrado en la imagen automatiza el proceso mediante los siguientes nodos: 1. Webhook Reto Personal: Recibe datos enviados desde una aplicación o formulario externo. 2. Google Sheets – Guardar Reto: Añade la información del reto recibido a una hoja de cálculo. 3. Telegram – Notificar Reto: Envía un mensaje automático al grupo o usuario de Telegram confirmando el nuevo reto. 4. Gmail – Confirmación Reto: Crea un borrador de correo de confirmación con los datos registrados. 5. Cron – Enviar Resumen Semanal: Programa una ejecución semanal para generar un resumen. 6. Google Sheets – Leer Retos: Recupera los datos acumulados de la hoja. 7. Gmail – Enviar Resumen Semanal: Genera y envía el resumen automatizado a los destinatarios.
