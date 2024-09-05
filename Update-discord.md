
### 1. **Cerrar Discord**:
Primero, asegúrate de que Discord esté completamente cerrado para evitar conflictos durante la actualización. Si está en ejecución, ciérralo.

### 2. **Eliminar la versión actual de Discord**:
Elimina la versión de Discord que ya tienes instalada en `/opt/discord` (asumiendo que fue instalada allí anteriormente):

```bash
sudo rm -rf /opt/discord
```

### 3. **Extraer el archivo `.tar.gz`**:
Descomprime el archivo que descargaste (`discord.0.0.67.tar.gz`):

```bash
tar -xvzf discord.0.0.67.tar.gz
```

Esto creará una carpeta llamada `Discord` en tu directorio actual.

### 4. **Mover la nueva versión a `/opt/discord`**:
Ahora, mueve la carpeta descomprimida `Discord` a `/opt`, donde normalmente se instalan aplicaciones de terceros:

```bash
sudo mv Discord /opt/discord
```

### 5. **Verificar o crear un enlace simbólico**:
Si ya tienes un enlace simbólico para ejecutar Discord, asegúrate de que esté actualizado. Si no lo tienes, créalo para que puedas ejecutar Discord desde la terminal fácilmente:

```bash
sudo ln -sf /opt/discord/Discord /usr/bin/discord
```

### 6. **Instalar dependencias (si es necesario)**:
Si faltan dependencias o librerías, asegúrate de instalarlas:

```bash
sudo pacman -S libnotify libappindicator-gtk3
```

### 7. **Ejecutar Discord**:
Una vez que se haya movido la nueva versión, puedes ejecutar Discord directamente desde la terminal con:

```bash
discord
```

### 8. **Actualizar el acceso directo (opcional)**:
Si ya tienes un acceso directo en tu menú de aplicaciones, no necesitas hacer nada más. Si deseas crear uno, sigue estos pasos:

Crea un archivo `.desktop` en `/usr/share/applications/`:

```bash
sudo nano /usr/share/applications/discord.desktop
```

Agrega este contenido:

```ini
[Desktop Entry]
Name=Discord
Comment=Discord - Chat for Communities and Friends
Exec=/usr/bin/discord
Icon=/opt/discord/discord.png
Type=Application
Categories=Network;InstantMessaging;
```

Guarda el archivo.

### **Resumen**:
1. Cerrar Discord.
2. Eliminar la versión anterior (`/opt/discord`).
3. Extraer el archivo `.tar.gz`.
4. Mover la nueva versión a `/opt/discord`.
5. Verificar o crear el enlace simbólico.
6. Instalar dependencias.
7. Ejecutar Discord.

Estos pasos actualizarán tu instalación de Discord a la nueva versión.
