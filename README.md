# iib-test-docker

DESCRIPCIÓN

Para poder ejecutar nuestra aplicación en un contenedor es necesario utilizar la siguiente imagen:

  docker pull ibmcom/iib

Para ejecutar nuestra aplicación es necesario tener el bar con nuestro servicio para entregarlo como argumento para iniciar el contenedor

docker run --name myNode -v IIB-Docker/bar:/tmp/BARs -e LICENSE=accept -e NODENAME=MYNODE -e SERVERNAME=MYSERVER -P ibmcom/iib

Los parámetros que se deben enviar al contenedor son los siguientes:

-v : para entregar nuestro directorio con 1 ó más bars como un volumen de docker, el cual será montado en /tmp/BARs del contenedor.

-e : indica las variables de ambientes necesarias y obligatorias para el funcionamiento de IIB
LICENSE = accept: para aceptar la licencia del producto IIB.
NODENAME = MYNODE: para indicar el nombre del Integration Node que se creará en el contenedor.
SERVERNAME =MYSERVERNAME: para indicar el nombre del Integration Server que se generará en el contenedor.
-P: para que los ports por default se expongan
