# PROYECTOFINAL-RONALDAROCHE

link del videO explicativo de nuestro proyecto: https://drive.google.com/file/d/1CY9wojcBRWEB5BUM1eXz6L6QxXWSTxRN/view?usp=sharing

Descripción del proyecto

El objetivo de mi proyecto fue modernizar mi aplicación de Android utilizando n8n como un servidor de inteligencia artificial que maneja la lógica de negocio.1. Integración Principal: App Móvil $\rightarrow$ Agente de IALa aplicación móvil envía las solicitudes al flujo de n8n usando un Webhook, lo cual me permitió:Lenguaje Natural: Enviar la interacción del usuario como texto (prompt), no solo como datos predefinidos.Respuesta Instantánea: El flujo devuelve una confirmación inmediata a la aplicación a través del nodo Responder al Webhook.2. El Corazón del Flujo: El Agente InteligenteEl núcleo es el Agente de IA que utiliza el modelo de OpenAI:NodoFunción ClaveAgente de IACerebro Central. Analiza el texto del usuario y decide qué acción tomar (si el usuario completó un reto, necesita guardar algo, etc.).Registrar_en_sheetHerramienta de Registro. Es llamado por el Agente para guardar automáticamente la Fecha, el Usuario y el Reto extraídos del texto en un Google Sheet.Bucle (Loop)La herramienta (Registrar_en_sheet) está conectada de vuelta al Agente. Esto asegura que el Agente reciba la confirmación de que la tarea fue exitosa antes de enviar la respuesta al usuario.
