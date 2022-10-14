author: Nombre del autor
summary: Resumen del CodeLab
id: identificador-unico-del-codelab
categories: codelab,markdown
environments: Web
status: Published
feedback link: Un enlace en el que los usuarios puedan darte feedback (quizás creando un issue en un repositorio de git)
analytics account: ID de Google Analytics

## configurado la BIOS para incrementar la seguridad del dispositivo 
Duration: 0:15:00

### 1.1 Breve descripcion De BIOS/UEFI

Bios  es el primer programa informático que se ejecuta al encender el ordenador se encarga de inicializar y probar todo el hardware del sistema informático, acutalmente
en los nuevos ordenadores con placas bases modernas utilizan UEFI que es casi excatamente igual que la UEFI solo que nos permite configurar mas funciones.
###
**Formas  de proteger tu BIOS**
  
- Contraseña de administrador de la BIOS.
- Contraseña de usuario de la BIOS o Contraseña de arranque del dispositivo.
- Permiso para el arranque desde dispositivos USB.
- Orden de arranque.
- Secure Boot.
</ul>

## Contraseña de Administrador y de usuario
Duration: 0:20:00

### 2.1 Contraseña de Administrador

La contraseña de administrador nos proporciona la seguridad y proteccion a la bios, nostros
tendremos acceso a cualquir parametro de configuracion de la bios y podremos modificarlo si queremos o no, si esta activada
la contraseña de administrador el usuario podra solo ver simplemente la configuracion pero nunca podra modificar ningun paramentro.(*Todo esto tambien depende la bios que sea*)
##
Para poder acceder a la UEFI/BIOS dependiendo del la placa base y del fabricante utilizaremos **F2** o **SUPR** sino alguna otra tecla, en mi caso es pulsando esas teclas.
##
Una vez dentro de mi UEFI en mi caso metere en el apartado de **Seguridad** que es donde se encuentra para poder configurar la contraseña de **administrador** y de **usuario**
##
Como podemos ver en la imagen de abajo yo ya tengo activado la contraseña del modo administrador, es recomendable poner una contraseña de minimo 8 caracteres para que sea muchisimo mas seguro.
##
![imagen](identificador-unico-del-codelab/img/administrador.jpeg)
##
##
Ahora en la siguiente podemos ver que cuando reiniciamos y entramos en la UEFI/BIOS nos aparece una ventana para que introduzcamos la contraseña.
##
![imagen](identificador-unico-del-codelab/img/contra1.jpeg)
##
listo y una vez dentro ya nos aparecera que tenemos el acceso como *administrador* y como he dicho anteriormente el administrador puede hacer cualquier cambio de configuracion de a bios
##
![imagen](identificador-unico-del-codelab/img/acceso.jpeg)
##
##
##

### 2.2 Contraseña de Usuario/Arranque

Ahora vamos a activar la contraseña del Usuario o contraseña de **arranque del dispositivo**, las pongo juntas porque en mi caso activando la de usuario tambien se activa la de arranque del dispositivo a que me quiero referir con esto. Cuando yo apague el reinicie el ordenador me va a aparecer la misma ventana para introducir la contraseña que nos permitira en este caso seguir con el arranque del equipo y poder acceder al windows.
##
##
![imagen](identificador-unico-del-codelab/img/usuario.jpeg)
##
##
Aqui tenemos la activacion de la contraseña del usuario y como bien indica mi UEFI/BiOS arriba en la descripcion 
"*Si solamente se estable la contraseña del usuario entonces es una contraseña de encendido y se debe especificar para arrancar o entrar en la configuracion, en la configuracion el usuario tendra derechos de administrativos*" lo que quiere decir con esto esque el si en mi **UEFI** solo tengo activado la contraseña de usuario me pedira una contraseña de arranque y tambien tendra los privilegios de administrador en la configuracion de la bios, por eso seria importante tener activado la de **administrador** y la de **usuario**
##
En mi caso si tengo activadas las dos contraseñas, el administrador es el unico que puede accceder a la configuracion de la BIOS/UEFI mientras tanto el usuario solo podro accedere al windows con la contraseña de arranque.
##
### 2.3 Contraseña de HDD
##
##
Antiguamente la contraseña de **arranque del dispostivos** estaba denominada como HDD password y en las placas antiguas se activaba de esta forma.
##
##
![imagen](identificador-unico-del-codelab/img/hdd.png)

## Arranque externos y Orden de arranque
Duration: 0:30:00

### 3.1 Arranques externos 

Cuando decimos arranques externos nos queremos referir a cuando arrancamos un sistema o un instalador atraves de algun dispositivos USB o tipo CD. Si no somos precavidos en ciertos aspectos cualquier persona que tenga acceso a nuestro ordenador gracias a un sistema live en un disco o en un USB podria intentar restablecer nuestra contraseña o cosas aun peores,
hoy en dia algunas **UEFI/BIOS** vienen sin poder Desabilitar el arranque por *USB*, por ejemplo en mi caso 
##
##
![imagen](identificador-unico-del-codelab/img/boot.jpeg)
##
##
E utilizado una **BIOS** virtual para mostrarles que en algunas BIOS un poco mas antiguas todavia sigue apareciendo el *USB BOOT* esto es lo que nos permite si queremos arrancar atraves de por medio de USB, si nostros conectaramos un USB con una ISO De windows o Ubuntu arrancaria el metodo de instalacion o podria intentar restaurar el sistema etc.
##
##
![imagen](identificador-unico-del-codelab/img/leonovo.png) 
##
##
Por lo menos en mi caso la unica solucion que yo veo posible ya que no tengo la opcion **USB boot** podria habilitar el *Secure boot* para windows pero esto mejor ya lo explico en la proxima seccion o sino tambien podria desactivar los puertos USB tambien es una forma segura que lo que hace esque los puertos USB del panel frontal queden desactivados completamente *(Tambien se pueden llegar a desactivar los de la placa)*.
##
##
### 3.2 Orden de arranque
##
##
El orden de arranque es muy importante tambien a la hora de hacer una configuracion segura a la BIOS/UEFI, imaginemos el caso que tenemos conectados al ordenador 4 discos duros,1 disquetera y 1 lectora de cd. si no tenemos bien configurado la orden de arranque se pondra a buscar en todo los dispositivos conectados al ordenador, la forma mas optima y mas segura es desactivar los dispositivos que no vamos a necesitar para que arranque.
##
##
![imagen](identificador-unico-del-codelab/img/orden.jpeg) 
##
##
En mi caso tengo 3 dispositivos, 1 M.2 y 2 SSD uno con un server PROXMOX instalado y otro para datos, y tengo como primer orden de arranque el windows que es mi sistema y los demas los tengo desactivado. porque tambien es seguro y es mucho mas rapido 
##
## Otras opciones de seguridad
Duration: 0:30:00
##
##
### Secure boot

El secure boot fue introducido por *Microsoft*, lo que hace es que no permite que se ejecuten software no firmado (linux, ubuntu o cualquiere otra distribucion, **"alguna distribucion de linux si se adaptaron"** ) o tambien todo lo que no sea windows
##
## 
![imagen](identificador-unico-del-codelab/img/secure.jpeg) 
##
esto nos ayuda para que nos no intenten ejecutar algun software malicioso.
##
##
### Wake on lan

El wake on lan es una opcion de la bios que nos permite encender el ordenador por red sin tener que darle al boton de encendido, ciertos programas te permite hacerlo atraves del movil o tambien desde apartos de domoticas como por ejemplo alexa. de por si no esta activado pero es recomendable tenerlo desactivado porque en enciertos casos se han detectado ataques ransomware que llegaban a apagar el ordenador
##
**para desactivarlo** 
![imagen](identificador-unico-del-codelab/img/wake.jpeg) 
##
En algunas BIOS/UEFI se llama **wake-on-lan** y en otras es en *power on by PCI-E* pero es la misma funcion
##
##
### TPM o Trusted platform module

sirve para proteger claves de cifrado por hardware y software. El tipo de claves que maneja y protege TPM, tanto la versión base como la 2.0, son claves de cifrado que almacenan credenciales nuestras, por lo que contienen información bastante
##
##
![imagen](identificador-unico-del-codelab/img/TPM.jpeg) 