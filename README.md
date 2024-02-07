# Install_VPS_swapfile
configurar swapfile para vps gratuitos de 1 GB  1 CPU 

Actualización y configuración del VPS GRATIS

1- Actualizar el sistema como se indica.

sudo apt update && sudo apt upgrade

2- Con el comando «htop» se observa que el sistema no tiene swap (memoria de intercambio).

3- Crear el swapfile con los comando mostrados debajo.

sudo fallocate -l 1G /swapfile

4- Formatear el swapfile como se muestra.

sudo dd if=/dev/zero of=/swapfile bs=1024 count=1048576

5- Otorgar permisos al swapfile.

sudo chmod 600 /swapfile

6- Activar el swapfile en el sistema.

sudo mkswap /swapfile

7- Encender el swap.

sudo swapon /swapfile

8- Agregar el swapfile para que lo reconozca el sistema en el inicio. Para eso hay que editar el archivo /etc/fstab agregar las siguiente línea.

/swapfile swap swap defaults 0 0

9- Montar la partición de swap.

sudo mount -a

10- Verificar con htop que el swap esté activo en el sistema. Luego reiniciar el sistema y verificar si el swap se monta automáticamente.

Ya tenemos nuestro «VPS gratis / VPS free».
