---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-27"

keywords: Microsoft Windows Update, software update services

subcollection: software

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Información de actualización de Microsoft Windows
{: #microsoft-windows-update-information}

IBM proporciona servicios de actualización del sistema operativo y software para entornos de Microsoft Windows Server de forma gratuita.

Todos los servicios de actualización de {{site.data.keyword.Bluemix_notm}} comparten las características siguientes:
* El tráfico de actualización se direcciona desde el servidor (por la VLAN privada) a la red de servicio privada
* El tráfico de actualización forma parte del ancho banda ilimitado de la red privada. Este tráfico no reduce las asignaciones de ancho de banda público.
* Las velocidades de actualización son mayores que si se actualiza directamente desde los proveedores (velocidades de puertos mejoradas disponibles bajo demanda).
* Las actualizaciones están disponibles fácilmente durante los días de actualizaciones mundiales masivas críticas.
* En situaciones de emergencia, los puertos públicos pueden cerrarse mientras se siguen permitiendo las actualizaciones a través de la red privada
* Los servidores se preconfiguran para actualizarse automáticamente durante el despliegue con actualizaciones manuales disponibles bajo demanda.


Los servidores de actualización de {{site.data.keyword.Bluemix_notm}} están en la red de servicio privada con los siguientes identificadores de ubicación.

Microsoft, **wsus01.service.softlayer.com**

Pruebe siempre las actualizaciones de núcleo o de Service Pack antes de instalarlas en entornos de servidores de producción. En la sección de Preguntas frecuentes o de controladores del portal de control encontrará información técnica relacionada con el hardware específico, con el sistema operativo y con las aplicaciones desplegadas por IBM. IBM prueba continuamente las actualizaciones del kernel y las actualizaciones de Service Pack y la información relacionada (incluida la información sobre los controladores) para ayudar al proceso de actualización.


## WSUS, Windows Server Update Services
{: #wsus-windows-server-update-services}

En muchos casos, los servidores de Microsoft Windows recogen automáticamente las actualizaciones de los servidores Windows Server Update Services (WSUS) locales. Sin embargo, si su servidor se suministra con una imagen habilitada para cloud-init, es posible que tenga que actualizar manualmente el registro de Windows para que utilice servidores {{site.data.keyword.cloud_notm}} Windows Server Update Services (WSUS) locales en lugar de los servidores Microsoft WSUS predeterminados.

Si solicita un servidor virtual con un sistema operativo Windows Server sin ningún complemento, como más software, scripts post suministro o supervisión avanzada, es probable que el servidor se suministre con una imagen de cloud-init. Para obtener más información sobre cómo actualizar el registro de modo que apunte a servidores {{site.data.keyword.cloud_notm}} WSUS, consulte [Actualización de una instancia para que utilice un servidor WSUS local](/docs/infrastructure/software?topic=software-updating-an-instance-to-use-a-local-wsus-server).

Para los sistemas operativos Microsoft Windows, los servidores se configuran de manera predeterminada para descargar e instalar los parches tan pronto como están disponibles. El servidor se reinicia automáticamente si es necesario. Las actualizaciones se realizan para ayudar a proteger los servidores ante vulnerabilidades cruciales. Si prefiere planificar las actualizaciones de otra manera, puede cambiar la planificación de actualizaciones mediante la característica **Actualizaciones de Windows** en el panel de control.
