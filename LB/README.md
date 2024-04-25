### **BALANCEADOR DE CARGAS**

Es necesario crear en AWS una IP elastica y asociarla a la instancia destinada para el Balanceador de Cargas, ademas, es necesario tener un dominio, en el cual vamos a configurar el DNS y apuntar el registro A a nuestra direccion IP elastica.


```ssh
sudo apt-get update
sudo git clone https://github.com/DannyMelguizo/Reto3-Telematica.git
sudo cp -r Reto3-Telematica/LB/docker-compose.yml .
sudo cp -r Reto3-Telematica/LB/nginx.conf .
sudo apt-get install certbot
sudo apt-get install python3-certbot-nginx
```

Vamos a solicitar un certificado utilizando un agente, en este caso utilizaremos certbot, remplaza tu-dominio.tld por tu dominio, tld hace referencia a tu top-level-domain (.com, .co, .org, .xyz, .online, ...)

```ssh
sudo certbot --nginx certonly -d tu-dominio.tld -d www.tu-dominio.tld
```

Proporcione un correo electronico y acepte los terminos que se te muestran a continuacion. Ejecutar los siguientes comandos de igual manera cambiando tu-dominio.tld por tu dominio.

```ssh
sudo mkdir ssl
sudo -s
cp /etc/letsencrypt/live/tu-dominio.tld/* /home/ubuntu/ssl/
cp /etc/letsencrypt/options-ssl-nginx.conf /home/ubuntu/ssl/
cp /etc/letsencrypt/ssl-dhparams.pem /home/ubuntu/ssl/
exit
```

Vamos ahora a modificar el archivo nginx.conf para que quede apuntando a tu dominio, remplazando de nuevo, las palabras tu-dominio.tld por tu dominio y adicionalmente cambiaremos las variables IP1 e IP2 por las IP's privadas correspondientes a las dos intancias de AWS correspondientes a Wordpress

```ssh
sudo nano nginx.conf
```

Por ultimo creamos el contenedor.

```ssh
sudo docker compose up
```