---
copyright:
  years: 2017, 2018
lastupdated: "2018-02-08"

keywords: software

subcollection: software
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Acerca del software
{: #about-software}

{{site.data.keyword.BluSoftlayer_full}} tiene relaciones estratégicas con proveedores para proporcionar licencias mensuales de software compatible con 32 y 64 bits.  Cuando realiza un pedido de un dispositivo, selecciona el tipo de sistema operativo y software para el mismo. Puede añadir más software al dispositivo dentro de {{site.data.keyword.slportal_full}} y cambiar a otro sistema operativo volviendo a cargar el SO en el dispositivo existente. El sistema automatizado de IBM proporciona software en el servidor respetando las directrices sobre mejores prácticas de cada proveedor para garantizar la máxima estabilidad y disponibilidad.

Consulte la siguiente lista del software al que se da soporte actualmente: [Software de servidor de nube ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud-computing/bluemix/node/153){: new_window}.

Si necesita software que actualmente no recibe soporte, utilice el acceso raíz al servidor para instalar y configurar su propia versión de ese software.  Para volver a una versión soportada en su dispositivo, vuelva a cargar el sistema operativo.

IBM incluye instrucciones o consideraciones para utilizar productos en el entorno de {{site.data.keyword.BluSoftlayer_notm}}. Para ver la documentación del software, consulte la documentación del proveedor que desarrolla el software.

## Sistemas operativos soportados para servidores virtuales de IBM Cloud
{: #supported-operating-systems-for-ibm-cloud-virtual-servers}

Los servidores virtuales de IBM Cloud dan soporte a los siguientes sistemas operativos.

- Cent OS 6 (PV)
- Cent OS 7 (HVM)
- Debian 7 (PV)
- Debian 8 (HVM)
- Debian 9 (HVM)
- RHEL 6 (PV)
- RHEL 7 (HVM)
- Ubuntu 14 (PV/HVM) utiliza de forma predeterminada la modalidad de arranque PV, pero puede cambiar a la modalidad de arranque HVM
- Ubuntu 16 (PV/HVM) utiliza de forma predeterminada la modalidad de arranque PV, pero puede cambiar a la modalidad de arranque HVM
- Windows 2012 (HVM)
- Windows 2012 R2 (HVM)
- Windows 2016 (HVM)

**Nota:** los tamaños de los discos de arranque varían en función del sistema operativo:<br>  
Linux OS da soporte a 25 GB y a 100 GB.
Windows solo da soporte a 100 GB.

Para obtener más información sobre cómo cambiar entre las modalidades de arranque PV y HVM, consulte los siguientes enlaces:
* [Modalidades de arranque soportadas de invitado virtual ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://sldn.softlayer.com/reference/services/SoftLayer_Virtual_Guest_Block_Device_Template_Group/getSupportedBootModes){: new_window}
* [Opción Añadir modalidad de arranque ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/softlayer/softlayer-python/pull/936/files/09c35a9595651d66f3e117a055efe585745ba2b3){: new_window}
