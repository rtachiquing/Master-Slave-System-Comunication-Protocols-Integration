# Master-Slave-System-Comunication-Protocols-Integration
Sistema Maestro–Esclavo con Comunicación UART/Bluetooth y SPI, Sensado Analógico y Control de Motor DC

_____________________________________________________________________________________
## 🧩 Descripción General

Este proyecto implementa un sistema embebido distribuido basado en dos **microcontroladores STM32F401RE**, configurados bajo una arquitectura **Maestro–Esclavo**.

El flujo general del sistema:

> **1.-** Un usuario envía comandos desde un celular vía Bluetooth usando una app de terminal UART.  
> **2.-** El microcontrolador Maestro recibe esos comandos por UART, los interpreta y los muestra en un LCD 16×2.  
> **3.-** El Maestro reenvía los comandos hacia el microcontrolador Esclavo mediante SPI.  
> **4.-** El Esclavo ejecuta las tareas principales:  
>> **4.1.-** Lee dos fotoresistencias mediante ADC.  
>> **4.2.-** Controla un motor DC mediante PWM y un puente H.  
>> **4.3.-** Mide las RPM del motor utilizando un sensor infrarrojo tipo herradura.  
> **5.-** El Esclavo devuelve información al Maestro vía SPI.  
> **6.-** El Maestro muestra los datos en el LCD y los envía al celular vía Bluetooth.  

El usuario observa la retroalimentación completa del sistema tanto en el LCD como en su dispositivo móvil.

_____________________________________________________________________________________
## 🎯 Objetivos del Proyecto
### Objetivo General
Desarrollar un sistema embebido distribuido donde dos microcontroladores colaboren para controlar un motor DC, sensar variables analógicas y entregar retroalimentación al usuario mediante Bluetooth y un display LCD.

### Objetivos Específicos
Implementar comunicación UART con módulo Bluetooth.

Implementar comunicación SPI Maestro–Esclavo.

Leer sensores analógicos usando ADC.

Controlar un motor DC por PWM.

Medir RPM mediante interrupciones o captura de eventos.

Definir un protocolo de comandos.

Mostrar información en LCD y enviarla al móvil.
