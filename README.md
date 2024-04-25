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

*******

```ssh
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install python3
sudo apt-get install python3-pip
sudo apt install docker.io
sudo docker run -d --hostname my-rabbit -p 15672:15672 -p 5672:5672 --name rabbit-server rabbitmq:3-management
sudo git clone https://github.com/DannyMelguizo/Telematica-Proyecto1.git
cd Telematica-Proyecto1
sudo python3 -m pip install -r requirements.txt
```