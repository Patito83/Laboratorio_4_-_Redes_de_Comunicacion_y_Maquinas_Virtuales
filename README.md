# Laboratorio 4 - Redes de Comunicación y Máquinas Virtuales
## Desarollo de Redes de Comunicación
### Generar Detección y Software
Para este apartado se realizo el siguiente codigo con el cual ajustamos la detección del dispositivo y los puesrtos seriales: **dmesg | grep tty, ls /dev/ttyUSB*sudo apt install usbutilslsusb** 

<img width="793" height="154" alt="Captura desde 2025-09-26 07-09-41" src="https://github.com/user-attachments/assets/e868481f-2bcd-48d7-882f-5479f6169e57" />

### Configuración de Ip's
Luego se configuraron las ip's de todas pas pc's que se usarian, en este caso se usaron dos potatiles y un computador gestionado por los ETM's de la universidad y tambien una raspberry. En las siguientes imagenes se vizualisaran las conexiones.

<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/0261ebbd-d4f7-43fc-998a-8fd23dd42897" />

<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/c0cb734d-686a-4681-8f7f-e97e775dc34f" />

<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/8850e11e-ab10-4f62-9190-8c36009f27af" />

<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/b7de0cbd-e00f-481a-9d10-4fd609e4685a" />

Luego se descargo el software Mimicon con el cual se realizo la configuración serial y el analisis de cada Ip.

**Apartado de verifiación de conexiones**

<img width="1081" height="233" alt="image" src="https://github.com/user-attachments/assets/532f8a90-59c5-4319-b696-6d8bf93bb81d" />

<img width="1081" height="168" alt="image" src="https://github.com/user-attachments/assets/7f9d90c3-e5ce-4238-a55d-0f8415983a89" />

<img width="1081" height="168" alt="image" src="https://github.com/user-attachments/assets/7a04158e-f296-42b3-94e4-2ed85016e560" />

<img width="1081" height="168" alt="image" src="https://github.com/user-attachments/assets/70e378a2-1b5f-4f3c-a844-f2154963e5e5" />

<img width="1081" height="168" alt="image" src="https://github.com/user-attachments/assets/76cbc374-140b-40f4-8d95-e6b927e34a67" />

## Maquinas Virtuales 

### Instalación de QEMU
Para trabajar con maquinas virtuales se uso QEMU, el cual nos ayudara a tener varias maquinas virtuales con las cuales trabajar. Para instalarlo sigue los siguientes pasos.

- En la terminal de Ubuntu, actualiza el sistema y descarga QEMU.
 **sudo apt update && sudo apt upgrade -y** y **sudo apt install qemu qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils virt-manager -y**
   Recuerda verificar la instalación de QEMU con **qemu-system-x86_64 --version**

<img width="599" height="51" alt="Captura desde 2025-10-17 16-50-36" src="https://github.com/user-attachments/assets/d554e9a0-8722-417f-b674-ecb692af8571" />

### Instalación de Maquinas Virtuales 
La varios casos de instalación de un sistema es igual, en este caso el ejemplo sera para Ubuntu. Lo primero que debes hacer es encontrar el ISO del sistema Operativo deseado y crearlo en una carpeta **wget https://releases.ubuntu.com/22.04/ubuntu-22.04.4-desktop-amd64.iso**

<img width="1500" height="199" alt="Captura desde 2025-10-17 16-57-23" src="https://github.com/user-attachments/assets/dd586373-3c20-4503-ad4d-a76f6dcd530d" />

- Luego debes gestionarlo mediante QEMU y darle una cantidad de recursos al sistema ISO para liego si realizar la instalación. **qemu-img create -f qcow2 ubuntu.qcow2 10G** y lego instalar con **qemu-system-x86_64 -hda ubuntu.qcow2 -cdrom ubuntu-22.04.4-desktop-amd64.iso -boot d -m 4096**

<img width="1465" height="123" alt="Captura desde 2025-10-17 16-18-31" src="https://github.com/user-attachments/assets/29ac9dc7-df53-462f-be11-fa532a27c193" />

- Se te desplegara una pantalla con el cual ya podras instalar tu sistema.

<img width="748" height="492" alt="Captura desde 2025-10-17 16-19-45" src="https://github.com/user-attachments/assets/e893cfa0-385d-4f81-8e1a-7ec70b6920d2" />

<img width="1308" height="892" alt="Captura desde 2025-10-17 16-22-05" src="https://github.com/user-attachments/assets/ec9ed419-1640-4805-b34d-6a8d408a2bb3" />


