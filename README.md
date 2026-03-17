# 🛡️ WiFi-Audit-Labs: Guía de Auditoría Inalámbrica

Esta serie de apuntes documenta el proceso completo de auditoría de redes WiFi de forma educativa y estructurada. Ideal para laboratorios de ciberseguridad.

---

## 📑 Índice de Contenidos

Haz clic en cada sección para acceder a los apuntes detallados:

### 🔍 Fase 1: Reconocimiento
*   [**01 - Reconocimiento de Red**](./01_reconocimiento.md)
    *   *Verificación de hardware, herramientas `ifconfig`, `iwconfig` y escaneo con `nmcli`.*

### 📡 Fase 2: Configuración
*   [**02 - Activación del Modo Monitor**](./02_modo_monitor.md)
    *   *Uso de `airmon-ng` y test de inyección de paquetes con `aireplay-ng`.*

### ⚔️ Fase 3: Explotación
*   [**03 - Captura de Paquetes y Ataques**](./03_captura_y_ataque.md)
    *   *Captura dirigida con `airodump-ng` y ataques de desautenticación (Deauth).*

### 🛠️ Fase 4: Análisis
*   [**05 - Análisis de Capturas y Handshake**](./05_wireshark.md)
    *   *Identificación de SSID con Wireshark y extracción de hashes con Aircrack-ng.*

### 🧹 Fase 5: Post-Auditoría
*   [**04 - Restauración del Sistema**](./04_restauracion.md)
    *   *Limpieza de procesos y restauración del NetworkManager.*

---

## 🛠️ Requisitos del Laboratorio

- 🐧 **Sistema**: Kali Linux o Parrot OS.
- 📶 **Hardware**: Tarjeta WiFi con soporte para **Modo Monitor** e **Inyección**.
- 🧰 **Software**: Suite `aircrack-ng` y `Wireshark`.

