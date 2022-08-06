# Obligatorio - Taller de Servidores Linux Matutino - 2022
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

5. Se instalan los Repositorios Extras de Fedora
6. Generamos la clave publica en el equipo Bastion con **ssh-keygen**
7. Ingresamos dicha clave en GitHub para tener acceso SSH.
8. 
