---
copyright:
  years: 1994, 2017
lastupdated: "2017-08-23"
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}



# Información de actualización de RedHat

IBM proporciona servicios de actualización del sistema operativo y software para entornos de RedHat de forma gratuita.

Todos los servicios de actualización de IBM comparten las características siguientes:
* El tráfico de actualización se direcciona desde el servidor (por la VLAN privada) a la red de servicio privada
* El tráfico de actualización es parte de la banda ilimitada de la red privada y no reduce las asignaciones de ancho de banda público.
* Las velocidades de actualización son mayores que si se actualiza directamente desde los proveedores (velocidades de puertos mejoradas disponibles bajo demanda).
* Las actualizaciones están disponibles fácilmente durante los días de actualizaciones mundiales masivas críticas.
* En situaciones de emergencia, los puertos públicos pueden cerrarse mientras se siguen permitiendo las actualizaciones a través de la red privada
* Los servidores se preconfiguran para actualizarse automáticamente durante el despliegue con actualizaciones manuales disponibles bajo demanda.

Los servidores de actualización de IBM están en la red de servicio privada con los siguientes identificadores de ubicación:

|Centro de datos|Dirección del host de servicio|
|---|---|
|Amsterdam|rhnproxyams0101.service.softlayer.com|
|Dallas|rhnproxy101.service.softlayer.com|
|Houston|rhnproxy421.service.softlayer.com|
|San José|rhnproxy501.service.softlayer.com|
|Seattle|rhnproxy201.service.softlayer.com|
|Singapur|rhnproxysng0101.service.softlayer.com|
|Washington D.C.|rhnproxy301.service.softlayer.com|

Pruebe siempre las actualizaciones de núcleo o de Service Pack antes de instalarlas en entornos de servidores de producción. En la sección de Preguntas Frecuentes del portal web del cliente podrá encontrar información técnica relacionada con el hardware específico, con el sistema operativo y con las aplicaciones desplegadas. IBM prueba continuamente las actualizaciones del kernel y las actualizaciones de Service Pack y la información relacionada (incluida la información sobre los controladores) para ayudar al proceso de actualización.

## Suscripción a RHN

Para sistemas operativos RedHat, IBM proporciona los servidores RedHat Network Satellite para instalar actualizaciones de seguridad críticas y no críticas.

La RedHat Network en SoftLayer incluye servidores RHN Satellite y Proxy. Cuando el servidor RedHat es suministrado, automáticamente se registra en el servidor de IBM RHN Satellite mediante el servidor proxy adecuado. Este registro permite utilizar mandatos **up2date** localmente en los servidores y extraer actualizaciones de la red de servicio privada.

Para garantizar la calidad de servicio empresarial y facilitar técnicas adecuadas de gestión de cambios, los servidores con sistema operativo RedHat se configuran de forma predeterminada para omitir las actualizaciones de kernel. Para asegurar la estabilidad del sistema, realice las actualizaciones del kernel manualmente después de completar las pruebas de regresión. IBM utiliza tecnologías de hardware avanzadas que requieren ediciones de kernel estables para obtener el rendimiento adecuado.
