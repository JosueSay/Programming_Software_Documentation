# Curso de Introducción a la Terminal y Línea de Comandos

![Banner Terminal](../images/banner_terminal.png "Banner Terminal")

## 🖥 **Terminal**

La terminal es una interfaz gráfica que muestra el **prompt** (línea de entrada de comandos), permitiendo al usuario interactuar con el sistema operativo mediante comandos.

## ⚙ **Línea de Comandos (Shell)**

El **Shell** es un programa que interpreta los comandos ingresados por el usuario y ejecuta las operaciones correspondientes en el sistema operativo.

## 🐚 **Tipos de Shell**

Existen diversos tipos de Shell, cada uno con sus propias características y funcionalidades:

| **Tipo de Shell** | **Descripción**                                                                                  |
|--------------------|--------------------------------------------------------------------------------------------------|
| **Bourne Shell (sh)**   | Uno de los primeros shells de Unix. Es simple y eficiente, pero con capacidades limitadas en scripting. |
| **Bash Shell**          | Evolución del Bourne Shell, ampliamente utilizado en Linux. Incluye funciones avanzadas y scripting poderoso. |
| **ZShell (zsh)**        | Shell interactivo moderno con autocompletado mejorado, personalización y plugins avanzados. |
| **C Shell (csh)**       | Diseñado para programación estructurada, incluye soporte para alias y variables.            |
| **Korn Shell (ksh)**    | Combina características del Bourne y C Shell, ideal para scripting avanzado.                |
| **Fish Shell**          | Shell interactivo amigable con autocompletado automático y sugerencias de comandos.         |
| **PowerShell**          | Línea de comandos avanzada de Windows con soporte para scripts en formato de objetos y comandos únicos. |

## Sistema de Archivos

![Sistema de Archivos](../images/sistema_archivos.png "Sistema de Archivos")

En los sistemas operativos basados en Unix, la carpeta **"Home"** es donde se almacena la información del usuario.

### Comandos Básicos

- **`ls`**: Lista las carpetas y archivos en el directorio actual.
- **`clear`** (o `Ctrl + L`): Limpia la terminal.
  
#### Opciones Comunes para `ls`

- **`ls -l`**: Muestra una lista detallada de archivos y carpetas en formato largo.
- **`ls -lh`**: Muestra tamaños de archivos en formato legible para humanos (por ejemplo, KB, MB).
- **`ls -a`**: Muestra archivos ocultos.
- **`ls -S`**: Ordena los archivos por tamaño.
- **`ls -r`**: Muestra los archivos en orden inverso por nombre.

### Navegación de Directorios

- **`cd`**: Cambia al directorio **Home** rápidamente.
- **`pwd`**: Muestra la ruta completa del directorio actual (ruta absoluta).
- **`cd ..`**: Retrocede al directorio anterior.
- **`cd .`**: Se mantiene en el directorio actual.

#### Rutas

- **Relativas**: Usan **`..`** o **`.`** para moverse dentro de la estructura de directorios.
- **Absolutas**: Usan la ruta completa desde la raíz, como **`/home/josue`**.

### Verificación del Tipo de Archivo

- **`file`**: Describe el tipo de archivo. Ejemplo:

```bash
$ file package.json
package.json: JSON data
```

### Comando `tree`

- Muestra la estructura de los archivos y carpetas en forma de árbol. Usa el parámetro **`-L`** para definir los niveles de profundidad:

```bash
tree -L 2
```

## Manipulación de Archivos y Directorios

| **Comando**  | **Descripción**                                                       |
|--------------|-----------------------------------------------------------------------|
| **`mkdir`**  | Crea un nuevo directorio. Si contiene espacios, usa comillas: `mkdir "Mi Directorio"`. Se pueden crear múltiples directorios a la vez: `mkdir dir1 dir2 dir3`. |
| **`touch`**  | Crea un archivo vacío. Se pueden crear múltiples archivos de una vez: `touch file1 file2`. |
| **`cp`**     | Copia archivos. Si no se especifica la ruta de destino, se copia en el mismo directorio: `cp file1 file_bk`. |
| **`mv`**     | Mueve archivos o carpetas. También se usa para renombrar: `mv file_bk ../dir2` o `mv file_bk fileCopy`. |
| **`rm`**     | Elimina archivos. Usa **`-i`** para confirmar la eliminación de manera interactiva: `rm -i fileCopy`. Para directorios usa **`-r`** (recursivo): `rm -r dir1`. La opción **`-f`** fuerza la eliminación sin confirmación: `rm -rf dir1`. Tambipen se pueden eliminar múltiples archivos o directorios a la vez como **`rm -r dir1 dir2`**|

## Contenido de un Archivo

| **Comando** | **Descripción**                                                                 |
|-------------|---------------------------------------------------------------------------------|
| **`head`**  | Muestra las primeras 10 líneas de un archivo. Se puede modificar con **`-n`**: `head archivo.md -n 15`. |
| **`tail`**  | Muestra las últimas 10 líneas de un archivo, se puede modificar igual que `head`. |
| **`less`**  | Permite explorar un archivo de manera interactiva. Usa las flechas o el scroll para moverse, y **`/`** para buscar una palabra o frase. Para salir presiona **`q`**. |

### Abrir un Archivo en una Terminal

Para abrir una terminal en una ruta específica, se puede usar el siguiente comando:

```bash
explorer.exe ruta
```

Este comando abre el explorador de archivos en la ruta especificada.

## Comandos

![Comandos](../images/comando.png "Comandos")

### Ver la Naturaleza de un Comando

El comando **`type`** permite verificar la naturaleza de un comando. Ejemplo:

```bash
$ type cd
cd is a shell builtin
```

Algunos comandos son **alias**. Por ejemplo, el comando `ls` utiliza un alias para habilitar colores en la terminal:

```bash
$ type ls
ls is aliased to `ls --color=auto'
```

### Crear Alias

Puedes crear alias personalizados usando el comando **`alias`**. Ejemplo:

```bash
alias l="ls -lh"
```

> **Nota**: Estos alias son **temporales**. Más adelante se explicará cómo crear alias permanentes.

### Obtener Ayuda de Comandos

Hay varias formas de obtener ayuda sobre los comandos:

| **Comando**          | **Descripción**                                                                                   |
|-----------------------|---------------------------------------------------------------------------------------------------|
| **`help <comando>`**  | Muestra ayuda básica sobre un comando.                                                           |
| **`man <comando>`**   | Abre el manual completo de un comando.                                                           |
| **`info <comando>`**  | Proporciona información más resumida que `man`.                                                  |
| **`whatis <comando>`**| Proporciona una descripción breve del comando.                                                   |

Ejemplos:

```bash
help cd
cd --help
man ls
info ls
whatis cd
```

## Wildcards (Comodines)

Los **wildcards** son caracteres especiales que permiten usar patrones para búsquedas avanzadas y manipulación de archivos.

### Comodines Básicos

| **Wildcard** | **Descripción**                                                   | **Ejemplo**                                                                                   |
|--------------|-------------------------------------------------------------------|----------------------------------------------------------------------------------------------|
| **`*`**      | Coincide con **cualquier número de caracteres**.                  | **`ls *.txt`**: Lista todos los archivos que terminan en `.txt`.                             |
| **`?`**      | Coincide con **un solo carácter**.                                | **`ls datos?`**: Lista archivos como `datos1`.                                              |
| **`[ ]`**    | Coincide con **un rango o conjunto de caracteres específicos**.   | **`ls [ad]*`**: Lista archivos que comienzan con `a` o `d`.                                  |
| **`[[:upper:]]`** | Coincide con caracteres **en mayúsculas**.                  | **`ls -d [[:upper:]]*`**: Lista directorios que comienzan con mayúsculas.                   |
| **`[[:lower:]]`** | Coincide con caracteres **en minúsculas**.                  | **`ls -d [[:lower:]]*`**: Lista directorios que comienzan con minúsculas.                   |

### Ejemplos Prácticos

#### Usando `*` (Asterisco)

```bash
$ ls *.txt
dot.txt  dot2.txt  file.txt
```

```bash
$ ls datos*
datos1  datos123
```

#### Usando `?` (Interrogación)

```bash
$ ls datos?
datos1
```

```bash
$ ls datos???
datos123
```

#### Usando Rango de Caracteres `[ ]`

Lista directorios que comienzan con **mayúsculas**:

```bash
$ ls -d [[:upper:]]*
Lab4_CSS  Lab5_JS  LaptopUnveilingHTML  LaptopUnveilingHTML.rar  OverBlogWatch  OverBlogWatchApi
```

Lista directorios que comienzan con **minúsculas**:

```bash
$ ls -d [[:lower:]]*
abc     datos123  dir2     dot2.txt  go                           index.html    package-lock.json  postgresql.conf
datos1  dir1      dot.txt  file.txt  go1.22.5.linux-amd64.tar.gz  node_modules  package.json       snap
```

Filtrar por archivos/directorios que comienzan con letras específicas (`a` o `d`):

```bash
$ ls [ad]*
abc  datos1  datos123  dot.txt  dot2.txt
```

### Uso de Wildcards en Manipulación de Archivos

Los wildcards también son útiles con comandos como **`rm`**, **`cp`**, o **`mv`**:

- **`rm *.log`**: Elimina todos los archivos que terminan en `.log`.
- **`cp datos* backup/`**: Copia todos los archivos que comienzan con "datos" al directorio `backup`.
- **`mv [ad]* folder/`**: Mueve todos los archivos que comienzan con "a" o "d" al directorio `folder`.

## Redirecciones

![Redirecciones](../images/redirecciones.png "Redirecciones")

Las redirecciones en la shell permiten manipular las salidas estándar, errores y entradas de los comandos. Cada flujo tiene un número asociado:

| **Flujo**             | **Número** |
|-----------------------|------------|
| **Entrada estándar**  | `0`        |
| **Salida estándar**   | `1`        |
| **Error estándar**    | `2`        |

Se utilizan los símbolos `>` y `>>` para redirigir o concatenar estos flujos hacia archivos o dispositivos.

### **Redirigir la Salida Estándar (`1`)**

Para guardar la salida de un comando en un archivo, usa el símbolo `>`:

```bash
ls Pictures > misFotos.txt
```

Esto captura la salida del comando `ls Pictures` y la guarda en el archivo `misFotos.txt`. Si el archivo ya existe, su contenido será sobrescrito.

### **Concatenar la Salida Estándar (`>>`)**

Si deseas **añadir** información al archivo en lugar de sobrescribirlo, utiliza `>>`:

```bash
ls Downloads >> misFotos.txt
```

Este comando agrega la salida del comando `ls Downloads` al final de `misFotos.txt` sin borrar el contenido existente.

### **Redirigir el Error Estándar (`2`)**

Para capturar errores de un comando en un archivo, usa `2>`:

```bash
ls skaond 2> error.txt
```

En este ejemplo, si el comando `ls skaond` genera un error, dicho error se guarda en el archivo `error.txt`.

### **Redirigir Ambos Flujos: Salida y Error**

Puedes redirigir simultáneamente la salida estándar y el error estándar a un solo archivo usando `2>&1`:

```bash
ls sjdoai > output.txt 2>&1
```

- **`> output.txt`**: Redirige la salida estándar al archivo `output.txt`.
- **`2>&1`**: Indica que el error estándar (`2`) debe redirigirse al mismo lugar que la salida estándar (`1`).

Esto asegura que tanto la salida como los errores se capturen en el archivo `output.txt`.

### **Usar la Entrada Estándar (`0`)**

Es posible redirigir datos desde un archivo o dispositivo hacia la entrada de un comando:

```bash
cat < archivo.txt
```

Aquí, `archivo.txt` se usa como entrada para el comando `cat`.

### **Combinaciones Avanzadas**

1. **Redirigir Salida Estándar y Error a Archivos Diferentes**:

   ```bash
   comando > salida.txt 2> errores.txt
   ```

   - `> salida.txt`: Guarda la salida estándar en `salida.txt`.
   - `2> errores.txt`: Guarda el error estándar en `errores.txt`.

2. **Silenciar la Salida Estándar**:

   Para descartar la salida estándar, redirígela a `/dev/null`:

   ```bash
   comando > /dev/null
   ```

   Esto elimina cualquier salida del comando.

3. **Silenciar Ambos Flujos**:

   Para descartar tanto la salida estándar como los errores:

   ```bash
   comando > /dev/null 2>&1
   ```

### **Resumen de Operadores de Redirección**

| **Operador**  | **Descripción**                                                                 |
|---------------|---------------------------------------------------------------------------------|
| `>`           | Redirige la salida estándar (sobrescribe el archivo de destino).               |
| `>>`          | Redirige la salida estándar (concatena al archivo de destino).                 |
| `2>`          | Redirige el error estándar (sobrescribe el archivo de destino).                |
| `2>>`         | Redirige el error estándar (concatena al archivo de destino).                  |
| `<`           | Redirige la entrada estándar desde un archivo.                                 |
| `/dev/null`   | Descartar la salida o errores (útil para silenciar comandos).                  |
| `2>&1`        | Combina la salida estándar y el error estándar en el mismo destino.            |

### **Ejemplo Completo**

```bash
ls archivos > salida.txt 2> errores.txt
```

En este ejemplo:

- La salida estándar de `ls archivos` se guarda en `salida.txt`.
- Los errores generados (si los hay) se guardan en `errores.txt`.

## Operador Pipe (`|`)

El operador **pipe** (`|`) permite redirigir la salida estándar de un comando hacia la entrada estándar de otro. Es una herramienta poderosa para crear flujos de procesamiento en la shell, facilitando la manipulación de datos sin necesidad de archivos intermedios.

### **Comandos Básicos Usados con Pipe**

1. **`echo`**:
   Muestra texto o variables en la salida estándar:

   ```bash
   echo "Hola, mundo"
   ```

2. **`cat`**:
   Muestra el contenido de un archivo o combina múltiples archivos en la salida estándar:

   ```bash
   cat archivo.txt
   ```

   También puede redirigir su entrada desde un archivo:

   ```bash
   cat < archivo.txt
   ```

### **Usando el Operador Pipe**

El pipe toma la salida estándar de un comando y la redirige como entrada estándar de otro. Ejemplo básico:

```bash
ls -lh | less
```

- **`ls -lh`**: Genera una lista detallada de archivos.
- **`less`**: Permite explorar la salida de forma interactiva (avanzar, retroceder y buscar).

### **Creando Archivos con `tee`**

El comando `tee` guarda la salida estándar en un archivo y simultáneamente la pasa como entrada a otro comando. Ejemplo:

```bash
ls -lh | tee output.txt | less
```

- **`ls -lh`**: Lista archivos.
- **`tee output.txt`**: Guarda la salida en el archivo `output.txt` y la envía a `less`.
- **`less`**: Muestra la salida en una interfaz interactiva.

Esto evita la necesidad de realizar múltiples redirecciones manualmente.

### **Ejemplo Complejo con `sort`**

Podemos combinar varios comandos con pipes. Por ejemplo, ordenar una lista, guardarla y visualizarla interactivamente:

```bash
ls -lh | sort | tee output.txt | less
```

- **`sort`**: Ordena alfabéticamente la salida de `ls`.
- **`tee`**: Guarda el resultado en `output.txt`.
- **`less`**: Permite interactuar con el resultado.

### **Mostrando Mensajes en Colores**

Los pipes también funcionan con comandos para personalizar la salida. Por ejemplo:

```bash
cowsay "Hola mundo" | lolcat
```

- **`cowsay`**: Genera un mensaje dentro de un bocadillo de texto acompañado de una vaca ASCII.
- **`lolcat`**: Aplica colores degradados al texto.

Salida:

```markdown
 ____________
< hola mundo >
 ------------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```

### **Librería `sharutils`**

La biblioteca **sharutils** proporciona herramientas para codificar y decodificar archivos en formatos especiales, como `uuencode` y `uudecode`, usados para empaquetar y compartir archivos en sistemas UNIX.

#### **Instalación**

Para instalar la biblioteca en sistemas basados en Debian:

```bash
sudo apt install sharutils
```

#### **Codificar un Archivo: `uuencode`**

El comando `uuencode` convierte un archivo en un formato seguro para transmisión (por ejemplo, por correo electrónico). Ejemplo:

```bash
uuencode archivo.txt archivo_codificado.txt > archivo.uu
```

- **`archivo.txt`**: Archivo original.
- **`archivo_codificado.txt`**: Nombre que tendrá el archivo después de ser decodificado.
- **`archivo.uu`**: Salida codificada.

#### **Decodificar un Archivo: `uudecode`**

Para recuperar un archivo codificado con `uuencode`, usa `uudecode`:

```bash
uudecode archivo.uu
```

Esto genera el archivo original (`archivo_codificado.txt`) en el directorio actual.

#### **Flujo Completo**

1. Codificar un archivo:

   ```bash
   uuencode archivo.txt archivo.txt > archivo.uu
   ```

2. Compartir el archivo `archivo.uu`.

3. Decodificar en otro sistema:

   ```bash
   uudecode archivo.uu
   ```

El archivo original estará disponible con el mismo nombre especificado durante la codificación.

## Operadores de Control

Los operadores de control en la shell son símbolos reservados que permiten ejecutar y encadenar múltiples comandos de diversas maneras. Estos operadores son útiles para controlar el flujo de ejecución, ejecutar comandos condicionalmente, o correr tareas en segundo plano.

### **Ejecución Secuencial con `;`**

El operador `;` permite ejecutar múltiples comandos de forma secuencial. Cada comando se ejecuta en orden, sin importar si el anterior tuvo éxito o no. Ejemplo:

```bash
ls; mkdir hola; cal
```

- **`ls`**: Lista los archivos del directorio actual.
- **`mkdir hola`**: Crea un directorio llamado `hola`.
- **`cal`**: Muestra el calendario del mes actual.

En este caso, todos los comandos se ejecutan uno tras otro, independientemente de su resultado.

### **Ejecución en Segundo Plano con `&`**

El operador `&` ejecuta comandos de manera asíncrona, es decir, cada comando se ejecuta en segundo plano en un hilo del procesador. Esto es útil para correr múltiples tareas simultáneamente.

```bash
ls & date & cal
```

Salida típica:

```bash
[1] 147207
[2] 147208
Wed Dec 18 14:20:49 CST 2024
Lab4_CSS                 OverBlogWatch                hola               postgresql.conf
Lab5_JS                  OverBlogWatchApi             node_modules       snap
LaptopUnveilingHTML      go                           package-lock.json
LaptopUnveilingHTML.rar  go1.22.5.linux-amd64.tar.gz  package.json
   December 2024
Su Mo Tu We Th Fr Sa
 1  2  3  4  5  6  7
 8  9 10 11 12 13 14
15 16 17 18 19 20 21
22 23 24 25 26 27 28
29 30 31

[1]-  Done                    ls --color=auto
[2]+  Done                    date
```

- **`ls &`**: Lista los archivos del directorio en segundo plano.
- **`date &`**: Muestra la fecha y hora actuales en segundo plano.
- **`cal &`**: Muestra el calendario en segundo plano.

Cada tarea genera un identificador de proceso (PID) y un indicador del estado (`Done` cuando termina).

### **Ejecución Condicional con `&&`**

El operador `&&` asegura que el segundo comando se ejecutará solo si el primero tiene éxito (código de salida `0`). Este operador es ideal para comandos que dependen del éxito de un paso previo.

```bash
mkdir test && cd test
```

- **`mkdir test`**: Crea un directorio llamado `test`.
- **`cd test`**: Cambia al directorio `test` si fue creado con éxito.

Si `mkdir test` falla (por ejemplo, si el directorio ya existe), `cd test` no se ejecutará.

### **Ejecución Alternativa con `||`**

El operador `||` ejecuta el segundo comando solo si el primero falla (código de salida distinto de `0`). Este operador es útil para definir acciones alternativas.

```bash
mkdir hola || echo "El directorio ya existe"
```

- **`mkdir hola`**: Intenta crear un directorio llamado `hola`.
- **`echo "El directorio ya existe"`**: Muestra un mensaje si `mkdir hola` falla.

### **Combinaciones de Operadores**

Es posible combinar múltiples operadores para lograr un flujo de control más complejo. Ejemplo:

```bash
mkdir nueva_carpeta && cd nueva_carpeta || echo "Error al crear o entrar en el directorio"
```

- **`mkdir nueva_carpeta && cd nueva_carpeta`**: Intenta crear un directorio y cambiar a él si tiene éxito.
- **`|| echo "Error al crear o entrar en el directorio"`**: Muestra un mensaje si cualquiera de los pasos falla.

### **Ejemplo Complejo**

Un flujo completo que combina varios operadores:

```bash
mkdir proyecto && cd proyecto && touch main.py || echo "Error al configurar el proyecto"
```

1. Crea el directorio `proyecto`.
2. Cambia al directorio `proyecto`.
3. Crea un archivo vacío `main.py`.
4. Si falla cualquiera de los pasos, muestra un mensaje de error.
