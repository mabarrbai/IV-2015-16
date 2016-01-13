# Asignatura: IV Grupo de Practicas Miercoles 8:30h a 10:30h
## Miguel Ángel García Villegas

# Ejercicios Tema 4

## Ejercicio 1.
### Instala LXC en tu versión de Linux favorita. Normalmente la versión en desarrollo, disponible tanto en GitHub como en el sitio web está bastante más avanzada; para evitar problemas sobre todo con las herramientas que vamos a ver más adelante, conviene que te instales la última versión y si es posible una igual o mayor a la 1.0.

Ejecutamos en el terminal: ```sudo apt-get install lxc```, se instalará la versión 1.0.8

![Versión1.0.8](https://www.dropbox.com/s/ddj9l05e5b10ojk/Captura%20de%20pantalla%20de%202016-01-07%2010%3A39%3A25.png?dl=1)




## Ejercicio 2.
### Comprobar qué interfaces puente se han creado y explicarlos.

Para crear contenedores deberemos también instalar varias
depencencias:
- [x] ```sudo apt-get install lxc-templates```
- [x] ```sudo apt-get install debootstrap```

Vamos a crear un contenedor  
```sudo lxc-create -t ubuntu -n contenedorU```

![Contenedor Debian](https://www.dropbox.com/s/7iqr67qsidhtyh9/ejer2.png?dl=1)

Vamos a iniciar el contenedor creado anteriormente. Ejecutamos en el terminal
```sudo lxc-start -n contenedorU```

Seguidamente tenemos que introducir ```ubuntu``` como usuario y contraseña.

![Contenedor Ubuntu](https://www.dropbox.com/s/mvpqv11t7lt6yzu/Captura%20de%20pantalla%20de%202016-01-07%2012%3A21%3A25.png?dl=1)

Ejecutando ifconfig en el contenedor, aquí podemos ver las interfaces que se han añadido.

![Ifconfig Contenedor Ubuntu](https://www.dropbox.com/s/3ozt3k3gsosb555/2.2.png?dl=1)

La interfaz ```eth0``` es para tener acceso a internet desde el contenedor, y ```lo``` es para la comunicación entre los contenedores.


## Ejercicio 3.

### 3.1 Crear y ejecutar un contenedor basado en Debian.

Vamos a crear un contenedor Debian. Ejecutamos en el terminal  
 ```sudo lxc-create -t debian -n contenedorD```

![Contenedor Debian](https://www.dropbox.com/s/o5gvgfsph4yihro/ejer3.2.png?dl=1)

### 3.2 Crear y ejecutar un contenedor basado en otra distribución, tal como Fedora. Nota En general, crear un contenedor basado en tu distribución y otro basado en otra que no sea la tuya. Fedora, al parecer, tiene problemas si estás en Ubuntu 13.04 o superior, así que en tal caso usa cualquier otra distro. Por ejemplo, Óscar Zafra ha logrado instalar Gentoo usando un script descargado desde su sitio, como indica en este comentario en el issue.

Verificamos que tenemos instalado yum, y nos disponemos a crear un contenedor centOS. Ejecutamos en el terminal  
```sudo lxc-create -t centos -n contenedorC```

![Contenedor CentOS](https://www.dropbox.com/s/ifwtpq6avt5zawm/3.2.png?dl=1)

Iniciamos el contenedor ejecutando en el terminal  
``` sudo lxc-start -n contenedorC ```

![Contenedor CentOS](https://www.dropbox.com/s/wfsnk189ik8n5uq/3.2.2.png?dl=1)


## Ejercicio 4.
### 4.1 Instalar lxc-webpanel y usarlo para arrancar, parar y visualizar las máquinas virtuales que se tengan instaladas.



### 4.2 Desde el panel restringir los recursos que pueden usar: CPU shares, CPUs que se pueden usar (en sistemas multinúcleo) o cantidad de memoria.

## Ejercicio 5.
### Comparar las prestaciones de un servidor web en una jaula y el mismo servidor en un contenedor. Usar nginx.

## Ejercicio 6.
### Instalar docker.

## Ejercicio 7.

### 7.1 Instalar a partir de docker una imagen alternativa de Ubuntu y alguna adicional, por ejemplo de CentOS.

### 7.2 Buscar e instalar una imagen que incluya MongoDB.

## Ejercicio 8.
### Crear un usuario propio e instalar nginx en el contenedor creado de esta forma.

## Ejercicio 9.
### Crear a partir del contenedor anterior una imagen persistente con commit.

## Ejercicio 10.
### Crear una imagen con las herramientas necesarias para el proyecto de la asignatura sobre un sistema operativo de tu elección.