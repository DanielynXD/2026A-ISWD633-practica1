# Imagen
### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**
# COMPLETAR
<img width="1219" height="347" alt="image" src="https://github.com/user-attachments/assets/d0cd007c-cccb-42fa-80f4-8b5a2b13fa83" />


**¿Qué es nginx?**
Es un software open source para servicio web, proxy inverso, almacenamiento caché, equilibrio de carga, transmición multimedia y más

Descargar la imagen  **nginx** en la versión **alpine**

```
docker pull nginx:alpine
```
<img width="974" height="369" alt="image" src="https://github.com/user-attachments/assets/d9a52b49-eb09-4087-9967-42c061c5c09a" />

### Listar imágenes

```
docker images
```

<img width="1460" height="152" alt="image" src="https://github.com/user-attachments/assets/e8469e8c-c9d0-469f-8da2-1bb698718413" />


**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
<img width="885" height="812" alt="image" src="https://github.com/user-attachments/assets/0a73c377-4e55-4ab3-ab9a-ca59624cd5f4" />


**¿Con qué algoritmo se está generando el ID de la imagen**
Se cifra con el algoritmo sha256

### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 
<img width="989" height="91" alt="image" src="https://github.com/user-attachments/assets/002ec8a2-04da-41d1-8612-429e9afddfe2" />


-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```
