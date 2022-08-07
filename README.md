# Obligatorio - Taller de Servidores Linux Matutino - 2022
## Docentes: Enrique Verdes - Sebastian Orrego
| ![LinuxLogo](https://github.com/heberdar/TSL/blob/main/images/Linux_logo.jpg) | ![RockyLogo](https://github.com/heberdar/TSL/blob/main/images/rocky-linux.jpg) |
| ----------- | ----------- |
## Repositorio para deploy de servicios, configuracion inicial

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
 
 | ![Ejemplo_Rocky8.5](image.jpg) | ![Ejemplo_Ubuntu22.04](image.jpg) |
| ----------- | ----------- |

5. Se crea el usuario **ansible** con password **ansible01** en ambos equipos
6. Terminada la instalacion de los dos equipos no olvide ** la Clonacion Completa al primer RockyLinux terminada su instalacion**

## Configuracion del Bastion Rocky

1. Se instalan los Repositorios Extras de Fedora **sudo dnf install epel-release**
2. Se instala Ansible **sudo dnf install ansible**
3. Se instala GIT **sudo dnf install git**
3. Mediante ventana SSH generamos la clave publica en el equipo Bastion con **"ssh-keygen"**
4. Utilizamos el siguente comando para ver el contenido de la SSH Key **cat .ssh/id_rsa.pub**
5. Dirigase a su cuenta de GitHub por navegador web en SSH and GPG Keys > New SSH Key, pega el contenido en el box
6. Ingresamos dicha clave en GitHub para tener acceso a nuestro Repositorio
7. Creamos la configuracion global de git con los siguientes comandos

- **git config --global user.name "Usuario"**
- **git config --global user.email "Usuario@dominio"**
- **git config --global user.color.ui true**
- **git config --global user.status auto**
- **git config --global user.branch auto**
- **git config --global core.editor vim**
- **git config --list**

8. Utilizamos el siguiente comando **git clone git@github.com:heberdar/OBL_TSL.git**
9. Esta el repositorio en nuestro equipo Bastion.
![ConfigGit](https://github.com/heberdar/OBL_TSL/blob/main/images/Configuraciones.png)

10. Realizada dicha configuracion procedemos a sincronizar el repositorio con Visual Studio Code
11. Configuramos la red en los Equipos destino para volcar nuestro Playbook **"Netplan - NetworkManager"**
12. Se llama al comando **"ssh-copy-id usuario@ip-destino"** obteniendo acceso a ese equipo en cuestion
13. Nos posicionamos en nuestro repositorio Git creamos un archivo **"host.ini"** donde esta la lista de equipos
15. Creamos nuestro primer Playbook llamado **"codigo.yaml"** el cual necesita estar relacionado con host.ini
