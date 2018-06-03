## Yoltlabot: Telegram Bot para notificaciones Slurm
---
Yoltlabot es un programa diseñado para la entrega de alertas y diversas estadisticas de un centro de computo. Este funciona con un framework llamado Telepot y brinda notificaciones de estadisticas entregadas por SLURM por medio de la aplicacion de mensajeria Telegram.

### Prerequisitos
---
* Contar con [python 2.7](https://www.python.org/)
* Instalar el framework [Telepot](https://github.com/nickoala/telepot)
* Crear un [bot](https://core.telegram.org/bots) en [Telegram](https://telegram.org/) y contar con su correspondiente [TOKEN](https://core.telegram.org/bots)
* Contar con acceso a SLURM y para notificaciones de LUSTRE tener acceso Root

### Organización del codigo
---
Yoltla bot fue dieñado en dos partes: la primera es el codigo generado en Python y la segunda es un Script en Bash que contiene todas las consultas que se realizan para enviar las notificaciones.

*yoltlabot - Directorio que contiene el codigo Python
*ordenes - Directorio que las intrucciones en Bash

### Instalacion
---
Yoltlabot no tiene una instalación como tal ni necesita un directorio específico, lo único necesario es que tanto yoltlabot como ordenes se encuentren en el mismo directorio y que se encuentre con los prerequisitos de funcionamiento.

### Ejecución
---
Para ejecutar, ingrese:
```bash
./yoltlabot TOKEN
```
Donde **TOKEN** es el "TOKEN" del bot creado y por el cual se van a enviar las notificaciones
### Comandos
---
Yoltlabot entrega notificaciones sin la necesidad de enviar un mensaje, pero opcionalmente se pueden obtener estadisticas enviando ciertos comandos:

```bash
/sinfo
```
Muestra los nodos que estan en estado Draining o Drained ya sea por swap, oom o gpu
![alt text](img/sinfo.png "/sinfo")
```bash
/status
```
Muestra la estadistica de cuantas tareas se encuentran corriendo, en espera o en modo idle
![alt text](img/status.png "/status")
```bash
/dstatus
```
Muestra un detallado de las tareas por partición, muestra las tareas pendientes (PD) y las tareas que se están ejecutando (R), solo aparecen las particiones que se encuentran con alguno de estos parametros.
![alt text](img/dstatus.png "/dstatus")
