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
*   [**06 - Instalación de Airgorah**](./06_instalacion_airgorah.md)
    *   *Guía paso a paso para instalar Airgorah y resolver errores de dependencias.*

### 🎭 Fase 4: Ingeniería Social
*   [**07 - Rogue AP con Wifipumpkin3**](./07_wifipumpkin3.md)
    *   *Creación de puntos de acceso falsos con portales cautivos (CaptiveFlask) para robar credenciales.*

### 🛠️ Fase 4: Análisis
*   [**05 - Análisis de Capturas y Handshake**](./05_wireshark.md)
    *   *Identificación de SSID con Wireshark y extracción de hashes con Aircrack-ng.*

### 🧹 Fase 5: Post-Auditoría
*   [**04 - Restauración del Sistema**](./04_restauracion.md)
    *   *Limpieza de procesos y restauración del NetworkManager.*

---

## 🧰 Glosario de Herramientas

A lo largo de estos apuntes, utilizaremos diversas herramientas especializadas. Aquí tienes un resumen rápido de para qué sirve cada una:

*   **`airmon-ng`**: Cambia el estado de la tarjeta de red de modo "Managed" (normal) a modo "Monitor" (escuha global) y detiene procesos que puedan interferir.
*   **`airodump-ng`**: Es el radar. Escanea el espectro WiFi, muestra las redes disponibles, los clientes conectados a ellas y captura sus paquetes (como el handshake) a un archivo.
*   **`aireplay-ng`**: Es el inyector. Genera tráfico malicioso, como forzar la desconexión de clientes (ataque Deauth) para que se vuelvan a conectar y podamos capturar su contraseña cifrada.
*   **`aircrack-ng`**: Es el crackeador (CPU). Analiza los archivos de captura (`.cap`) para verificar si contienen contraseñas (handshakes) y puede intentar descifrarlas usando diccionarios.
*   **`Wireshark`**: Analizador de protocolos de red (Sniffer). Permite abrir los archivos `.cap` y estudiar los paquetes de forma gráfica para extraer información oculta, como el nombre de una red (SSID).
*   **`Airgorah`**: Es una interfaz gráfica moderna para la suite aircrack-ng. Hace el mismo trabajo de escanear, capturar y desautenticar, pero desde una ventana amigable en lugar de la terminal de comandos.
*   **`Wifipumpkin3`**: Framework avanzado para ataques de Ingeniería Social. Permite crear redes WiFi falsas (Rogue AP) con portales cautivos para engañar a los usuarios y que introduzcan sus credenciales voluntariamente.

---

## 🛠️ Requisitos del Laboratorio

- 🐧 **Sistema**: Kali Linux o otros.
- 📶 **Hardware**: Tarjeta WiFi con soporte para **Modo Monitor** e **Inyección**.
- 🧰 **Software**: Suite `aircrack-ng` y `Wireshark`.