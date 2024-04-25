### **NFS**

```ssh
sudo apt-get update
sudo apt-get install nfs-kernel-server -y
sudo mkdir -p /mnt/wordpress
sudo chown -R nobody:nogroup /mnt/wordpress
sudo chmod 777 /mnt/wordpress
```

Entra a la siguiente archivo y modifica el contenido para exponer la carpeta creada a traves de NFS.

```ssh
sudo nano /etc/exports
```

Agregar la siguiente linea en el archivo.

```ssh
/mnt/wordpress *(rw,sync,no_subtree_check)
```

Por ultimo reiniciar el servidor

```ssh
sudo exportfs -a
sudo systemctl restart nfs-kernel-server
```