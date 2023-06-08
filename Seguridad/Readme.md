# AWS WAF, Amazon GuardDuty y AWS Security Hub

## AWS WAF (Web Application Firewall)

AWS WAF es un firewall de aplicaciones web que proporciona protección para aplicaciones web hospedadas en la nube. Algunas características clave de AWS WAF incluyen:

- Protección contra ataques comunes: AWS WAF protege tus aplicaciones web contra ataques comunes como inyección de SQL, cross-site scripting (XSS) y ataques de denegación de servicio (DDoS).

- Control de tráfico de entrada: Puedes utilizar AWS WAF para controlar el tráfico de entrada a tus aplicaciones web. Esto te permite filtrar solicitudes maliciosas o no deseadas en función de reglas y condiciones definidas.

- Reglas personalizables: AWS WAF te permite crear reglas personalizadas para proteger tus aplicaciones web. También puedes utilizar reglas predefinidas proporcionadas por AWS y la comunidad.

## Amazon GuardDuty

Amazon GuardDuty es un servicio de detección de amenazas y análisis de seguridad que utiliza el aprendizaje automático y la inteligencia artificial para identificar actividades maliciosas o no autorizadas en tu cuenta de AWS. Algunas características clave de Amazon GuardDuty incluyen:

- Detección de comportamientos sospechosos: GuardDuty analiza continuamente los eventos y registros en busca de comportamientos sospechosos, como intentos de intrusión, actividad de malware y comunicaciones no autorizadas.

- Alertas en tiempo real: GuardDuty proporciona alertas en tiempo real sobre posibles amenazas. Estas alertas te ayudan a identificar y responder rápidamente a los incidentes de seguridad.

- Integración con otros servicios de AWS: GuardDuty se integra con otros servicios de AWS, como CloudTrail y VPC Flow Logs, para obtener información adicional sobre las actividades sospechosas.

## AWS Security Hub

AWS Security Hub es un servicio de seguridad centralizado que te proporciona una vista consolidada de tus alertas y recomendaciones de seguridad de múltiples servicios de AWS. Algunas características clave de AWS Security Hub incluyen:

- Visibilidad centralizada: Security Hub te brinda una vista centralizada de tus alertas y recomendaciones de seguridad de servicios como GuardDuty, Inspector, Macie y otros.

- Agregación y priorización: Security Hub recopila y prioriza las alertas de seguridad de varios servicios de AWS, lo que te ayuda a identificar y priorizar las acciones necesarias para mejorar la seguridad de tu entorno.

- Integración con herramientas y servicios de terceros: Security Hub se integra con herramientas y servicios de terceros, lo que te permite agregar datos de seguridad adicionales y obtener una visión más completa de tu postura de seguridad.

## Waf de aplicaciones
## Configuración y provisión del Firewall de Aplicaciones Web (WAF) de AWS

La siguiente plantilla de AWS CloudFormation proporciona una configuración básica para la provisión de AWS WAF con reglas para una prueba de concepto. Esta plantilla incluye varios parámetros que se pueden personalizar al crear un stack a partir de ella.

### Parámetros configurables:

- **WAFName**: El nombre base que se utilizará para los nombres de recursos y exportaciones relacionados con este stack de WAF.
- **WAFCloudWatchPrefix**: El prefijo de CloudWatch que se utilizará para cada regla.
- **WAFManualBlacklistIPRule1Name**: El nombre del recurso para la primera regla de lista negra manual de IP.
- **WAFManualBlacklistIPSet1Name**: El nombre del recurso para el primer conjunto de lista negra manual de IP.
- **WAFUserAgentBlacklistRule1Name**: El nombre del recurso para la primera regla de lista negra de agente de usuario.
- **WAFUserAgentByteSet1Tuple1String**: Una lista separada por comas de cadenas que se incluirán en la regla de lista negra de agente de usuario.
- **WAFUserAgentBlacklistSet1Name**: El nombre del recurso para el conjunto de lista negra de agente de usuario.

### Recursos utilizados en la configuración del WAF:

- **WAFManualBlacklistIPSet1**: Define un conjunto de direcciones IP para la lista negra del WAF.
- **WAFUserAgentBlacklistSet1**: Define un conjunto de bytes coincidentes para la lista negra de agentes de usuario del WAF.
- **WAFManualBlacklistIPRule1**: Define una regla del WAF para la lista negra de direcciones IP.
- **WAFUserAgentBlacklistRule1**: Define una regla del WAF para la lista negra de agentes de usuario.
- **WAFWhitelistIPSet1**: Define un conjunto de direcciones IP para la lista blanca del WAF.
- **WAFWhitelistIPRule1**: Define una regla del WAF para la lista blanca de direcciones IP.
- **WAFSqlInjectionDetectionSet1**: Define un conjunto de detección de inyección SQL para el WAF.
- **WAFSqlInjectionExceptionByteSet1**: Define un conjunto de bytes coincidentes para excepciones de inyección SQL en el WAF.
- **WAFSqlInjectionRule1**: Define una regla del WAF para la detección de inyección SQL.


Además, puedes utilizar [reglas predefinidas proporcionadas por AWS y la comunidad](https://docs.aws.amazon.com/waf/latest/developerguide/waf-rule-statement-type.html) para complementar la configuración del WAF.

## Tabla resumen

| Servicio         | Puntos de conexión                                                                                                                   | Independencia           |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------|-------------------------|
| AWS WAF          | - Puede enviar registros de auditoría a AWS CloudWatch Logs para su análisis<br>- Puede utilizar AWS WAF como origen de eventos para reglas personalizadas en AWS EventBridge (anteriormente Amazon CloudWatch Events) | Parcialmente independiente |
| Amazon GuardDuty | - Puede enviar hallazgos de Amazon GuardDuty a AWS Security Hub para su centralización y análisis<br>- Puede utilizar Amazon GuardDuty como origen de eventos para reglas personalizadas en AWS EventBridge (anteriormente Amazon CloudWatch Events) | Parcialmente independiente |
| AWS Security Hub | - Puede recibir hallazgos de AWS WAF y Amazon GuardDuty para su visualización y correlación<br>- Puede utilizar AWS Security Hub como origen de eventos para reglas personalizadas en AWS EventBridge (anteriormente Amazon CloudWatch Events) | Parcialmente independiente |
