---
title: "Tercer día, instalación de docker y primeros pasos."
date: 2021-03-05T18:22:30+01:00
---

Hoy, empecé por instalar docker en mi máquina virtual debian favorita, ***intc*** . 
Todo se ha de hacer desde ***sudo, o desde root***. 


Lo comandos que he empleado, han sido los siguientes:

sudo passwd user1 (para aquellos que no saben cambiar la pass del user1  ;) )


***sudo apt-get update***

***sudo apt-get install apt-transport-https ca-certificates curl gnupg2 software-properties-common***


-----------

Tras instalar los paquetes, ***instalaremos docker con los siguientes comandos***:

curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add –


sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian buster stable"


Actualizamos el repositorio con nuestro famoso ***sudo apt-get update***.

Instalamos el motor de docker con > ***sudo apt-get install docker-ce docker-ce-cli containerd.io***


Y para comprobar su estado, el conocido "systemct status" nos valdrá.

-----------

Hoy, también, y para adelantar tarea, comenzaré con la ***creación***, ¡es muy simple!

Primero, ***crearemos un volumen de docker*** >>>>

docker volume create nombre_del_vol

Luego, ***pondremos en marcha el servidor***, gracias a nuestros amigos de poste.io >>>>

docker run -p 443:443 -e TZ=Europe/Andorra -v nombre_del_vol:/data --name "nombredelservidor" -h "nombredeldominio.algo" -t analogic/poste.io

De esta manera, ***ya tendremos, prácticamente, nuestro servidor de correo en marcha***.

----------

***Comandos básicos de docker***:

-docker ps -a > nos muestra un listado de nuestros volúmenes aka servidores.

-docker start contenedor_name > pondremos en marcha un contenedor detenido.

-docker stop > detendremos nuestro contenedor.

-docker rm > nos despediremos de nuestro contenedor, para siempre.