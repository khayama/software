---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-25"

keywords: OS Reload, Operating System, cpsrvd email

subcollection: software

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:faq: data-hd-content-type='faq'}

# Preguntas frecuentes
{: #faqs}

## ¿Puede el sistema operativo (SO) cambiarse en el dispositivo?
{: #can-the-operating-system-os-be-changed-on-the-device-}

Puede cambiar el sistema operativo y el software que ha instalado recargando un sistema operativo <! --[SO](perform-os-reload-device.html){:new_window}-- >. Después de seleccionar el SO en el dispositivo, el sistema muestra un enlace a una página que le permite actualizar el software existente en el sistema. Desde esta página puede actualizar el sistema operativo, el Panel de control, los paquetes antivirus y el software de base de datos.

## ¿Proporcionan recargas de sistema operativo gratuitas?
{: #do-you-provide-complimentary-os-reloads-}

Las recargas automatizadas del sistema operativo son gratuitas, incluidas las recargas personalizadas como el cambio de sistema operativo, adición o eliminación de paneles de control, edición de particiones y otras opciones. Abra el Portal de clientes para obtener más información.

## ¿Cómo puedo realizar un seguimiento del estado de la recarga del sistema operativo?
{: #how-can-i-track-the-status-of-the-os-reload-}

En el Portal de clientes, bajo Hardware hay una sección Notas para cada uno de los servidores. La sección Notas incluye enlaces a información sobre en qué paso se encuentra la recarga y el tiempo estimado para concluir esa parte de la recarga.

## ¿Una recarga del sistema operativo puede borrar los discos secundarios?
{: #can-an-os-reload-erase-secondary-disks-}

Una recarga del sistema operativo sólo formatea el disco primario del sistema. Todos los demás discos se dejan como están. Esto funciona de la misma manera cuando se recarga desde una plantilla de imagen. Si la plantilla contiene más de un disco, sólo el disco primario se formatea. No se realizan cambios en el resto de los discos.

## ¿Por qué falla el correo electrónico de cpsrvd?
{: #why-did-my-cpsrvd-email-fail-}

En la mayoría de los casos, cuando se recibe un correo electrónico que indica **fallo de cpsrvd**, se envía inmediatamente después de un reinicio. Este error se produce cuando chkservd intenta validar el proceso cpsrvd. La validación falla porque el proceso no se ha iniciado.

Si recibe un correo electrónico del servicio chkservd, indicando que cpsrvd ha fallado, puede ignorar el mensaje en la mayoría de los casos. Sin embargo, si recibe 5 o más de estos mensajes seguidos, o si recibe más de 4 en un día después de reinicios, abra una incidencia de soporte.
