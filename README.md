# **ST0263 Tópicos Especiales en Telemática**

# **Estudiante**: Daniel Melguizo Roldan, dmelguizor@eafit.edu.co

# **Profesor**: Juan Carlos Montoya Mendoza, jcmontoy@eafit.edu.co

*******

### **RETO 3**
Es un reto que consiste en el despligue de una aplicacion web desarrollada en wordpress, se propone desplegar cinco instancias en AWS, una instancia que funcionara como Balanceador de Cargas (LB), una instancia que funcionara como Base de Datos (DB), una instancia que funcionara como un NFS (NFS), y dos instancias que contendran la aplicacion de Wordpress (Wordpress).

Todas las maquinas se iniciaran con la siguiente configuracion:

* EC2
* Ubuntu: version 20.04 LTS
* Tipo de instancia: t2.micro
* Grupo de Seguridad con los siguientes puertos activos:
    * 80
    * 443
    * 3306
    * 2049
    * 22

*******

En cada carpeta encontraras los respectivos comandos para correr cada una de las instancias, cabe mencionar que cada instancia cuenta con docker y docker compose, recomiendo usar la guia oficial para instalar docker: https://docs.docker.com/engine/install/ubuntu/