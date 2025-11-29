# Master-Slave-System-Comunication-Protocols-Integration
Sistema Maestro–Esclavo con Comunicación UART/Bluetooth y SPI, Sensado Analógico I2C* (TWI) y Control de Motor DC.

Nota: I2C* (TWI) no aplicacrá para versiones de entregas UP-MIC2-2025

<img width="1218" height="564" alt="image" src="https://github.com/user-attachments/assets/12aaf53e-92c5-4592-a084-64e2274145ae" />

_____________________________________________________________________________________
## 🧩 Descripción General

Este proyecto implementa un sistema embebido distribuido basado en dos **microcontroladores STM32F401RE**, configurados bajo una arquitectura **Maestro–Esclavo**.

El flujo general del sistema:

* **1.-** Un usuario envía comandos desde un celular vía Bluetooth usando una app de terminal UART.  
* **2.-** El microcontrolador Maestro recibe esos comandos por UART, los interpreta y los muestra en un LCD 16×2.  
* **3.-** El Maestro reenvía los comandos hacia el microcontrolador Esclavo mediante SPI.  
* **4.-** El Esclavo ejecuta las tareas principales:  
> * **4.1.-** Lee dos fotoresistencias mediante ADC.  
> * **4.2.-** Controla un motor DC mediante PWM y un puente H.  
> * **4.3.-** Mide las RPM del motor utilizando un sensor infrarrojo tipo herradura.  
* **5.-** El Esclavo devuelve información al Maestro vía SPI.  
* **6.-** El Maestro muestra los datos en el LCD y los envía al celular vía Bluetooth.  

El usuario observa la retroalimentación completa del sistema tanto en el LCD como en su dispositivo móvil.

_____________________________________________________________________________________
## 🎯 Objetivos del Proyecto
### Objetivo General
Desarrollar un sistema embebido distribuido donde dos microcontroladores colaboren para controlar un motor DC, sensar variables analógicas y entregar retroalimentación al usuario mediante Bluetooth y un display LCD.

### Objetivos Específicos
* Implementar comunicación UART con módulo Bluetooth.
* Implementar comunicación SPI Maestro–Esclavo.
* Leer sensores analógicos usando ADC.
* Controlar un motor DC por PWM.
* Medir RPM mediante interrupciones o captura de eventos.
* Definir un protocolo de comandos.
* Mostrar información en LCD y enviarla al móvil.

_____________________________________________________________________________________
## 📦 Requerimientos Técnicos Mínimos

### 1. Comunicación con el Usuario (Bluetooth–UART)
* Recibir comandos desde app móvil.
* Enviar retroalimentación estructurada y clara.

### 2. Microcontrolador Maestro
* Mostrar información relevante en un LCD 16×2.
* Reenviar comandos al Esclavo mediante SPI.
* Manejo simple de errores de comunicación.

### 3. Microcontrolador Esclavo
* Leer dos sensores LDR mediante ADC.
* Generar PWM para controlar motor DC.
* Medir RPM mediante sensor infrarrojo tipo herradura.
* Responder comandos enviados por el Maestro.

### 4. Protocolo de Comandos
Debe incluir al menos 5 comandos funcionales, por ejemplo:
* Solicitar luminocidad.
* Solicitar RPM actual.
* Controlar velocidad del motor.
* Encender/apagar.
* Solicitar estado general.

### 5. Retroalimentación
Información visible en:
* LCD 16×2
* Aplicación móvil vía Bluetooth

### 6. Entregables
* Código del Maestro y Esclavo.
* Esquemático electrónico.
* Manual de usuario.
* Reporte técnico.
* Video demostrativo.

_____________________________________________________________________________________
## ⚠️ Restricciones Técnicas
* Usar SPI real, no simulado.
* Usar timers del microcontrolador para PWM.
* Lectura de RPM basada en interrupciones (ICPn o INTn).
* ADC configurado correctamente (prescaler, Vref, canal).
* LCD manejado con librería propia.

_____________________________________________________________________________________
## 📝 Rúbrica de Evaluación (100 puntos)

| Criteria | Description | Points |
|---|---|---|
| **UART–Bluetooth Communication** | **Recepción correcta de comandos, envío de respuestas y manejo básico de errores. -->** | **15** |
| - Command handling | Interpretación adecuada de comandos provenientes del celular | 10 |
| - Feedback formatting | Respuesta clara, estructurada y consistente | 5 |
| **LCD 16×2 Display (Master)** | **Visualización clara del estado del sistema -->** | **10** |
| - Correct LCD updates | Cambios en tiempo real según eventos del sistema | 7 |
| - Readability | Mensajes breves y bien presentados | 3 |
| **SPI Master–Slave Protocol** | **Comunicación correcta, sincronización y estabilidad -->** | **15** |
| - Correct SPI framing | Envío/recepción adecuada de datos | 10 |
| - Error handling | Manejo básico de fallas de comunicación | 5 |
| **ADC – Light Sensors (Slave)** | **Medición estable de dos canales ADC -->** | **10** |
| - Correct ADC configuration | Referencia, prescaler y selección de canal | 7 |
| - Stable sensor reading | Valores coherentes y sin ruido excesivo | 3 |
| **PWM – Motor Control (Slave)** | **Control correcto de velocidad del motor DC -->** | **10** |
| - Duty-cycle variation | Respuesta del motor a múltiples niveles PWM | 7 |
| - Stability | PWM sin jitter perceptible | 3 |
| **RPM Measurement via Encoder (Slave)** | **Conteo confiable mediante interrupciones -->** | **15** |
| - Correct pulse counting | Uso adecuado de interrupciones o captura de eventos | 10 |
| - RPM calculation | Conversión precisa a unidades de RPM | 5 |
| **Command Protocol Design** | **Estructura clara del conjunto de comandos -->** | **10** |
| - Minimum 5 commands | Implementados y documentados | 5 |
| - Logical structure | Sintaxis consistente y fácil de entender | 5 |
| **System Integration** | **Funcionamiento estable entre Maestro–Esclavo–Usuario -->** | **10** |
| - Full system workflow | Flujo continuo sin fallos | 7 |
| - User interaction | Operación intuitiva y bien organizada | 3 |
| **Technical Report and Evidence** | **Documentación y demostración del proyecto -->** | **5** |
| - Report and schematic | Reporte claro, esquemas correctos | 3 |
| - Video demonstration | Demostración funcional del sistema | 2 |


_____________________________________________________________________________________
## 📤 Entrega Final

La carpeta final debe incluir:
* Código fuente del microcontrolador Maestro
* Código fuente del Esclavo
* pdf – Diagrama del sistema
* manual_usuario.pdf – Manual rápido
* demo.mp4 – Video de funcionamientotos.


