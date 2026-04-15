# Mapeo de puertos
El mapeo de puertos es un mecanismo que permite redirigir el tráfico de red desde un puerto en el host (tu máquina local o servidor) hacia un puerto específico en un contenedor Docker.
Por ejemplo, supongamos que tienes un contenedor que ejecuta un servidor web en el puerto 80 dentro del contenedor, pero quieres acceder a ese servidor desde tu navegador en la máquina host. Puedes usar el mapeo de puertos para redirigir el tráfico del puerto 80 del contenedor al puerto 3000 en el host. De esta manera, cuando accedas a http://localhost:3000 en tu navegador, el tráfico se dirigirá al servidor web dentro del contenedor en el puerto 80.

![mapeo](mapeoPuertos.PNG)

### Para crear un mapeo de puertos (puerto host y puerto contenedor)
El mapeo de puertos se especifica al ejecutar un contenedor Docker utilizando la opción -p o --publish seguida de los puertos que deseas mapear
```
docker run -d --name <nombre contenedor> -p <puerto host>:<puerto contenedor> <nombre imagen>:<tag>

```
Crear un contenedor a partir de la imagen nginx version alpine con el mapeo de puertos del ejemplo gráfico, host 3000 y contenedor 80
<img width="825" height="65" alt="image" src="https://github.com/user-attachments/assets/666efcb0-4150-4abb-8c3a-981604b51513" />


<img width="1898" height="1011" alt="image" src="https://github.com/user-attachments/assets/3eae09d0-ca5a-4bb2-9cfb-5aa8a2e8bc29" />


### Para mapear más de un puerto

```
docker run -d --name <nombre contenedor> -p <puerto host 01>:<puerto contenedor 01> -p <puerto host 02>:<puerto contenedor 02> <nombre imagen>:<tag>
```

Crear un contenedor a partir de la imagen rabbitmq version management-alpine, para este mapeo de puertos usar en el host los mismos puertos del contenedor.
<img width="1447" height="524" alt="image" src="https://github.com/user-attachments/assets/d1b6e9f4-ac6c-4e96-9edd-e02edc45c71e" />

<img width="1902" height="1001" alt="image" src="https://github.com/user-attachments/assets/85e27412-2909-4678-8f53-59d6e3da98ad" />

### Usando una forma más semántica cuando se especifican puertos

```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> <nombre imagen>:<tag> 
```
### Publicando todos los puertos
```
docker run -P -d --name <nombre contenedor> <nombre imagen>:<tag> 
```

-P: le indica a Docker que asigne automáticamente puertos aleatorios en tu host para todos los puertos expuestos por el contenedor.

**Recordar**
No puedes mapear puertos a un contenedor existente directamente después de su creación con Docker. El mapeo de puertos debe especificarse en el momento de crear y ejecutar el contenedor.

### Crear contenedor de Jenkins puertos contenedor: 8080 (interface web) y 50000 (comunicación entre nodos) imagen: jenkins/jenkins:alpine3.18-jdk11
<img width="1097" height="453" alt="image" src="https://github.com/user-attachments/assets/d7ea2e7a-747c-4751-abf4-b524330e6f30" />



# http://localhost:8080
<img width="1917" height="1018" alt="image" src="https://github.com/user-attachments/assets/16bc24bc-0cc4-497b-a957-4d16dd053ef1" />


### ¿Cómo obtener la contraseña solicitada?
Para obtener la contraseña solicitada es necesario ingresar al contenedor.

![Imagen](jenkins.PNG)

