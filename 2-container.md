# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine
# COMPLETAR
```
docker create --name srv-web nginx:alpine
```
<img width="945" height="105" alt="image" src="https://github.com/user-attachments/assets/ad4bbb78-e0d6-46ed-8255-52179c1a1662" />


Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world
# COMPLETAR

```
docker create hello-world
```

### Listar los contenedores ejecutándose o no

```
docker ps -a
```

<img width="856" height="259" alt="image" src="https://github.com/user-attachments/assets/37f6bccf-08e3-44f3-af08-84af305e2e11" />

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```

Iniciar el contenedor srv-web 
# COMPLETAR
```
docker start bc74fc9c75bf
```

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
# COMPLETAR
```
docker run --name srv-web2 nginx:alpine
```

**¿Qué sucede luego de la ejecución del comando?**
# COMPLETAR  
Se observa la ejecución del contenedor más no de la imagen. Es decir, se ve la ejecución del contenedor en primer plano

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine
# COMPLETAR
```
docker run -d --name srv-web3 nginx:alpine
```
<img width="1075" height="241" alt="image" src="https://github.com/user-attachments/assets/fa891690-2335-4e89-adc9-87176b0351ea" />


### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 
# COMPLETAR
```
docker rm tender_sinoussi
```

Verificar que el contenedor que se eliminó
# COMPLETAR
```
docker ps -a
```
<img width="1030" height="112" alt="image" src="https://github.com/user-attachments/assets/06cc36c3-a7c7-49f6-841a-1073dbc5d19b" />


### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3** 
# COMPLETAR
```
docker rm -f srv-web3
```

Verificar que el contenedor que se eliminó
# COMPLETAR
```
docker ps -a
```
<img width="1031" height="139" alt="image" src="https://github.com/user-attachments/assets/7560357a-9922-4b26-9a25-6d96c2646e39" />


### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 
# COMPLETAR

```
docker inspect srv-web
```

