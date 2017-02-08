# Infrastructure

## Introducción

Para desarrollar este proyecto estamos usando Vagrant para administrar el ambiente de desarrollo y Ansible para manejar
todas las dependencias del proyecto. De esta manera, tenemos un ambiente de desarrollo muy similar al ambiente
productivo y podemos destruir y volver a crear ambientes (productivo o pruebas) de manera automatica gracias a Vagrant
y Ansible respectivamente.

## Requerimientos

Necesitas tener instalados los siguientes programas

* git
* ansible
* vagrant

## Instalación del ambiente de desarrollo

Lo pasos para tener un ambiente de desarrollo funcional son los siguientes

* Clonar este *repository*
* Entrar al directorio donde se acaba de clonar el proyecto.
* Ejecutar `vagrant plugin install vagrant-hostsupdater`
* Ahora,
  * Si no has clonado el projecto `filmoteca` anteriormente, ejecutar `git clone git@github.com:filmoteca/filmoteca.git project`
  * Si ya clonaste el proyecto filmoteca, copia toda la carpeta `filmoteca` a este projecto y renamobrala a `project`
* Ejecutar `vagrant up --provision` para "levantar" (crear) la máquina virtual. Te pedira la contraseña de administrador
en algún momento.
* Ahora la página es accessible desde `filmoteca.dev`

Con esto ya puedes modificar el proyecto dentro de la carpeta `project` como normalmente se haría.


## Usario por default de la zona administrativa

usuario: filmoteca@unam.mx

Password: filmoteca
