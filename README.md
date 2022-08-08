# Obligatorio - Taller de Servidores Linux Matutino - 2022
## Docentes: Enrique Verdes - Sebastian Orrego
| ![LinuxLogo](https://github.com/heberdar/TSL/blob/main/images/Linux_logo.jpg) | ![RockyLogo](https://github.com/heberdar/TSL/blob/main/images/rocky-linux.jpg) |
| ----------- | ----------- |
## Repositorio para deploy de servicios, configuración inicial

1. Se crean dos equipos uno con Rocky Linux 8.5 y uno con Ubuntu Server 22.04.
2. Se agregan dos tarjetas de Red una en Modo NAT y otra en Modo Virtual Host Only
3. Recordar que para continuar con la instalacion en UBUNTU es necesario desactivar la red.
4. Se particionan los discos con el siguiente diagrama LVM.


| Tamaño | Ubicacion | 
| ----------- | ----------- |
| 1GB | /home |
| 1GB | /boot |
| 2GB | /SWAP|
| 5GB | /var |
| 5GB | /opt |
| 5GB | /    |
|![Ejemplo_Rocky8.5](https://github.com/heberdar/OBL_TSL/blob/main/images/rocky8_LVM.JPG) | ![Ejemplo_Ubuntu22.04](image.jpg) |

5. Se crea el usuario **ansible** con password **ansible01** en ambos equipos
6. Terminada la instalacion de los dos equipos no olvide ** la Clonacion Completa al primer RockyLinux terminada su instalacion**

## Configuración Ubuntu Server

1. Configure la red con netplan escriba el siguiente comando **sudo vim /etc/netplan/00-installer-config.yaml**
Modifique los valores respetando los espacios y caracteres
![netplan_config](image.jpg)
Despues de finalizada la modificacion **sudo netplan apply** ya tiene conectividad.

## Configuración del Bastion Rocky

1. Se instalan los Repositorios Extras de Fedora **sudo dnf install epel-release**
2. Se instala Ansible **sudo dnf install ansible**
3. Se instala GIT **sudo dnf install git**
4. Mediante ventana SSH generamos la clave pública en el equipo Bastion con **ssh-keygen**
5. Utilizamos el siguente comando para ver el contenido de la SSH Key **cat .ssh/id_rsa.pub**
6. Dirigase a su cuenta de GitHub por navegador web en SSH and GPG Keys > New SSH Key, pega el contenido en el box
7. Ingresamos dicha clave en GitHub para tener acceso a nuestro Repositorio



## Integracion con Visual Studio

1. Recordar que en el equipo bastion debe tener instalado el paquete tar **sudo dnf install tar**
2. En extensiones (imagen del cubo) Instalar SSH y Ansible
3. Crear un archivo de conexion SSH, columna izquierda anteultima opcion
4. Necesita elegir tipo de sistema operativo y escribir las credenciales de acceso, se continuan instalando otros paquetes de Visual.
5. En la ventana SSH de Visual escriba esta configuración con los siguientes comandos

- **git config --global user.name "Usuario"**
- **git config --global user.email "Usuario@dominio"**
- **git config --global user.color.ui true**
- **git config --global user.status auto**
- **git config --global user.branch auto**
- **git config --global core.editor vim**
- **git config --list**
- ![ConfigGit](https://github.com/heberdar/OBL_TSL/blob/main/images/Configuraciones.png)

6. Utilizamos el siguiente comando **git clone git@github.com:heberdar/OBL_TSL.git**
7. El repositorio se encuentra en nuestro equipo Bastion.



12. Se llama al comando **"ssh-copy-id usuario@ip-destino"** obteniendo acceso a ese equipo en cuestion
