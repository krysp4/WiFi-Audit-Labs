# 06 - Instalación de Airgorah en Kali Linux

Airgorah es una herramienta gráfica poderosa para auditorías WiFi. A continuación, se detalla el proceso de instalación paso a paso, incluyendo cómo resolver los errores comunes de dependencias.

## 1. Descarga del Paquete

Primero, descargamos la última versión del paquete `.deb` desde el repositorio oficial de GitHub.

```bash
wget https://github.com/martin-olivier/airgorah/releases/download/v0.7.3/airgorah_0.7.3_x86_64.deb
```
---

## 2. Intento de Instalación y Errores

Al intentar instalarlo con `apt`, es común encontrarse con errores de dependencias insatisfechas, especialmente con `policykit-1`.

```bash
sudo apt install ./airgorah_0.7.3_x86_64.deb
```

### El error común:
> **Error**: Depende de `policykit-1` pero no es instalable.

Esto sucede porque en versiones modernas de Kali, el paquete se llama `polkitd` o el nombre de la dependencia ha cambiado.

---

## 3. Resolución de Problemas

Para solucionar esto, primero intentamos actualizar nuestros repositorios e instalar las librerías necesarias de polkit:

```bash
sudo apt update
sudo apt install polkitd libpolkit-agent-1-0 libpolkit-gobject-1-0 pkexec
```
---

## 4. Instalación Forzada (Solución Final)

Si después de instalar las librerías sigue dando error de dependencia con `policykit-1`, podemos forzar la instalación ignorando esa dependencia específica, ya que las librerías equivalentes ya están en el sistema:

```bash
sudo dpkg -i --ignore-depends=policykit-1 airgorah_0.7.3_x86_64.deb
```

**Explicación del comando**:
- `dpkg -i`: Instala el archivo .deb.
- `--ignore-depends=policykit-1`: Salta la verificación de esa dependencia específica que causaba el fallo.

---

## 5. Ejecución

Una vez instalado, podemos lanzar la aplicación simplemente escribiendo su nombre en la terminal:

```bash
airgorah
```
> [!NOTE]
> Es posible que al ejecutarlo veas algunos avisos (Warnings) sobre drivers de video (DRI3) o temas de GTK, pero la aplicación debería funcionar correctamente para auditar redes.
