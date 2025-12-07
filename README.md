Trabajo Practico : Administracion de sistemas Linux
Materia: Arquitectura y Sistemas Operativos.
Integrantes:
* Breme Fernando (Administrador).
* Acuña Liam (Desarrollador).
* Joel Acosta (Operador).

Contenido del proyecto: Este proyecto fue diseñado con el fin de gestionar y administrar un entorno de trabajo colaborativo Virtualizado utilizando Vagrant y VirtualBox
sobre una distribucion Ubuntu 22.04 LTS. El principal objetivo fue simular un escenario de administracion de servidores. Gestionando: Archivos, permisos, grupos y entornos de trabajo,
almacenamiento logico -LVM-, y utilizacion de contenedores docker.
Bonus: Implementacion de servidor LAMP -LINUX, APACHE, MYSQL, PHP-

Proceso:
1_ Automatizacion de la VM.
  Se creo el vagrantfile con el fin de automatizar la inicializacion de la Maquina Virtual a traves de VirtualBox. Ademas,
Nos aseguramos de Instalar todas las dependencias necesarias para el desarrollo de dicho Proyecto.
2_ Configuracion Inicial y Repositorio.
  Se llevo a cabo la creacion de un repositorio publico en github, el cual fue clonado en cada VM de los integrantes del grupo.
  Posteriormente Fuimos analizando el proyecto en cuestion, con el fin de resolver los pasos a seguir y las indicaciones para cada integrante del equipo.
3_ Fastfetch (Colaborativo).
  Se Guardo en el archivo system_info.txt el fastfetch de cada uno de los miembros del equipo, ademas de la IP de cada VM en caso de ser requerida posteriormente.
4_Gestion de Permisos (Individual + colaborativo).
  *individual: en esta etapa, cada integrante creo un espacio de trabajo persional, generando archivo privado -permisos 600- y publico -permisos 644-
  *Colaborativo: Se crearon 3 usuarios de prueba, a la vez, un grupo llamado equipotrabajo -Permisos 770- con el fin de simular un entorno real de trabajo, donde el grupo de trabajo tiene el mismo nivel de permisos que el usuario dueño.
  Todo Fue documentado dentro del archivo usuarios.txt y verificacion_permisos.txt
5_Gestion de LVM -Logical Volume Manager-
  Se siguieron diferentes directrices:
    * pvcreate : Creacion de physical Volume
    * vgcreate : Creacion de Volume Group
    * lvcreate : Creacion de Logical Volume
    * Formateo .ext4
    * Creacion de punto de montaje y ejecucion
    * Creacion de fstab para montaje automatico.
  Al finalizar el proceso, se Creo el archivo de lvm (individual) con la documentacion necesaria de todos los escaneos de      lvm y diferencia entre disco con y sin LVM montado.
6_Gestion de archivos y directorios.
  Se creo una mini estructura con la inicializacion de 10 archivos, para luego ir moviendolos a los subdirectorios que         indican el status de cada archivo, como tipo de proyecto. Todo esto dentro del disco montado con LVM.
  Se documento cada uno de los subdirectorios con el contenido en cada uno de ellos.
7_Contenedores y monitoreo con docker compose (Colaborativo).
  Se investigo el proposito y formato del archivo docker-compose.yml
  Posteriormente, se desarrollo dicho archivo, configurando variables de entorno y networking en cada uno de los servicios     incorporados.
  Se utilizo docker-compose logs con el fin de encontrar los errores intencionales en el archivo y solucionar los errores de   ejecucion de algunos de los servicios incorporados. Los que se encontraron errores fueron:
    - Grafana
    - Redis
    - Prometheus.yml 'nginx'
  Luego de resueltos dichos errores, se ejecuto docker ps para revisar que todos los servicios se encuentren en estado         activo.
  Se Ingreso a grafana con la IP de la VM para configurar los datasource -Prometheus y Loki- y configurar un dashboard de      Prometheus.
  Luego fuimos al sitio de prometheus que se encontraba en el puerto 9090, el cual notamos que habia 1 target, perteneciente   a NGINX, que indicaba DOWN, debido a que Nginx por defecto no expone metricas. Por lo que encontramos 2 opciones:            desabilitar Nginx o utilizar Nginx Prometheus Exporter, una herramienta que funciona como intermediario para poder           graficar las metricas de Nginx con el sistema de monitorizacion Prometheus.
  Por ultimo, se realizo la documentacion requerida, tanto en formato texto, como las screenshots de los datasource de         grafana, su dashboard, y los targets de prometheus.
8_ BONUS: Servidor LAMP.
  *Se instalaron los componentes del stack LAMP
  *Configuracion de MySQL
  *Configuracion de Apache
  *Creacion de sitio web con un formato sencillo de HTML y codigo CSS incorporado.
  *Creacion de archivo de prueba PHP
  *Creacion de archivo de conexion a MySQL con la informacion de servidor, usuario y db.
  *Configuracion de permisos
  *Verificacion de status de servicios -Apache2 y MySQL-
  *Documentacion Requerida.

CONCLUSION DEL PROYECTO: Mas alla de seguir lineas de comando para realizar cada una de las tareas, el proceso nos fue mostrando que dicho proyecto no era tan dificil como se presentia antes de empezar, incluso con el vagrantfile, y al final nos permitio ser mucho mas agilidosos dentro de la VM y su consola.
 Logramos incorporar conocimientos tanto de LVM, Docker, servidores web, conexion con db, el manejo colaborativo a traves de  github con los comandos git (add, commit, push, pull) resolviendo divergencias en la rama principal del proyecto.
 Al final del dia, este proyecto, nos permitio entender mucho mas toda la teoria Vista en durante el cuatrimestre en la materia y tuvimos la posibilidad de poner en practica todos los conocimientos que fuimos incorporando. Ademas de aprender y adptarnos al trabajo en equipo de forma remota, enseñandonos unos a otros, y gestionar el uso de nuestro tiempo compartido con el fin de hacer un proyecto largo y complicado, en algo mucho mas sencillo e intuitivo.
 
