---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft

subcollection: software

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Restauración de un servidor con R1Soft Tivoli Continuous Data Protection for Files

Siga este procedimiento para llevar a cabo una [restauración de servidor nativo](http://wiki.r1soft.com/display/CDP/Bare-Metal+Restore){:new_window} en un servidor virtual público o privado (VSI) de {{site.data.keyword.BluSoftlayer_full}} si se produce un error del servidor que deriva en una pérdida de datos o del sistema operativo.

Se restauran todos los bloques del sistema de archivos de los que se ha hecho copia de seguridad, incluido el sistema operativo y todos los archivos que no se han excluido de las copias de seguridad. No siga este procedimiento si desea restaurar un subconjunto de archivos. Para restaurar solo los archivos, consulte [http://wiki.r1soft.com/display/CDP/Restoring+Files](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}.

## Preparación del servidor de R1Soft Tivoli Continuous Data Protection for Files

1. Abra una ventana de navegador e inicie una sesión en el servidor de R1Soft Tivoli Continuous Data Protection for Files (encontrará la IP y las contraseñas de administrador en [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}).
2. Pulse **Puntos de recuperación** en el portal de gestión de R1Soft Tivoli Continuous Data Protection for Files.
3. Seleccione el **Servidor** que desea restaurar y el **Disco seguro** desde el que desea restaurar.
4. Localice el punto desde el que desea realizar la restauración en la lista de puntos de recuperación.
5. Pulse **Restauración nativa** (el icono de escudo) para iniciar el **Asistente de restauración**.
6. Pulse **Siguiente** en el **Asistente de restauración**.
7. Seleccione los sistemas de archivos que desea restaurar y pulse **Siguiente**.
8. Seleccione el host en el que desea realizar la restauración. Puede ser el host original u otro host. (Nota: en los pasos de este procedimiento se realiza la restauración en el mismo servidor.)
9. Pulse **Siguiente**.
10. Elija la configuración de almacenamiento que desea utilizar (utilice la que hay en el servidor o elija una en función de las copias de seguridad).
11. Seleccione las **Tablas de partición** que desea utilizar si ha optado por elegir el diseño de sistema de archivos.
12. Correlacione los sistemas de archivos con los dispositivos de bloque correctos (por ejemplo C:\ = /dev/sda1) y pulse **Siguiente**.
13. Seleccione las opciones de restauración, como por ejemplo **Rearrancar después de restauración**, **Comprobar sistema de archivos después de restauración** y pulse **Siguiente**.
14. Verifique sus opciones y pulse **Restaurar** o bien retroceda para cambiar sus opciones de restauración.

Aparece una ventana con el estado de la restauración actual.

## Preparación del dispositivo para la restauración

1. Abra una ventana de navegador y acceda a [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Pulse **Dispositivos**, **Lista de dispositivos** y seleccione el dispositivo que desea restaurar.
3. Pulse **Acciones** y seleccione **Arrancar desde imagen** para que se muestre una lista de imágenes privadas.
4. Seleccione **Imágenes públicas** en el menú.
4. Elija la imagen de arranque del agente R1Soft adecuada para su versión de servidor R1Soft (*r1soft-cdp-bootcd-server-4.0.0.iso*) y pulse **Arrancar desde esta imagen**.
5. Pulse **Acciones**, **Consola de KVM** en la página Detalles del dispositivo correspondiente al servidor que va a restaurar. Cuando la consola esté activa y se inicie la imagen, verá una pantalla del cargador de Debian con algunas opciones.
6. Pulse **Intro** para arrancar con la opción predeterminada.
7. Escriba netconfig en el indicador r1soft-recovery después de que se inicie el sistema operativo y pulse **Intro**.
8. Seleccione **Sí** para configurar la red.
9. Especifique los detalles de la configuración de red en la página **Detalles del dispositivo**.
10. Pulse **Sí** cuando se le solicite que reinicie la red.
11. **Opcional**: escriba `passwd root` para definir una contraseña raíz para los inicios de sesión SSH y escriba `service ssh` start para permitir el inicio de sesión SSH, lo que puede resultar útil si la consola de KVM tarda en responder.
12. Escriba `service cdp-agent restart`. Este mandato inicia el agente de Tivoli Continuous Data Protection for Files aunque no se esté ejecutando.
13. Seleccione **Arrancar desde imagen**. Aparece un marco en el que se indica que el dispositivo se ha configurado para que arranque desde la imagen *r1soft-cdp-bootcd-agent-4.0.0.iso*. Aparecerá una pregunta sobre descarga de la imagen y vuelta al arranque normal.
14. Pulse **Sí** y el servidor rearrancará desde el disco del sistema

El servidor ejecutará un proceso chkdsk o fsck para verificar el disco y es posible que se reinicie automáticamente. Una vez finalizado el proceso, el servidor o la VM estarán operativos con los datos restaurados desde el punto de restauración seleccionado.
