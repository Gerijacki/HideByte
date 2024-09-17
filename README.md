<h1 align="center">HideByte - Manual de Uso de Steghide</h1>

<p align="center">
  <img src="https://github.com/Gerijacki.png" width="100" alt="Logo"/><br/>
  Hi 👋, I'm <a href="https://github.com/Gerijacki">Gerijacki</a>
</p>

<p align="center">
  <a href="https://github.com/Gerijacki/HideByte/stargazers"><img src="https://img.shields.io/github/stars/Gerijacki/passWifi?colorA=363a4f&colorB=b7bdf8&style=for-the-badge"></a>
  <a href="https://github.com/Gerijacki/HideByte/issues"><img src="https://img.shields.io/github/issues/Gerijacki/passWifi?colorA=363a4f&colorB=f5a97f&style=for-the-badge"></a>
  <a href="https://github.com/Gerijacki/HideByte/contributors"><img src="https://img.shields.io/github/contributors/Gerijacki/passWifi?colorA=363a4f&colorB=a6da95&style=for-the-badge"></a>
</p>

## Introducción

**Steghide** es una herramienta de software utilizada para **esteganografía**, que permite ocultar archivos dentro de otros, como imágenes o archivos de audio, manteniendo el archivo portador lo más parecido posible al original. Además, Steghide puede cifrar el archivo que ocultas utilizando una contraseña, ofreciendo una capa adicional de seguridad.

## Funciones Principales de Steghide

- **Ocultar archivos**: Permite ocultar un archivo dentro de otro (portador).
- **Extraer archivos**: Permite extraer archivos previamente ocultos en un portador.
- **Compatibilidad**: Puede trabajar con diversos tipos de archivos como imágenes (JPEG, BMP, PNG) y audio (WAV, AU).
- **Compresión**: Automáticamente comprime el archivo a ocultar para reducir el tamaño del portador.
- **Cifrado**: Los datos ocultos pueden estar cifrados utilizando un algoritmo de cifrado como **AES**.
- **Soporte de meta-información**: Preserva información adicional, como el tiempo de modificación del archivo oculto.

---

## Instalación de Steghide

### En sistemas Linux (Debian/Ubuntu):

1. Abre una terminal.
2. Ejecuta el siguiente comando para instalar Steghide:
   ```bash
   sudo apt update
   sudo apt install steghide
   ```

### En sistemas basados en Red Hat (CentOS/Fedora):

1. Usa `dnf` o `yum` para instalar:
   ```bash
   sudo dnf install steghide
   ```
   o
   ```bash
   sudo yum install steghide
   ```

### En sistemas Windows:

1. Descarga el instalador de Steghide desde su página oficial o desde fuentes como GitHub.
2. Sigue las instrucciones del instalador para instalar la herramienta.
3. Asegúrate de agregar Steghide al PATH del sistema para poder ejecutarlo desde cualquier carpeta en la línea de comandos.

---

## Comandos Básicos

### 1. Ocultar un archivo

Para ocultar un archivo dentro de otro archivo portador, utiliza el siguiente comando:

```bash
steghide embed -cf <archivo_portador> -ef <archivo_a_ocultar> -p <contraseña>
```

- `-cf` especifica el archivo portador (ej. una imagen o un archivo de audio).
- `-ef` especifica el archivo que deseas ocultar.
- `-p` establece una contraseña para cifrar el archivo oculto (opcional).

**Ejemplo**:
```bash
steghide embed -cf imagen.jpg -ef secreto.txt -p miContraseña123
```
Este comando ocultará `secreto.txt` dentro de `imagen.jpg` con la contraseña `miContraseña123`.

### 2. Extraer un archivo oculto

Para extraer un archivo oculto de un portador, usa el siguiente comando:

```bash
steghide extract -sf <archivo_portador> -p <contraseña>
```

- `-sf` indica el archivo portador donde está oculto el archivo.
- `-p` es la contraseña con la que se ocultó el archivo.

**Ejemplo**:
```bash
steghide extract -sf imagen.jpg -p miContraseña123
```
Este comando extraerá el archivo oculto de `imagen.jpg` usando la contraseña `miContraseña123`.

### 3. Verificar la información del archivo portador

Puedes verificar si un archivo portador contiene datos ocultos y revisar sus propiedades con este comando:

```bash
steghide info <archivo_portador>
```

**Ejemplo**:
```bash
steghide info imagen.jpg
```

Este comando muestra si `imagen.jpg` tiene datos ocultos y detalles sobre el método de compresión y cifrado.

---

## Métodos Interesantes y Recomendaciones

### 1. Ocultar múltiples archivos

Steghide permite ocultar un archivo comprimido (.zip o .tar.gz) que contenga múltiples archivos. Para hacerlo:

1. Crea un archivo comprimido que contenga los archivos que deseas ocultar:
   ```bash
   zip archivos_ocultos.zip archivo1.txt archivo2.docx
   ```

2. Oculta el archivo comprimido dentro de un portador:
   ```bash
   steghide embed -cf imagen.jpg -ef archivos_ocultos.zip -p miContraseña
   ```

### 2. Cifrado seguro

Siempre utiliza una contraseña fuerte con una combinación de letras mayúsculas, minúsculas, números y caracteres especiales para asegurarte de que los archivos ocultos estén bien protegidos.

### 3. Uso de archivos WAV como portador

Los archivos de audio en formato WAV son altamente recomendados para la esteganografía, ya que son capaces de ocultar grandes cantidades de datos sin perder calidad perceptual.

**Ejemplo**:
```bash
steghide embed -cf cancion.wav -ef documento.pdf -p miContraseñaSegura
```

### 4. Extracción automatizada sin contraseña

Si no usaste una contraseña al momento de ocultar el archivo, puedes extraer el archivo oculto sin la opción `-p`:

```bash
steghide extract -sf imagen.jpg
```

---

## Ejemplos adicionales

### Ocultar un archivo de texto dentro de una imagen PNG:

```bash
steghide embed -cf portada.png -ef nota.txt -p secreto123
```

### Extraer un archivo oculto en una imagen BMP sin contraseña:

```bash
steghide extract -sf imagen.bmp
```

### Comprobar si hay un archivo oculto en un archivo WAV:

```bash
steghide info audio.wav
```

---
## Conclusión

Steghide es una herramienta poderosa para realizar esteganografía de manera segura y eficiente. Su capacidad de compresión, cifrado y compatibilidad con varios formatos de archivo la convierten en una opción ideal para ocultar información confidencial. Solo recuerda utilizar contraseñas seguras y archivos portadores lo suficientemente grandes para evitar una degradación visual o auditiva significativa.

---

<p align="center">
  <a href="https://github.com/Gerijacki">
    <img src="https://github-readme-stats.vercel.app/api?username=Gerijacki&show_icons=true&theme=dark&count_private=true" alt="GitHub Stats" />
  </a>
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/Trilokia/Trilokia/379277808c61ef204768a61bbc5d25bc7798ccf1/bottom_header.svg" />
</p>


