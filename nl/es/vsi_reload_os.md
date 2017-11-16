---



copyright:
  years: 2017
lastupdated: "2017-09-25"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

#  Recarga de un sistema operativo
Puede recargar el sistema operativo (SO) de un dispositivo en cualquier momento para restaurar un dispositivo a su estado de trabajo original, o para reconfigurar un dispositivo con software diferente. Una recarga de SO elimina todos los datos del dispositivo y aplica una configuración "como nuevo", tal como se especifica durante el proceso de configuración de la recarga del sistema operativo. Dado que las recargas del sistema operativo borran todos los datos del dispositivo, si no se ha realizado una copia de seguridad de los datos antes de la recarga, éstos se suprimirán permanentemente y no podrán ser recuperados.
{:shortdesc}

**Importante:** Si desea conservar sus datos, haga una copia de seguridad de todos los datos antes de llevar a cabo una recarga del sistema operativo.

## Recarga del sistema operativo
1. De la **Lista de dispositivos**, pulse el servidor que necesita una recarga del sistema operativo para mostrar la página Detalles del dispositivo.
2. Del menú **Acciones**, seleccione **Recarga del sistema operativo**.
3. Determine si desea recargar la configuración existente o cargar el dispositivo con una nueva configuración.

   <table>
   <CAPTION>Tabla 1. Opciones de recarga de sistema operativo</CAPTION>
   <THEAD>
   <TR>
   <th>Tipo de recarga</th>
   <th>Pasos</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>Si desea cargar una nueva configuración...</td>
   <td>
   <ol>
   <li>Pulse <b>Editar</b> para la Categoría que requiere una actualización.</li>
   <li>Seleccione el nuevo software que aplicar al dispositivo en la lista desplegable <i>Seleccionar software</i>.</li>
   </ol>
   </td>
   </tr>
   <tr>
   <td>Si desea recargar la configuración existente...</td>
   <td>Continúe con el paso siguiente.</td>
   </tr>
   </TBODY>
   </table>

4. Determine si desea aplicar un script posterior a la instalación una vez el dispositivo esté dispuesto.

   Si desea aplicar un script posterior a la instalación, seleccione el script de la lista desplegable Scripts existentes o escriba el URL totalmente cualificado del nuevo script. De lo contrario, vaya al siguiente paso.

5. Para dispositivos físicos, determine si desea añadir o eliminar particiones instaladas o si deben permanecer sin cambios.
   
   <table>
   <CAPTION>Tabla 2. Opciones de acción de partición</CAPTION>
   <THEAD>
   <TR>
   <th>Acción de partición</th>
   <th>Pasos</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>Para añadir particiones instaladas...</td>
   <td>
   <ul>
   <li>Pulse en el enlace <b>Añadir otra partición</b>.</li>
   <li>Especifique el nombre exacto de la partición.</li>
   <li>Especifique el tamaño de la partición (en GB). Si desea, puede seleccionar Crecer para que la partición crezca hasta llenar el espacio de disco restante. <p><b>Nota:</b> Sólo puede seleccionarse una partición para crecer a la vez. Esta partición será mayor que el tamaño especificado, y llenará toda la capacidad disponible. La capacidad de la partición que crecerá se calcula restando el tamaño combinado de todas las demás particiones del número Capacidad total que se proporciona en la sección Particiones instaladas.</p>
   </li>
   </ul>
   </td>
   </tr>
   <tr>
   <td>Para suprimir particiones instaladas...</td>
   <td>Pulse en <b>Suprimir</b> para suprimir la partición.</td>
   </tr>
   <tr>
   <td>Para continuar sin cambios...</td>
   <td>Continúe con el paso siguiente.</td>
   </tr>
   </TBODY>
   </table>
    
6. Determine si desea aplicar una o varias claves SSH al dispositivo.

7. Seleccione los recuadros de selección correspondientes a las opciones que desea aplicar al dispositivo durante o después de la recarga del sistema operativo. 

   **Nota:** Las opciones varían en función del dispositivo. No todas las opciones están disponibles para cada dispositivo.

8. Pulse en **Recargar la configuración indicada** para comenzar la revisión. Pulse **Cancelar** para cancelar los cambios al dispositivo y salir de la pantalla.

9. Verifique que todos los detalles en la sección Nueva configuración son correctos.  

10. Pulse en **Confirmar la recarga del sistema operativo ** para confirmar e iniciar la recarga. Pulse en **Cancelar** para cancelar la operación.

## ¿Qué es lo siguiente?
Después de iniciar el proceso de recarga del sistema operativo, se pone el dispositivo fuera de línea y comienza el proceso de recarga. El tiempo que dura la operación de recarga del sistema operativo depende de las configuraciones actual y nueva del dispositivo. Durante el proceso de configuración, el tiempo mínimo para la recarga de SO se muestra en cada pantalla. El intervalo de tiempo que se muestra es una estimación generada por el sistema. Si la recarga tarda más de 24 horas, póngase en contacto con el soporte de IBM.

Cuando el dispositivo vuelve a estar en línea, funciona como se había especificado en la nueva configuración para la recarga del sistema operativo. Todos los datos almacenados en el dispositivo se han perdido, pero pueden restaurarse si se había creado una copia del dispositivo antes de la recarga del sistema operativo. Si no se hizo una copia de seguridad de los datos, éstos no pueden recuperarse.
 
Deberá volver a registrar el dispositivo con eVault. <!--using the folliwng link: ![External link icon](../icons/launch-glyph.svg "External link icon")](https://knowledgelayer.softlayer.com/procedure/how-do-i-re-register-evault){: new_window}.-->
