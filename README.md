# MRW LiveKit - Asistente de Voz para Consultas de Envíos

Este repositorio contiene una aplicación de asistente de voz desarrollada con LiveKit que permite a los clientes de MRW consultar el estado de sus envíos a través de una interfaz de voz.

## Estructura del Proyecto

El proyecto está dividido en dos partes principales:

### 1. Backend (carpeta `/app`)

Contiene el agente de voz implementado en Python utilizando LiveKit Agents. El asistente puede:

- Recibir llamadas a través de integración con Twilio SIP
- Conversar con el usuario utilizando procesamiento de lenguaje natural
- Consultar la API de MRW para proporcionar información sobre el estado de los envíos
- Registrar las conversaciones en archivos de log

Tecnologías principales:
- Python
- LiveKit Agents
- OpenAI GPT-4o para el procesamiento de lenguaje
- Cartesia TTS para la síntesis de voz
- Twilio para la integración telefónica

### 2. Frontend (carpeta `/frontend`)

Interfaz web para interactuar con el asistente de voz a través del navegador. Incluye:

- Un botón para iniciar la conversación
- Visualizador de audio para mostrar cuando el asistente o el usuario están hablando
- Controles para pausar/reanudar la conversación o desconectarse

Tecnologías principales:
- Next.js
- React
- Tailwind CSS
- LiveKit SDK para la comunicación en tiempo real

## Configuración y Uso

### Requisitos Previos

- Node.js v18+
- Python 3.10+
- Una cuenta de LiveKit Cloud
- Credenciales de API para OpenAI, Cartesia y MRW

### Configuración del Backend

1. Navega a la carpeta `/app`
2. Crea un entorno virtual de Python: `python -m venv venv`
3. Activa el entorno virtual:
   - Windows: `venv\Scripts\activate`
   - Linux/Mac: `source venv/bin/activate`
4. Instala las dependencias: `pip install -r requirements.txt`
5. Configura las variables de entorno copiando el archivo `.env.example` a `.env.local` y completa con tus credenciales
6. Inicia el agente: `python agent.py dev`

### Configuración del Frontend

1. Navega a la carpeta `/frontend`
2. Instala las dependencias: `npm install` o `pnpm install`
3. Configura las variables de entorno copiando `.env.example` a `.env.local`
4. Inicia el servidor de desarrollo: `npm run dev` o `pnpm dev`
5. Accede a la aplicación en `http://localhost:3000`

## Funcionalidades Principales

- **Consulta de Envíos**: Los usuarios pueden consultar el estado de sus envíos proporcionando su número de teléfono o número de envío.
- **Interacción por Voz**: Interfaz completamente conversacional que permite una experiencia natural.
- **Integración Telefónica**: Posibilidad de recibir consultas a través de llamadas telefónicas gracias a la integración con Twilio.
- **Experiencia Web**: Alternativa de acceso a través de navegador para usuarios que prefieran esta modalidad.

## Licencia

Este proyecto está bajo la Licencia MIT. Consulta los archivos LICENSE en las carpetas `/app` y `/frontend` para más detalles.