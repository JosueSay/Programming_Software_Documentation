# 💻 Curso de Configuración de Entorno de Desarrollo en Windows

![Banner Configuración Windows](../images/banner_configuracion_windows.png "Banner Configuración Windows")

## 🌐 **Navegadores**

Los navegadores sirven para **visitar sitios web**. Se conectan a un servidor a través de una petición **HTTP** o **HTTPS** (*Hypertext Transfer Protocol*), obteniendo información y renderizándola en el sitio web.  

### 🤔 **¿Por qué las páginas se ven igual en distintos navegadores?**

En un inicio, las páginas se veían diferentes en cada navegador, ya que cada uno tenía su propia forma de interpretar una página web. Con el tiempo, esto **se estandarizó** gracias a la creación de HTML para estructurar páginas web y **CSS** para definir el estilo visual. Esto permitió que los navegadores **se pusieran de acuerdo** y mostraran sitios de manera uniforme.  

Además, los navegadores se encargan de ejecutar **JavaScript**, el cual permite generar interacción y dinamismo en los sitios web.  

#### 🛠️ **3 elementos clave para una página web**

1. **HTML** - Estructura la página.  
2. **CSS** - Da estilo y diseño visual.  
3. **JavaScript** - Añade interacción y dinamismo.  

### 🚀 **Ejemplo: Google Chrome**

![Chrome](../images/chrome.png "Chrome")  

Google Chrome es un ejemplo de navegador moderno. Cuenta con **3 versiones principales**:  

1. **Stable** ✅  
   - Es la versión **estable** de Chrome y se descarga por defecto.  
2. **Dev** 🛠️  
   - Versión de **desarrollo** que permite probar código en futuras versiones estables de Chrome (entre **9 a 12 semanas** antes de su lanzamiento).  
3. **Canary** 🧪  
   - Es una versión **experimental**, no recomendada para trabajar en producción debido a su inestabilidad.  

### 🔗 **Estándares y motores de navegación**

Una gran ventaja es que muchos navegadores utilizan el mismo **motor de Chrome**, conocido como **Chromium**, lo cual ayuda a establecer un **estándar común** para el desarrollo de sitios web.

## 🐧 **WSL 2 (Windows Subsystem for Linux)**  

**WSL 2** es una herramienta que permite tener el **kernel de Linux** funcional en Windows. Esto es especialmente útil porque, históricamente, muchos sistemas y herramientas de desarrollo web, backend, frontend, e incluso videojuegos se basan en Linux o macOS.  

Microsoft se dio cuenta de que estaba perdiendo parte del público desarrollador, así que integró Linux como una herramienta dentro de Windows.  

### 🔧 **Instalación de WSL 2**  

Para instalar WSL 2, sigue estos pasos:  

1. **Instala Windows Terminal desde la Microsoft Store**  
   Esta herramienta es ideal porque permite personalizar muchas configuraciones mediante un archivo **JSON**.  

   ![Windows Terminal](../images/windows_terminal.png "Windows Terminal")  

2. **Ejecuta el siguiente comando en una terminal:**

   ```bash
   wsl --install
   ```

   - El sistema solicitará varios permisos, **acéptalos**.  
   - Una vez completado, la instalación estará lista.  

---

### ⚠️ **Solución de errores comunes**  

#### 🔄 **Error de Virtualización**  

Si ocurre un error relacionado con la **virtualización**, sigue estos pasos:  

1. Abre **PowerShell** como **Administrador**.  
2. Ejecuta el siguiente comando para habilitar las características de máquinas virtuales:  

   ```bash
   dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
   ```  

---

#### 🛡️ **Error 0x80370114**  

Este error puede ocurrir al iniciar **Ubuntu** por primera vez. Aquí hay dos posibles soluciones:  

##### **Solución 1: Ajustar la seguridad de Windows**  

1. Abre **Windows Security**.  
2. Ve a **App & Browser Control**.  
3. Haz clic en **Exploit Protection Settings**.  
4. Selecciona la pestaña **Program settings**.  
5. Busca `C:\WINDOWS\System32\vmcompute.exe`.  
6. Haz clic en **Edit** y ajusta la configuración.  

##### **Solución 2: Activar características de Windows**  

1. Abre **"Turn Windows features on or off"** (Activar o desactivar características de Windows).  
2. Activa las siguientes opciones:  
   - **Windows Subsystem for Linux**  
   - **Virtual Machine Platform**  
   - **Windows PowerShell 2.0**  
3. Aplica los cambios y **reinicia la computadora**.  

### 🧑‍💻 **Configuración de la Cuenta Unix**  

Una vez solucionados los errores:  

1. Al iniciar Ubuntu por primera vez, el sistema te pedirá **crear una cuenta Unix**.  
2. Configura un **usuario y contraseña**.  

¡Listo! Ahora tendrás la **terminal Linux disponible** dentro de Windows. 🎉  

## 💻 **VirtualBox**  

**VirtualBox** es una alternativa a **WSL** que permite instalar y ejecutar una **máquina virtual**. La virtualización toma los recursos del equipo local (**host**) y los asigna a un equipo virtual (**invitado**).  

### 🛠️ **¿Por qué usar VirtualBox?**  

- Es ideal para **mantenimiento** y **optimización de recursos**, ya que permite virtualizar varios sistemas en un mismo equipo físico.  
- Puedes ejecutar diferentes **sistemas operativos**, como **Ubuntu**, sin afectar tu sistema principal.  

### 📥 **Instalación de VirtualBox y Ubuntu**  

1. **Descarga Oracle VirtualBox** desde su página oficial.  
2. Consigue una imagen **ISO de Ubuntu**.  
3. Crea una nueva máquina virtual en VirtualBox y asigna los recursos necesarios:  
   - **RAM**  
   - **Núcleos de CPU**  
   - **Espacio en Disco**  

### 🚀 **Configuración de Ubuntu en VirtualBox**  

1. **Instalación de aplicaciones útiles**  
   Utiliza la tienda **Ubuntu Software** para instalar aplicaciones como:  
   - **VS Code** (Editor de código)  
   - **Zoom** (Videollamadas)  
   - **Terminator** (Terminal avanzada)  

2. **Abrir la terminal**  
   - Ve a **"Activities"**.  
   - Escribe **"Terminal"** en la barra de búsqueda.  

### 🔌 **Apagar y Reiniciar la Máquina Virtual**  

- Para **apagar** la máquina virtual:  
  - Ve a **"Activities"** dentro de Ubuntu y selecciona las opciones de apagado en el menú superior.  

- Para **reiniciar** la máquina virtual:  
  - Cierra Ubuntu y regresa a **Oracle VirtualBox**.  
  - Desde allí, puedes **iniciar** nuevamente la máquina virtual.  

## 🖥️ **Comandos Básicos**

| **Comando** | **Descripción**                               |
|-------------|-----------------------------------------------|
| `pwd`       | Muestra la ruta actual del directorio.        |
| `cd`        | Cambia de directorio.                         |
| `~`         | Indica que estamos en la carpeta principal.   |
| `..`        | Retrocede un directorio.                      |
| `.`         | Selecciona el directorio actual.              |
| `/`         | Representa el directorio raíz.                |
| `clear`     | Limpia la terminal.                           |
| `reset`     | Reinicia la consola en caso de lentitud.      |
| `touch`     | Crea un archivo vacío.                        |
| `ls`        | Lista los archivos del directorio.            |
| `code .`    | Abre Visual Studio Code en el directorio actual. |

## 🚀 **Node.js**

Node.js es un **entorno de ejecución para JavaScript** en el servidor.  
NPM (Node Package Manager) es un **gestor de paquetes** para JavaScript.

### **Instalación de Node.js y NPM**

Para instalar **Node.js**, utiliza el siguiente comando:

```bash
sudo apt install nodejs
```

Para instalar **NPM**, el gestor de paquetes de Node.js, utiliza:

```bash
sudo apt install npm
```

### **Actualizar Node.js a la última versión**

Para actualizar Node.js, primero instala la herramienta `n`:

```bash
npm install -g n
```

Luego, utiliza el siguiente comando para actualizar Node.js a la última versión:

```bash
n latest
```

📌 **Nota:** Después de actualizar, cierra y vuelve a abrir la terminal para aplicar los cambios.

## 🐍 **Python**

Python es un lenguaje de programación versátil que se utiliza para desarrollo web, ciencia de datos, automatización, entre otros.

### **Preparar la instalación de Python**

Primero, instala las herramientas necesarias:

```bash
sudo apt install software-properties-common
```

Luego, agrega el repositorio de Python:

```bash
sudo add-apt-repository ppa:deadsnakes
```

Actualiza los repositorios para cargar el nuevo repositorio:

```bash
sudo apt update
```

### **Instalar una versión específica de Python**

Para instalar **Python 3.13.1**, utiliza el siguiente comando:

```bash
sudo apt install python3.13.1
```

## 🐙 **Git**

Git es un sistema de control de versiones distribuido utilizado para gestionar proyectos de manera eficiente.

### **Instalación de Git**

Para instalar Git en tu sistema, ejecuta el siguiente comando en la terminal:

```bash
sudo apt-get install git-all
```

## 🔑 **SSH (Secure Shell)**

SSH es un protocolo utilizado para acceder de forma segura a servidores y dispositivos remotos. Una de las funcionalidades clave de SSH es el uso de llaves públicas y privadas para autenticación.

### **Generar una llave SSH**

Para generar una llave SSH, utiliza el siguiente comando:  

```bash
ssh-keygen -t ed25519 -C "correo@gmail.com"
```

🔍 **Explicación de los parámetros:**

- `-t ed25519`: Especifica el tipo de algoritmo de encriptación a utilizar (en este caso, **ed25519**, recomendado por su seguridad y rapidez).
- `-C "correo@gmail.com"`: Añade un comentario identificador para la llave (generalmente tu correo electrónico).  
- `-f ~/.ssh/name_ssh_key`: (Opcional) Define un nombre y ruta personalizados para la llave, en lugar del valor predeterminado (`id_ed25519`).

### **Proceso de generación**

1. Una vez ejecutado el comando, se te pedirá:  
   - **Ruta para guardar la llave**: Presiona `Enter` para usar la predeterminada (`~/.ssh/id_ed25519`) o ingresa un nombre/ruta personalizada.  
   - **Passphrase (frase de paso)**: Opcional, pero recomendable para añadir una capa extra de seguridad. Debes recordarla, ya que se usará para desbloquear la llave.  

2. La herramienta generará dos archivos:  
   - **Llave privada**: No la compartas ni distribuyas.  
   - **Llave pública**: Este archivo puede compartirse para configurar accesos en servidores remotos.

### **Verificar que el agente SSH se está ejecutando**

El agente SSH administra las llaves privadas cargadas para evitar ingresar la passphrase repetidamente. Verifica que esté activo con:  

```bash
eval "$(ssh-agent -s)"
```

🔍 Si está funcionando, aparecerá un mensaje similar:  
`Agent pid 12345`

### **Añadir la llave SSH al agente**

Para cargar tu llave privada en el agente SSH, usa:  

```bash
ssh-add ~/.ssh/private_name_key
```

- **~/.ssh/private_name_key**: Especifica la ruta de tu llave privada generada anteriormente.  
- Te pedirá ingresar la passphrase, si configuraste una.  

🔍 **¿Por qué usar `ssh-add`?**  
Este comando carga tu llave en el agente SSH, lo que permite usarla sin necesidad de ingresarla manualmente cada vez que te conectes a un servidor. El agente gestiona estas llaves de manera temporal durante la sesión.

### **Verificación de la llave pública**

Para visualizar tu llave pública y copiarla al servidor remoto, utiliza:  

```bash
cat ~/.ssh/name_ssh_key.pub
```

Copia el contenido y añádelo al archivo `~/.ssh/authorized_keys` del servidor remoto para permitir el acceso.

### **Otros parámetros útiles de `ssh-keygen`**

- `-b <bits>`: Define el tamaño de la llave (por ejemplo, `-b 4096` para llaves RSA).  
- `-N <passphrase>`: Configura la passphrase directamente al generar la llave.  
- `-q`: Ejecuta el comando en modo silencioso, sin mensajes de confirmación.
