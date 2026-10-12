# NEXORA AI — Sistema de cualificación automática de leads mediante IA

## Descripción del proyecto

NEXORA AI es un proyecto de automatización empresarial que utiliza inteligencia artificial para analizar consultas comerciales recibidas mediante un formulario, identificar posibles oportunidades de negocio y generar respuestas personalizadas.

El objetivo es demostrar cómo combinar automatización, modelos de lenguaje e integraciones para optimizar la primera fase de la atención comercial.

## Problema empresarial

Las empresas reciben consultas de clientes potenciales que requieren revisión, clasificación y respuesta. Gestionar estas solicitudes manualmente puede consumir tiempo, retrasar la atención y dificultar la identificación de oportunidades comerciales.

Este proyecto propone automatizar parte de ese proceso mediante un workflow de n8n.

## Solución desarrollada

El sistema recoge la información de un formulario, la envía a un modelo de inteligencia artificial para analizarla y utiliza el resultado para decidir qué tipo de respuesta enviar.

El workflow contempla dos escenarios:

- **TRUE — Posible oportunidad comercial:** la consulta se identifica como una oportunidad y sigue una rama específica de tratamiento.
- **FALSE — Consulta general o no cualificada:** se prepara una respuesta personalizada para solicitar más información o atender la consulta inicial.

En ambos casos, el sistema prepara y envía un correo electrónico con una plantilla HTML y una identidad visual común bajo la marca NEXORA AI.

## Arquitectura del workflow

El flujo de automatización sigue esta secuencia:

1. **Formulario de entrada:** recoge los datos de la consulta.
2. **Análisis con IA:** un modelo Gemini analiza el mensaje y devuelve una clasificación estructurada.
3. **Procesamiento con JavaScript:** convierte la respuesta del modelo en datos utilizables por los siguientes nodos.
4. **Condición IF:** determina qué rama debe ejecutarse según el resultado de la cualificación.
5. **Preparación del correo:** organiza los datos y el contenido de la respuesta.
6. **Envío mediante Gmail:** envía un email HTML adaptado a cada escenario.

## Tecnologías utilizadas

- **n8n:** diseño y ejecución del workflow de automatización.
- **Google Gemini:** análisis de consultas y generación de respuestas.
- **JavaScript:** procesamiento de la respuesta estructurada del modelo.
- **Gmail:** envío de correos electrónicos.
- **HTML y CSS inline:** presentación visual de los mensajes.

## Objetivos de aprendizaje

Este proyecto permite practicar:

- Diseño de workflows de automatización.
- Integración de modelos de lenguaje en procesos empresariales.
- Uso de respuestas estructuradas en formato JSON.
- Procesamiento de datos con JavaScript.
- Implementación de condiciones y ramificaciones.
- Integración con servicios externos mediante credenciales.
- Generación de comunicaciones personalizadas con HTML.
- Validación de un proceso automatizado de principio a fin.

## Instalación y configuración

El archivo `nexora-ai-cualificacion-leads.json` contiene la exportación del workflow de n8n.

Para utilizarlo en otra instalación:

1. Importa el archivo JSON desde n8n.
2. Configura las credenciales necesarias para Google Gemini y Gmail.
3. Comprueba los parámetros del formulario y las expresiones de los nodos.
4. Revisa el comportamiento de ambas ramas.
5. Realiza pruebas controladas antes de utilizarlo con consultas reales.

Las credenciales no se incluyen en el repositorio y deben configurarse de forma independiente en cada instalación.

La disponibilidad del servicio de IA, las cuotas de uso y los límites de las API pueden afectar a la ejecución del workflow.

## Consideraciones y mejoras futuras

Este proyecto es un prototipo funcional con fines formativos y de portfolio. Antes de utilizarlo en un entorno de producción, sería conveniente incorporar:

- Reintentos y gestión de errores cuando el servicio de IA no esté disponible.
- Validación de la respuesta JSON del modelo.
- Registro de ejecuciones y errores.
- Protección de los datos personales recibidos.
- Pruebas adicionales con distintos tipos de consultas.
- Revisión humana de las oportunidades comerciales antes de tomar decisiones importantes.

## Autoría y propósito

Proyecto desarrollado como parte de mi formación en inteligencia artificial aplicada a empresas, con especial atención a la automatización de procesos, las integraciones y el uso práctico de modelos de lenguaje.

**NEXORA AI** es una marca conceptual utilizada para presentar el proyecto.

## Demostración visual

### Workflow de n8n

![Workflow completo de cualificación automática de leads](screenshots/workflow-completo.png)

### Email HTML de NEXORA AI

![Ejemplo del correo personalizado de NEXORA AI](screenshots/email-nexora-ai.png)
