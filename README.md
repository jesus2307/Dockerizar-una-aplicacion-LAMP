# iaw-practica-16
# 1 Práctica 16: «Dockerizar» una aplicación LAMP
En esta práctica tendremos que crear un archivo Dockerfile para crear una imagen Docker que contenga una aplicación web LAMP. Posteriormente deberá realizar la implantación del sitio web en Amazon Web Services (AWS) haciendo uso de contenedores Docker y de la herramienta Docker Compose.

## 1.1 Tareas a realizar
#### A continuación se describen muy brevemente algunas de las tareas que tendrá que realizar.

#### Crear una máquina virtual Amazon EC2.

#### Instalar y configurar Docker y Docker compose en la máquina virtual.

#### Crear un archivo Dockerfile para crear una imagen que contenga el servicio de Apache con la siguiente aplicación web:

https://github.com/josejuansanchez/iaw-practica-lamp
#### Crear un archivo docker-compose.yml para poder desplegar los servicios de Apache, MySQL y phpMyAdmin. Deberá utilizar las imágenes oficiales de Docker Hub.

#### Busque cuál es la dirección IP pública de su instancia y compruebe que puede acceder a los servicios de Apache y phpMyAdmin desde una navegador web.

DROP DATABASE IF EXISTS lamp_db;
CREATE DATABASE lamp_db CHARSET utf8mb4;
USE lamp_db;

CREATE TABLE users (
  id int(11) NOT NULL auto_increment,
  name varchar(100) NOT NULL,
  age int(3) NOT NULL,
  email varchar(100) NOT NULL,
  PRIMARY KEY (id)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

CREATE USER IF NOT EXISTS 'lamp_user'@'%';
SET PASSWORD FOR 'lamp_user'@'%' = 'lamp_password';
GRANT ALL PRIVILEGES ON lamp_db.* TO 'lamp_user'@'%';
