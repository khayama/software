---



copyright:
  years: 2017
lastupdated: "2017-09-25"

subcollection: software


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Recarga de un sistema operativo utilizando una plantilla de imagen

## Diferencias entre una recarga de sistema operativo estándar y una recarga de una plantilla de imagen
Durante el proceso de recarga de SO estándar, se seleccionan individualmente las opciones de configuración para el dispositivo. Cuando se recarga desde una plantilla de imagen, la configuración se carga exactamente como aparece en la plantilla de imagen. 

En una plantilla de recarga de imagen, puede añadir características antes de recargar el sistema operativo.

Utilice los pasos siguientes para cargar un sistema operativo desde una plantilla de imagen mediante la característica de Carga desde una imagen en el Portal de cliente.

**Importante:** Si desea conservar sus datos, haga una copia de seguridad de todos los datos antes de llevar a cabo la recarga del sistema operativo. Una recarga del sistema operativo borra todos los datos del dispositivo; por lo tanto, si no se hace una copia de seguridad de los datos antes de la recarga, éstos se suprimirán de forma permanente y no se podrán recuperar.{:shortdesc}

##Recargar un sistema operativo
1. De la **Lista de dispositivos**, pulse el servidor que necesita una recarga del sistema operativo para mostrar la página Detalles del dispositivo.
2. En el menú **Acciones**, seleccione **Cargar desde imagen**.
3. Seleccione el recuadro de selección correspondiente a la plantilla de imagen que debe cargarse en el dispositivo.

   **Nota:** Antes de completar la recarga, la plantilla de imagen se copia en el centro de datos que contiene el dispositivo, si no se encuentra ya en el mismo centro de datos. Si la plantilla de imagen debe copiarse en el centro de datos, es posible que se aplique un cargo si la plantilla no se suprime de la ubicación una vez haya finalizado la recarga del sistema operativo.
  
4. Determine si desea añadir características. Las características que seleccione se añadirán al dispositivo como parte del proceso de recarga.
   
   <table>
   <CAPTION>Tabla 1. Características opcionales</CAPTION>
   <THEAD>
   <TR>
   <th>Características Opcionales</th>
   <th>Pasos</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   </tr>
   <tr>
   <td>Sí, deseo añadir características opcionales.</td>
   <td>
   <ol>
   <li>Pulse en <b>Cargar imagen seleccionada</b>.</li>
   <li>Revise la configuración de imagen y continúe o cancele el proceso.</li>
   <li>Pulse en <b>Confirmar la recarga del sistema operativo</b> para confirmar la acción e iniciar el proceso de recarga. </li>
   </ol>
   </td>
   </tr>
   <tr>
   <td>No, no deseo añadir características opcionales.</td>
   <td>Pulse en <b>Ver características opcionales</b>.</td>
   </tr>
   </TBODY>
   </table>

5. Configure las opciones tal como sea relevante. Consulte la siguiente información para obtener más detalles.
   
   <dl>
   <dt>Script de postinstalación</dt>
   <dd>Añade un script posterior a la instalación, existente o nuevo.</dd>
   <dt>Clave SSH</dt>
   <dd>Añade una clave SSH al dispositivo durante la acción de recarga. </dd>
   <dt>Restablecer contraseña de IPMI</dt>
   <dd> Esta opción sólo está disponible para dispositivos físicos. </dd>
   <dt>Aplicar actualizaciones de BIOS a la placa del sistema</dt>
   <dd>Esta opción sólo está disponible para dispositivos físicos. </dd>
   <dt>Aplicar actualizaciones de firmware para todos los discos duros</dt>
   <dd>Esta opción sólo está disponible para dispositivos físicos. </dd>
   <dt>Añadir a agrupación de repuesto después de cargar el sistema operativo</dt>
   <dd>Esta opción está disponible sólo en dispositivos físicos y requiere aprobación interna antes de estar disponible en una cuenta.</dd>
   <dt>Borrar todos los discos duros</dt>
   <dd> Esta opción está disponible solo en dispositivos físicos y requiere que el administrador de la cuenta defina permisos de usuario especiales.</dd>
   <dt>Recarga del sistema operativo con conservación de disco</dt>
   <dd>Conserva todos los datos existentes en el disco primario actual durante el proceso de recarga del sistema operativo. La conservación de disco convierte la unidad primaria en un dispositivo de almacenamiento portátil. Esta opción sólo está disponible en dispositivos virtuales e incurre en cargos basados en los patrones de facturación (por hora o mensual) del dispositivo. Es posible que puedan cancelarse los cargos cancelando el dispositivo de almacenamiento portátil en cualquier momento después de que se haya creado.</dd>
   </dl>

6. Pulse en **Cargar imagen seleccionada**.

7. Revise la configuración de la imagen y pulse en **Siguiente** para continuar con la pantalla siguiente o **Cancelar** para cancelar la acción.

   **Nota:** Después de pulsar **Siguiente**, el sistema cerrará todos los puertos de red del dispositivo y éste dejará de estar disponible durante un período máximo de 15 minutos. Durante este tiempo, la acción se puede cancelar en cualquier momento pulsando **Cancelar**. El siguiente paso debe completarse dentro de los 15 minutos siguientes a pulsar **Siguiente** o los pasos anteriores deberán completarse otra vez. Este proceso está ideado como una salvaguarda para asegurar que no se añaden datos a un dispositivo entre la confirmación de configuración y el inicio de la recarga del sistema operativo.

8. Pulse en **Confirmar la recarga del sistema operativo** para confirmar la acción e iniciar el proceso de recarga. Pulse en **Cancelar** para cancelar la operación.


## ¿Qué es lo siguiente?
Después de iniciar el proceso de recarga del sistema operativo, se pone el dispositivo fuera de línea y comienza el proceso de recarga. El tiempo que dura la operación de recarga del sistema operativo depende de las configuraciones actual y nueva del dispositivo. Durante el proceso de configuración, el tiempo mínimo para la recarga de SO se muestra en cada pantalla. El intervalo de tiempo que se muestra es una estimación generada por el sistema y se ofrece sólo como una cortesía. Si la recarga tarda más de 24 horas, póngase en contacto con el soporte de IBM.

Cuando el dispositivo vuelve a estar en línea, funciona como se había especificado en la nueva configuración para la recarga del sistema operativo. Todos los datos almacenados en el dispositivo se han perdido, pero pueden restaurarse si se había creado una copia del dispositivo antes de la recarga. Si no se hizo una copia de seguridad de los datos, éstos no pueden recuperarse. 

Deberá volver a registrar el dispositivo con eVault. <!--using the folliwng link: ![External link icon](../icons/launch-glyph.svg "External link icon")](https://knowledgelayer.softlayer.com/procedure/how-do-i-re-register-evault){: new_window}.-->
