---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-26"

subcollection: software
---
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Instalación de ClamAV

Utilice este procedimiento para instalar ClamAV.

1. Inicie sesión en WHM con https://x.x.x.x:2087 (sustituya x.x.x.x por la dirección IP de su servidor)
2. Haga clic en el icono cPanel en el extremo derecho de la pantalla.
3. Haga clic en el icono **Gestionar plugins** para ver la lista de plugins de cPanel.
4. En la página **Módulos de extensión**, localice **clamavconnector**. Habilite **Instalar y mantener actualizado** y pulse en **Guardar** al final de la página.
La instalación tardará unos veinte minutos en completarse.

**Notas**
La comprobación de la versión de biblioteca está inhabilitada de forma predeterminada. Sin embargo, el servidor debe tener instalada la zlib 1.2.2 o posterior.

La licencia es la razón más común para que falle la instalación de ClamAV. El complemento ClamAV es gratuito; sin embargo debe registrarse como una licencia profesional. Consulte https://www.clamav.net/ para obtener más información. Tras registrar su licencia correctamente, vuelva al paso 4, desinstale y vuelva a instalar clamavconnector.
