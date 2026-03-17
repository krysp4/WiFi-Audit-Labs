# WiFi-Audit-Labs: Guía de Auditoría de Redes Inalámbricas

Esta serie de apuntes está diseñada para documentar el proceso de auditoría de redes WiFi de forma educativa, desde el reconocimiento inicial hasta la captura de tráfico y ataques controlados.

> [!IMPORTANT]
> Esta guía tiene fines exclusivamente educativos y de auditoría ética. El acceso a redes sin autorización es ilegal.

## Índice de Contenidos

1. [**01 - Reconocimiento de Red**](file:///c:/Users/adria/Documents/A%20Educem/apuntesHardcore/01_reconocimiento.md): Verificación de la antena y escaneo inicial.
2. [**02 - Activación del Modo Monitor**](file:///c:/Users/adria/Documents/A%20Educem/apuntesHardcore/02_modo_monitor.md): Preparación de la tarjeta para inyección de paquetes.
3. [**03 - Captura de Paquetes y Ataques**](file:///c:/Users/adria/Documents/A%20Educem/apuntesHardcore/03_captura_y_ataque.md): Obtención del handshake y ataques de desautenticación.
4. [**04 - Restauración del Sistema**](file:///c:/Users/adria/Documents/A%20Educem/apuntesHardcore/04_restauracion.md): Volver a la configuración de red normal.
5. [**05 - Análisis de Capturas y Handshake**](file:///c:/Users/adria/Documents/A%20Educem/apuntesHardcore/05_wireshark.md): Análisis con Wireshark y extracción de hash con Aircrack-ng.

---

## Requisitos Previos

- Un sistema Linux (o máquina virtual con Kali Linux/Parrot OS).
- Una tarjeta WiFi compatible con **Inyección de Paquetes** y **Modo Monitor**.
- Suite `aircrack-ng` instalada.
