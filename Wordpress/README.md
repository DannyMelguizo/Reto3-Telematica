### **WORDPRESS**

```ssh
sudo apt-get update
sudo apt-get install nfs-common -y
sudo mkdir -p /mnt/wordpress
sudo git clone https://github.com/DannyMelguizo/Reto3-Telematica.git
sudo cp -r Reto3-Telematica/Wordpress/docker-compose.yml .
```

Remplazar en el archivo docker-compose.yml la variable WORDPRESS_DB_HOST por la IP privada de la instancia de AWS correspondiente a la base de datos.

```ssh
sudo nano docker-compose.yml
```

Configurar el NFS, remplazando ip_nfs por la IP privada de la instancia de AWS correspondiente al servidor NFS.

```ssh
sudo mount ip_nfs:/mnt/wordpress /mnt/wordpress
sudo docker compose up
```

