# Obligatorio - Taller de Servidores Linux Matutino - 2022
## Docentes: Enrique Verdes - Sebastian Orrego
| ![LinuxLogo](https://github.com/heberdar/TSL/blob/main/images/Linux_logo.jpg) | ![RockyLogo](https://github.com/heberdar/TSL/blob/main/images/rocky-linux.jpg) |
| ----------- | ----------- |
## Repositorio para deploy de servicios 

1. Se inician tres equipos dos con Rocky Linux 8.5 y uno con Ubuntu Server 22.04
2. En todos los equipos se hacen diagramas LVM con discos de 20GB
3. A estos equipos se les configura la red con dos tarjetas modo NAT y VirtualHostOnly
4. Se crea un usuario **ansible** con password **ansible01**

| Tamaño | Ubicacion |
| ----------- | ----------- |
| 1GB | /home |
| 1GB | /boot |
| 2GB | /SWAP|
| 5GB | /var |
| 5GB | /opt |
| 5GB | /    |

5. Se instalan los Repositorios Extras de Fedora **"Epel-Release"**
6. Generamos la clave publica en el equipo Bastion con **"ssh-keygen"**
7. Ingresamos dicha clave en GitHub para tener acceso a nuestro Repositorio
8. Descargamos Git en el equipo Rocky Bastion y Ansible
9. Ahora seguimos con la configuracion global de Git
10. ![ConfigGit](https://github.com/heberdar/OBL_TSL/blob/main/images/Configuraciones.png)
11. Realizada dicha configuracion procedemos a sincronizar el repositorio con Visual Studio Code
12. Configuramos la red en los Equipos destino para volcar nuestro Playbook **"Netplan - NetworkManager"**
13. Se llama al comando **"ssh-copy-id usuario@ip-destino"** obteniendo acceso a ese equipo en cuestion
14. Nos posicionamos en nuestro repositorio Git creamos un archivo **"host.ini"** donde esta la lista de equipos
15. Creamos nuestro primer Playbook llamado **"codigo.yaml"** el cual necesita estar relacionado con host.ini
