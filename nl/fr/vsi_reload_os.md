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

#  Rechargement d'un système d'exploitation
Vous pouvez recharger le système d'exploitation sur un terminal à tout moment pour restaurer un terminal à son état de fonctionnement d'origine ou pour reconfigurer un terminal avec un autre logiciel. Un rechargement du système d'exploitation supprime toutes les données du terminal et applique la configuration d'origine, comme cela est spécifié lors de la configuration du rechargement du système d'exploitation. Vu que le rechargement du système d'exploitation efface toutes les données du terminal, si celles-ci n'ont pas été sauvegardées avant le rechargement, elles sont supprimées définitivement et ne peuvent pas être récupérées.
{:shortdesc}

**Important :** si vous désirez conserver vos données, effectuez une sauvegarde de toutes les données avant d'effectuer un rechargement du système d'exploitation. 

## Rechargement du système d'exploitation
1. Dans **Liste des unités**, cliquez sur le serveur nécessitant un rechargement de son système d'exploitation afin d'afficher la page Détails de l'unité.
2. Dans le menu **Actions**, sélectionnez **Rechargement du système d'exploitation**.
3. Déterminez si vous désirez recharger la configuration existante ou recharger le terminal avec une nouvelle configuration.

   <table>
   <CAPTION>Tableau 1. Options de rechargement du système d'exploitation</CAPTION>
   <THEAD>
   <TR>
   <th>Type de rechargement</th>
   <th>Etapes</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>Si vous désirez recharger avec une nouvelle configuration...</td>
   <td>
   <ol>
   <li>Cliquez sur <b>Editer</b> pour la catégorie à mettre à jour.</li>
   <li>Sélectionnez le nouveau logiciel à appliquer au terminal dans la liste déroulante <i>Sélectionner le logiciel</i>.</li>
   </ol>
   </td>
   </tr>
   <tr>
   <td>Si vous désirez recharger avec la configuration existante...</td>
   <td>Passez à l'étape suivante.</td>
   </tr>
   </TBODY>
   </table>

4. Déterminez si un script de post-installation doit être appliqué après que le terminal a été provisionné.

   Si vous désirez appliquer un script de post-installation, sélectionnez-le dans la liste déroulante Script existant ou entrez l'URL qualifiée du nouveau script. Sinon, passez à l'étape suivante.

5. Pour les unités physiques, déterminez s'il convient d'ajouter ou de supprimer des partitions installées ou de les conserver telles quelles.
   
   <table>
   <CAPTION>Tableau 2. Options d'action de partition</CAPTION>
   <THEAD>
   <TR>
   <th>Action de partition</th>
   <th>Etapes</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>Ajout de partitions installées...</td>
   <td>
   <ul>
   <li>Cliquez sur le lien <b>Ajouter autre partition</b>.</li>
   <li>Entrez le nom exact de la partition.</li>
   <li>Entrez la taille de la partition (en Go). Si vous le souhaitez, vous pouvez sélectionner Développer afin que la partition occupe l'espace restant.
   <p><b>Remarque :</b> Vous pouvez sélectionner une seule partition à la fois pour cette opération. Cette partition est plus importante que la taille indiquée et occupe toute la capacité disponible. La capacité de cette partition est calculée en soustrayant la taille de toutes les autres partitions de la capacité totale fournie dans la section des partitions installées.</p>
   </li>
   </ul>
   </td>
   </tr>
   <tr>
   <td>Suppression de partitions installées...</td>
   <td>Cliquez sur <b>Supprimer</b> pour supprimer la partition.</td>
   </tr>
   <tr>
   <td>Conservation de la configuration existante...</td>
   <td>Passez à l'étape suivante.</td>
   </tr>
   </TBODY>
   </table>
    
6. Déterminez le nombre de clés SSH à appliquer au terminal.

7. Cochez les cases appropriées pour les options que vous désirez appliquer au terminal pendant ou après le rechargement du système d'exploitation.

   **Remarque :** Les options varient en fonction du terminal. Toutes les options ne sont pas disponibles pour chaque terminal.

8. Cliquez sur **Recharger configuration ci-dessus** pour examiner la configuration. Cliquez sur **Annuler** pour annuler les modifications du terminal et quitter l'écran.

9. Vérifiez que les informations s'affichant dans la section Nouvelle configuration sont correctes.  

10. Cliquez sur **Confirmer le rechargement du système d'exploitation** pour confirmer l'opération et déclencher le rechargement du système d'exploitation. Cliquez sur **Annuler** pour annuler l'action.

## Etape suivante
Une fois que vous lancez le processus de rechargement du système d'exploitation, le terminal est mis hors ligne et le processus de rechargement du système d'exploitation débute.
La durée du rechargement du système d'exploitation varie en fonction de la configuration en cours et de la nouvelle configuration du terminal.
Pendant la configuration, la durée minimale du rechargement du système d'exploitation s'affiche sur chaque écran.
La durée affichée constitue une estimation générée par le système. Si le rechargement prend plus de 24 heures, contactez le support IBM.

Lorsque le terminal revient en ligne, il fonctionne comme spécifié dans la nouvelle configuration pour le rechargement du système d'exploitation. Toutes les données qui avaient été enregistrées sur le terminal sont perdues, mais peuvent être restaurées si vous avez effectué une sauvegarde du terminal avant le rechargement du système d'exploitation. Dans le cas contraire, les données ne peuvent pas être récupérées.
 
Vous devrez enregistrer à nouveau votre terminal auprès d'eVault. <!--using the folliwng link: ![External link icon](../icons/launch-glyph.svg "External link icon")](https://knowledgelayer.softlayer.com/procedure/how-do-i-re-register-evault){: new_window}.-->
