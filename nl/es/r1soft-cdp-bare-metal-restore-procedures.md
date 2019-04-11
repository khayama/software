---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft, restoring OS, restoring bare metal

subcollection: software

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Restauración del servidor desde una imagen de R1Soft
{: #restoring-your-server-from-an-r1soft-image}

Siga este procedimiento para realizar una restauración en {{site.data.keyword.BluVirtServers_full}} o {{site.data.keyword.BluBareMetServers_full}} público o privado. Siga este proceso si un error en el servidor deriva en una pérdida de datos o del sistema operativo. Este proceso restaura todos los bloques del sistema de archivos de los que se ha hecho copia de seguridad (incluido el sistema operativo y todos los archivos que no se han excluido de las copias de seguridad).

No utilice este proceso si desea restaurar un subconjunto de archivos. Para restaurar únicamente archivos, consulte la [wiki de R1Soft](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}.

## Restauración del dispositivo virtual
{: #restoring-your-virtual-device}

1. Pulse el dispositivo que desea restaurar en el [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Pulse el menú **Acciones** y seleccione **Arrancar desde imagen** para ver una lista de imágenes privadas.
3. Seleccione **Imágenes públicas** en el menú.
4. Elija la imagen de arranque del agente R1Soft adecuada para su versión de servidor R1Soft (serverbackup-centos-bootcd-agent.iso) y pulse el enlace **Arrancar desde esta imagen** de la derecha.
5. En la página **Detalles del servidor** correspondiente al servidor que va a restaurar, pulse **Acciones** > **Consola de KVM**.
6. Cuando la consola esté activa y se arranque la imagen, verá una pantalla del cargador de Debian con algunas opciones. Pulse la tecla Intro para arrancar desde la opción predeterminada.
7. Cuando se arranque el sistema operativo, escriba `netconfig` y pulse **Intro**.
8. Seleccione **Sí** para configurar la red.
9. Especifique los detalles de configuración de la red en los detalles del dispositivo en el portal de control.
10. Seleccione **Sí** cuando se le solicite que reinicie la red.
11. Si lo desea, escriba `passed root` para establecer una contraseña raíz para los inicios de sesión SSH y escriba service ssh start para permitir el inicio de sesión SSH. Este paso puede resultar útil si la consola de KVM es lenta.
12. Escriba `service cdp-agent restart` (este mandato inicia el agente de Tivoli Continuous Data Protection for Files si aún no se está ejecutando).

## Restauración del dispositivo nativo
{: #restoring-your-bare-metal-device}

1. Abra una incidencia en el [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} y solicite que arranquemos su servidor nativo en **modalidad de restauración nativa de R1Soft**.
2. En la página **Detalles del dispositivo** del servidor que va a restaurar, inicie una sesión en la **consola de KVM de IPMI**.
3. Cuando la consola esté activa y se arranque la imagen, verá una pantalla del cargador de Debian con algunas opciones. Pulse la tecla Intro para arrancar desde la opción predeterminada.
4. Cuando se arranque el sistema operativo, escriba `netconfig` y pulse **Intro**.
5. Seleccione **Sí** para configurar la red.
6. Especifique los detalles de configuración de la red en los detalles del dispositivo en el portal de control.
7. Seleccione **Sí** cuando se le solicite que reinicie la red.
8. Si lo desea, escriba `passed root` para establecer una contraseña raíz para los inicios de sesión SSH y escriba service ssh start para permitir el inicio de sesión SSH. Este paso puede resultar útil si la consola de KVM es lenta.
9. Escriba `service cdp-agent restart` (este mandato inicia el agente de Tivoli Continuous Data Protection for Files si aún no se está ejecutando).

## Selección del servidor R1Soft y de otros parámetros y opciones de restauración
{: #selecting-the-r1soft-server-and-other-restore-parameters-and-options}

Consulte la documentación de R1Soft sobre [Cómo realizar una restauración nativa](http://wiki.r1soft.com/display/ServerBackup/Perform+a+bare-metal+restore). Tiene que seleccionar el servidor que desea restaurar y el sistema de archivos, las tablas de porciones y otras opciones de restauración.
