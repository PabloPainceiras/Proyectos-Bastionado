author: Pablo Painceiras Martinez
summary: En este codelab quedan expuestos diferentes mecanismos de protección de BIOS/UEFI.
id: BIOS/UEFI
categories: codelab,markdown,BIOS,cybersecurity
environments: Web
status: Published
feedback link:
analytics account: ID de Google Analytics

## Proyecto-1.1-Bationado

En este proyecto vamos a describir como hacer una configuración segura de la BIOS/UEFI de un portátil HP.

¿Qué es la BIOS?

La BIOS (Basic Input/Output System, o Sistema Básico de Entrada/Salida) es un software que se ejecuta en un chip ubicado en la placa madre de una computadora. Es el primer software que se ejecuta al encender la máquina y su principal función es iniciar y probar el hardware del sistema, como el procesador, la memoria RAM, el disco duro, la tarjeta de vídeo, entre otros.

Antes de empezar tendremos que saber como entrar el la BIOS.

Para entrar en la BIOS del propio ordenador introducimos el siguiente comando en Windows Powershell en modo administrador. Esto reinicia el ordenador y al arrancar te introduce en la BIOS

shutdown /r /fw /t 0  

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/e58b3df3-5cd1-4e89-bb15-cbc24ac40878/08108424-0ef1-45af-9d18-37c94f51e281/Untitled.png)

Una vez al entrar en el menú principal de la BIOS presionamos la tecla F10 para entrar en la BIOS Setup

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/e58b3df3-5cd1-4e89-bb15-cbc24ac40878/aaeb598d-af24-412f-864c-f28164981919/Untitled.png)

Una vez entrado, nos movemos a la sección de “Security”, en donde podemos encontrar la contraseña del administrador (Administrator Password) y del arranque (Power-On Password).

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/e58b3df3-5cd1-4e89-bb15-cbc24ac40878/77b05bb6-4359-48b8-bc5e-f16d26aa0683/Untitled.png)

Nos situamos donde pone “Clear” en cada uno de los dos, unas vez encima, pulsamos “ENTER” y ponemos una contraseña.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/e58b3df3-5cd1-4e89-bb15-cbc24ac40878/0b973043-93d7-49de-91ea-86c1384e64c9/Untitled.png)

Luego nos movemos a “Boot Options”, en donde podemos encontrar las opciones de arranque.

Nos fijaremos en USB Boot, la cual deshabilitaremos para impedir que el sistema pueda hacer el arranque a través de un USB o dispositivo de memoria externa.

Por otro lado, en este caso ya esta deshabilitada la opción de arranque por una red, pero si esta activa la desactivaríamos

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/e58b3df3-5cd1-4e89-bb15-cbc24ac40878/04c9dde4-5ab1-46d5-bd52-00a1aa6b6e47/Untitled.png)

Una vez realizado las acciones anteriores se quedaran de la siguiente forma.

El orden de prioridades solo tendrá un tipo de arranque, ya que los demás están inactivos

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/e58b3df3-5cd1-4e89-bb15-cbc24ac40878/6f8daec5-4e01-4c6a-91ff-8ed5dc636dae/Untitled.png)

A continuación, habilitaremos el Secure Boot. De normal esta inaccesible, para poder acceder a él tendremos que restaurar las HP Factory Default Keys.

Una vez restauradas nos permitirá acceder al Secure Boot, el cual habilitaremos. Esto garantizar que el sistema arranque únicamente utilizando software que sea considerado confiable.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/e58b3df3-5cd1-4e89-bb15-cbc24ac40878/7921e7c8-467a-47a2-b9ab-3ce387e24072/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/e58b3df3-5cd1-4e89-bb15-cbc24ac40878/401436e2-0591-434b-aee6-8ebe4cff6970/Untitled.png)

A continuación volveremos a la pestaña “Security” en donde habilitaremos el TPM, esto nos proporcionara múltiples capacidades relacionadas con la seguridad, y su propósito es mejorar la integridad y la seguridad de un sistema informático. Para ello habilitaremos el TPM Device y el TPM State.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/e58b3df3-5cd1-4e89-bb15-cbc24ac40878/bc816a18-5b77-4bb3-b81b-3847a6dad42e/Untitled.png)
