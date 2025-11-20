# Master-Slave-System-Comunication-Protocols-Integration
Sistema Maestro–Esclavo con Comunicación UART/Bluetooth y SPI, Sensado Analógico y Control de Motor DC

🧩 Descripción General

Este proyecto implementa un sistema embebido distribuido basado en dos microcontroladores AVR, configurados bajo una arquitectura Maestro–Esclavo.

El flujo general del sistema:

Un usuario envía comandos desde un celular vía Bluetooth usando una app de terminal UART.

El microcontrolador Maestro recibe esos comandos por UART, los interpreta y los muestra en un LCD 16×2.

El Maestro reenvía los comandos hacia el microcontrolador Esclavo mediante SPI.

El Esclavo ejecuta las tareas principales:

Lee dos fotoresistencias mediante ADC.

Controla un motor DC mediante PWM y un puente H.

Mide las RPM del motor utilizando un sensor infrarrojo tipo herradura.

El Esclavo devuelve información al Maestro vía SPI.

El Maestro muestra los datos en el LCD y los envía al celular vía Bluetooth.

El usuario observa la retroalimentación completa del sistema tanto en el LCD como en su dispositivo móvil.

🎯 Objetivos del Proyecto
Objetivo General

Desarrollar un sistema embebido distribuido donde dos microcontroladores colaboren para controlar un motor DC, sensar variables analógicas y entregar retroalimentación al usuario mediante Bluetooth y un display LCD.

Objetivos Específicos

Implementar comunicación UART con módulo Bluetooth.

Implementar comunicación SPI Maestro–Esclavo.

Leer sensores analógicos usando ADC.

Controlar un motor DC por PWM.

Medir RPM mediante interrupciones o captura de eventos.

Definir un protocolo de comandos.

Mostrar información en LCD y enviarla al móvil.

📦 Requerimientos Técnicos Mínimos
1. Comunicación con el Usuario (Bluetooth–UART)

Recibir comandos desde app móvil.

Enviar retroalimentación estructurada y clara.

2. Microcontrolador Maestro

Mostrar información relevante en un LCD 16×2.

Reenviar comandos al Esclavo mediante SPI.

Manejo simple de errores de comunicación.

3. Microcontrolador Esclavo

Leer dos sensores LDR mediante ADC.

Generar PWM para controlar motor DC.

Medir RPM mediante sensor infrarrojo tipo herradura.

Responder comandos enviados por el Maestro.

4. Protocolo de Comandos

Debe incluir al menos 5 comandos funcionales, por ejemplo:

Solicitar luminocidad.

Solicitar RPM actual.

Controlar velocidad del motor.

Encender/apagar.

Solicitar estado general.

5. Retroalimentación

Información visible en:

LCD 16×2

Aplicación móvil vía Bluetooth

6. Entregables

Código del Maestro y Esclavo.

Esquemático electrónico.

Manual de usuario.

Reporte técnico.

Video demostrativo.

⚠️ Restricciones Técnicas

Usar SPI real, no simulado.

Usar timers del microcontrolador para PWM.

Lectura de RPM basada en interrupciones (ICPn o INTn).

ADC configurado correctamente (prescaler, Vref, canal).

LCD manejado con librería propia (no Arduino).

Sin uso de Arduino IDE.
Se debe programar en C con AVR-GCC.

📝 Rúbrica de Evaluación (100 puntos)
Categoría	Descripción	Puntos
UART–Bluetooth	Recepción y envío correctos, comandos definidos, manejo de errores.	15 pts
LCD 16×2 (Maestro)	Mensajes claros y actualización dinámica.	10 pts
SPI Maestro–Esclavo	Protocolo funcional y sincronización correcta.	15 pts
ADC – Fotoresistencias	Lectura estable y conversión adecuada.	10 pts
PWM – Motor DC	Control correcto de ciclo de trabajo.	10 pts
RPM por Encoder	Conteo mediante interrupciones y cálculo estable.	15 pts
Protocolo de Comandos	Mínimo 5 comandos funcionales bien documentados.	10 pts
Integración General	Flujo estable entre Maestro–Esclavo–Usuario.	10 pts
Reporte Técnico y Evidencias	Calidad del reporte, esquemas y video.	5 pts
Total		100 pts
📤 Entrega Final

La carpeta final debe incluir:

/code/maestro/ – Código fuente del microcontrolador Maestro

/code/esclavo/ – Código fuente del Esclavo

/docs/esquematico.pdf – Diagrama del sistema

/docs/manual_usuario.pdf – Manual rápido

/docs/reporte_tecnico.pdf – Reporte técnico

/video/demo.mp4 – Video de funcionamiento
