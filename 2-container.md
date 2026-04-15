# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine
<img width="781" height="72" alt="image" src="https://github.com/user-attachments/assets/ed45ef35-5384-4964-9861-141cc396bf49" />


Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world
<img width="971" height="213" alt="image" src="https://github.com/user-attachments/assets/cd08f4e4-531a-498b-931e-90327080b657" />


### Listar los contenedores ejecutándose o no

```
docker ps -a
```

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web 
<img width="432" height="84" alt="image" src="https://github.com/user-attachments/assets/8d459ad1-d0ae-478a-a3f5-633f17aa58a8" />


### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

### Para detener un contenedor

```
docker stop <nombre contenedor>
```

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine
<img width="1180" height="661" alt="image" src="https://github.com/user-attachments/assets/fbf13339-c523-41c9-ab1c-cbbc085f2e8b" />


**¿Qué sucede luego de la ejecución del comando?**
Cuando usamos el comando docker run, sucede que el contenedor se esta ejecutando en primer plano y la entrada de la terminal esta siendo capturada por el contenedor, no podemos introducir más comandos a menos que se detenga el contenedor.

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine
<img width="789" height="68" alt="image" src="https://github.com/user-attachments/assets/30357a73-3b0f-48e7-8d8e-5e6ed95d7ddb" />
<img width="1390" height="93" alt="image" src="https://github.com/user-attachments/assets/b456cb0d-fb5e-4534-9633-52fa788d657e" />


### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 
<img width="1543" height="184" alt="image" src="https://github.com/user-attachments/assets/f5249d56-5795-4da1-b87c-3d38d61f10d0" />

<img width="525" height="64" alt="image" src="https://github.com/user-attachments/assets/3f92b915-993f-48d9-8db3-8067067cc99e" />



Verificar que el contenedor que se eliminó
<img width="1491" height="141" alt="image" src="https://github.com/user-attachments/assets/13be2307-fc61-41af-bf76-bddc0c6d6fcf" />


### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3** 
<img width="443" height="64" alt="image" src="https://github.com/user-attachments/assets/bfba3918-f293-4a2e-9c60-9e2381b1ae1d" />


Verificar que el contenedor que se eliminó
<img width="1406" height="113" alt="image" src="https://github.com/user-attachments/assets/b7fba35e-8f3d-42ee-af73-81f0aabac936" />


### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 
<img width="1504" height="750" alt="image" src="https://github.com/user-attachments/assets/d9f02b82-aeec-47e0-835a-7e0317ccb1e3" />
<img width="671" height="807" alt="image" src="https://github.com/user-attachments/assets/2c61115f-aa04-4b27-b420-19b6a7436ce6" />
<img width="785" height="781" alt="image" src="https://github.com/user-attachments/assets/2ea9b6f3-43ae-41a4-9af5-28d228a2a8f0" />
<img width="892" height="785" alt="image" src="https://github.com/user-attachments/assets/cd6e83a0-afa5-4fc4-9fd0-b2fccb29c819" />
<img width="1225" height="298" alt="image" src="https://github.com/user-attachments/assets/470bcbb8-f7d3-4be5-b242-ba3a9215b9e1" />





