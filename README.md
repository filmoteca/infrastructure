# Infrastructure

## Introducción

Para desarrollar este proyecto estamos usando Vagrant para administrar el ambiente de desarrollo y Ansible para manejar
todas las dependencias y configuración del proyecto. De esta manera, tenemos un ambiente de desarrollo muy similar al ambiente
productivo y podemos destruir y volver a crear ambientes (productivo o pruebas) de manera automatica gracias a Vagrant
y Ansible.

Una de las responsabilidades de Ansible es administrar dependencias de los servidores, por ejemplo, installar php y mysql,
y configurarlo de manera adecuada, por ejemplo, crear el virtual host para el web server.

## Requerimientos

Necesitas tener instalados los siguientes programas

* git
* ansible
* vagrant
* virtual box

## Instalación del ambiente de desarrollo

Lo pasos para tener un ambiente de desarrollo funcional son los siguientes

* Clonar este *repository*
* Entrar al directorio donde se acaba de clonar el proyecto.
* Ejecutar `vagrant plugin install vagrant-hostsupdater`
* Ahora,
  * Si no has clonado el projecto `filmoteca` anteriormente, ejecutar `git clone git@github.com:filmoteca/filmoteca.git project`
  * Si ya clonaste el proyecto filmoteca, copia toda la carpeta `filmoteca` a este projecto y renamobrala a `project`
    de tal manera que quede `infrastructure/project`.
* Ejecutar `vagrant up --provision` para "levantar" (crear) la máquina virtual. Te pedira la tu contraseña de administrador
de la computadora donde se corrio el comando.
* Ahora la página es accessible desde `filmoteca.dev`

Con esto ya puedes modificar el proyecto dentro de la carpeta `project` como normalmente se haría.


## Usario por default de la zona administrativa

usuario: filmoteca@unam.mx

Password: filmoteca

## Provisionar otros ambientes

Para provisionar el ambiente de producción se debe correr los siguientes commandos

#### Producción
```
ansible-playbook webservers.yml mysql.yml -i inventaries/production/hosts.yml
```

#### Staging
```
ansible-playbook webservers.yml mysql.yml -i inventaries/stating/hosts.yml
```

#### Local
```
ansible-playbook webservers.yml mysql.yml -i inventaries/local/hosts.yml
```
