---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-27"
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Información de actualización de Microsoft Windows
IBM proporciona servicios de actualización del sistema operativo y software para entornos de Microsoft Windows Server de forma gratuita.

Todos los servicios de actualización de SoftLayer comparten las características siguientes:
* El tráfico de actualización se direcciona desde el servidor, por la VLAN privada, a la red de servicio privada
* El tráfico de actualización es parte de la banda ilimitada de la red privada y no reduce las asignaciones de ancho de banda público.
* Las velocidades de actualización son mayores que si se actualiza directamente desde los proveedores (velocidades de puertos mejoradas disponibles bajo demanda).
* Las actualizaciones están disponibles fácilmente durante los días de actualizaciones mundiales masivas críticas.
* En situaciones de emergencia, los puertos públicos pueden cerrarse mientras se siguen permitiendo las actualizaciones a través de la red privada
* Los servidores se preconfiguran para actualizarse automáticamente durante el despliegue con actualizaciones manuales disponibles bajo demanda.


Los servidores de actualización de SoftLayer están en la red de servicio privada con los siguientes identificadores de ubicación.

Microsoft: **wsus01.service.softlayer.com**

Pruebe siempre las actualizaciones de núcleo o de Service Pack antes de instalarlas en entornos de servidores de producción. En la sección de Preguntas Frecuentes del portal web del cliente podrá encontrar información técnica relacionada con el hardware específico, con el sistema operativo y con las aplicaciones desplegadas por IBM. Los ingenieros de IBM prueban continuamente las actualizaciones del kernel y las actualizaciones de Service Pack y la información relacionada (incluida la información sobre los controladores) para ayudar al proceso de actualización.


## WSUS - Windows Server Update Services

Los servidores de Microsoft Windows recogen automáticamente las actualizaciones de los servidores Windows Server Update Services (WSUS) locales.

Para los sistemas operativos Microsoft Windows, los servidores se configuran de manera predeterminada para descargar e instalar los parches tan pronto como están disponibles. El servidor se reinicia automáticamente si es necesario. Estas actualizaciones se realizan para ayudar a proteger los servidores de vulnerabilidades cruciales. Si prefiere planificar las actualizaciones de manera diferente, puede cambiar la planificación de actualizaciones mediante la característica **Actualizaciones de Windows** en el Panel de control.
