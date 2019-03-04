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

# Rechargement d'un système d'exploitation à l'aide d'un modèle d'image

## Différences entre un rechargement standard de système d'exploitation et un rechargement depuis un modèle d'image
Au cours du processus de rechargement standard de système d'exploitation, vous devez sélectionner individuellement les options de configuration. Lorsque vous effectuez le rechargement depuis un modèle d'image, la configuration est chargée exactement comme elle apparaît dans le modèle d'image. 

Dans un rechargement depuis un modèle d'image, vous pouvez néanmoins ajouter des fonctionnalités avant de recharger le système d'exploitation.

Procédez comme suit pour recharger un système d'exploitation depuis un modèle d'image à l'aide la fonction Charger à partir d'une image dans le portail client.

**Important :** si vous désirez conserver vos données, effectuez une sauvegarde de toutes les données avant de recharger le système d'exploitation. Comme le rechargement du système d'exploitation efface toutes les données du terminal, si vous n'avez pas sauvegardé les données avant le rechargement, elles sont supprimées définitivement et ne peuvent pas être récupérées.
{:shortdesc}

##Rechargement d'un système d'exploitation
1. Dans **Liste des unités**, cliquez sur le serveur nécessitant un rechargement de son système d'exploitation afin d'afficher la page Détails de l'unité.
2. Dans le menu **Actions**, sélectionnez **Charger à partir d'une image**.
3. Cochez la case du modèle d'image à charger sur le terminal.

   **Remarque :** avant d'effectuer le rechargement, le modèle d'image est copié sur le centre de données qui contient le terminal, s'il n'y était pas déjà. Si le modèle d'image doit être copié sur le centre de données, des frais peuvent vous être facturés si le modèle d'image n'est pas supprimé de cet emplacement après le rechargement du système d'exploitation.
  
4. Déterminez si vous désirez ajouter des fonctions. Les fonctions que vous sélectionnez sont ajoutées au terminal dans le cadre du processus de rechargement.
   
   <table>
   <CAPTION>Tableau 1. Fonctions facultatives</CAPTION>
   <THEAD>
   <TR>
   <th>Fonctions facultatives</th>
   <th>Etapes</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   </tr>
   <tr>
   <td>Oui, je souhaite ajouter des fonctions facultatives.</td>
   <td>
   <ol>
   <li>Cliquez sur <b>Charger Image Sélectionnée</b>.</li>
   <li>Consultez la configuration de l'image et continuez ou annulez cette action.</li>
   <li>Cliquez sur <b>Confirmer le rechargement du système d'exploitation</b> pour confirmer l'action et commencer le processus de rechargement du système d'exploitation.</li>
   </ol>
   </td>
   </tr>
   <tr>
   <td>Non, je ne souhaite pas ajouter de fonctions facultatives.</td>
   <td>Cliquez sur <b>Afficher Fonctions En Option</b>.</td>
   </tr>
   </TBODY>
   </table>

5. Configurez les options, le cas échéant. Pour plus de détails, consultez les informations suivantes.
   
   <dl>
   <dt>Script de Post-Installation</dt>
   <dd>Ajoute un script de post-installation existant ou nouveau.</dd>
   <dt>Clé SSH</dt>
   <dd>Ajoute une clé SSH au terminal lors de l'action de rechargement. </dd>
   <dt>Réinitialiser Mot de passe IPMI</dt>
   <dd> Cette option est disponible uniquement pour les terminaux physiques. </dd>
   <dt>Appliquer les mises à niveau du BIOS sur la carte mère</dt>
   <dd>Cette option est disponible uniquement pour les terminaux physiques. </dd>
   <dt>Appliquer les mises à jour du microcode pour tous les disques durs</dt>
   <dd>Cette option est disponible uniquement pour les terminaux physiques.</dd>
   <dt>Ajouter au pool de secours après le rechargement du système d'exploitation</dt>
   <dd>Cette option n'est disponible que sur les terminaux physiques et requiert une approbation en interne avant d'être disponible sur un compte.</dd>
   <dt>Effacer tous les disques durs</dt>
   <dd> Cette option est disponible uniquement sur les terminaux physiques et requiert des droits utilisateur spéciaux définis par l'administrateur de compte.</dd>
   <dt>Rechargement du système d'exploitation avec préservation du disque</dt>
   <dd>Conserve toutes les données sur le disque principal pendant le processus de rechargement de système d'exploitation. La préservation du disque convertit l'unité de stockage principale en Dispositif de Stockage Portable. Cette option est disponible uniquement sur les unités virtuelles et génère des frais basés sur le mode de facturation (horaire ou mensuelle) du terminal. Ces frais peuvent être abrogés en annulant le dispositif de stockage portable à n'importe quel moment après sa création.</dd>
   </dl>

6. Cliquez sur **Charger Image Sélectionnée**.

7. Vérifiez la configuration de l'image puis cliquez sur **Suivant** pour passer à l'écran suivant ou sur **Annuler** pour annuler l'action.

   **Remarque :** après que vous cliquiez sur **Suivant**, tous les ports réseau sur le terminal sont systématiquement fermés et le terminal peut être inaccessible pendant 15 minutes. Pendant cette période, l'action peut être annulée à tout moment en cliquant sur **Annuler**. Vous disposez de 15 minutes après avoir cliqué sur **Suivant** pour l'étape suivante, sinon il est nécessaire d'effectuer à nouveau la procédure. Ce processus est une protection pour s'assurer qu'aucune donnée supplémentaire ne soit ajoutée à un terminal entre la confirmation de la configuration et le déclenchement du rechargement du système d'exploitation.

8. Cliquez sur **Confirmer le rechargement du système d'exploitation** pour confirmer l'action et commencer le processus de rechargement du système d'exploitation. Cliquez sur **Annuler** pour annuler l'action.


## Etape suivante
Une fois que vous lancez le processus de rechargement du système d'exploitation, le terminal est mis hors ligne et le processus de rechargement du système d'exploitation débute.
La durée du rechargement du système d'exploitation varie en fonction de la configuration en cours et de la nouvelle configuration du terminal.
Pendant la configuration, la durée minimale du rechargement du système d'exploitation s'affiche sur chaque écran.
La durée affichée constitue une estimation par le système fournie à titre indicatif. Si le rechargement prend plus de 24 heures, contactez le support IBM.

Lorsque le terminal revient en ligne, il fonctionne comme spécifié dans la nouvelle configuration pour le rechargement du système d'exploitation. Toutes les données qui avaient été enregistrées sur le terminal sont perdues, mais peuvent être restaurées si vous avez effectué une sauvegarde du terminal avant son rechargement. Dans le cas contraire, les données ne peuvent pas être récupérées. 

Vous devrez enregistrer à nouveau votre terminal auprès d'eVault. <!--using the folliwng link: ![External link icon](../icons/launch-glyph.svg "External link icon")](https://knowledgelayer.softlayer.com/procedure/how-do-i-re-register-evault){: new_window}.-->
