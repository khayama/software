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

# Recarregando um OS usando um modelo de imagem

## Diferenças entre um recarregamento padrão do OS e um recarregamento de um modelo de imagem
Durante o processo de Recarregamento de OS padrão, você seleciona opções de configuração para o dispositivo individualmente. Quando você recarrega de um modelo de imagem, a configuração é carregada exatamente como aparece no modelo de imagem. 

Em um recarregamento do modelo de imagem, ainda é possível incluir recursos antes de recarregar o OS.

Use as etapas a seguir para recarregar um OS de um modelo de imagem usando o recurso Carregar da imagem no Portal do cliente.

**Importante:** se desejar reter seus dados, faça backup de todos os dados antes de recarregar o OS. Um recarregamento de OS limpa todos os dados do dispositivo, portanto, se você não tiver feito backup dos dados antes do recarregamento, eles serão permanentemente excluídos e não poderão ser recuperados.
{:shortdesc}

##Recarregar um OS
1. Na **Lista de dispositivos**, clique no servidor que precisa de um Recarregamento de OS para mostrar a página Detalhes do dispositivo.
2. No menu **Ações**, selecione **Carregar da imagem**.
3. Marque a caixa de seleção do modelo de imagem para que o modelo de imagem seja carregado no dispositivo.

   **Nota:** antes de concluir o recarregamento, o modelo de imagem será copiado para o data center que contém o dispositivo, se ele ainda não estiver localizado no mesmo data center. Se o modelo de imagem tiver que ser copiado para o data center, uma taxa poderá ser cobrada se o modelo não for excluído do local depois que o Recarregamento de OS ocorrer.
  
4. Determine se deseja incluir algum recurso. Todos os recursos selecionados serão incluídos no dispositivo como parte do processo de recarregamento.
   
   <table>
   <CAPTION>Tabela 1. Recursos opcionais</CAPTION>
   <THEAD>
   <TR>
   <th>Recursos opcionais</th>
   <th>Etapas</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   </tr>
   <tr>
   <td>Sim, eu desejo incluir recursos opcionais.</td>
   <td>
   <ol>
   <li>Clique em <b>Carregar imagem selecionada</b>.</li>
   <li>Revise a configuração de imagem e continue ou cancele.</li>
   <li>Clique em <b>Confirmar recarregamento de OS</b> para confirmar a ação e iniciar o processo de recarregamento de OS.</li>
   </ol>
   </td>
   </tr>
   <tr>
   <td>Não, eu não desejo incluir recursos opcionais.</td>
   <td>Clique em <b>Visualizar recursos opcionais</b>.</td>
   </tr>
   </TBODY>
   </table>

5. Configure as opções, conforme relevante. Consulte as informações a seguir para obter mais detalhes.
   
   <dl>
   <dt>Script de pós-instalação</dt>
   <dd>Inclui um script de pós-instalação novo ou existente.</dd>
   <dt>Chave SSH</dt>
   <dd>Inclui uma chave SSH no dispositivo após a ação de recarregamento. </dd>
   <dt>Reconfigurar senha do IPMI</dt>
   <dd> Essa opção está disponível somente para dispositivos físicos. </dd>
   <dt>Aplicar upgrades de BIOS da placa-mãe</dt>
   <dd>Essa opção está disponível somente para dispositivos físicos. </dd>
   <dt>Aplicar atualizações de firmware para todos os discos rígidos</dt>
   <dd>Essa opção está disponível somente para dispositivos físicos.</dd>
   <dt>Incluir no conjunto sobressalente após Recarregamento de OS</dt>
   <dd>Essa opção fica disponível somente em dispositivos físicos e requer aprovação interna antes de ficar disponível em uma conta.</dd>
   <dt>Apagar todos os discos rígidos</dt>
   <dd> Essa opção está disponível somente em dispositivos físicos e requer permissões de usuário especiais configuradas pelo administrador da Conta.</dd>
   <dt>Recarregamento de OS com preservação de disco</dt>
   <dd>Retém todos os dados no disco primário atual durante o processo de Recarregamento de OS. A preservação de disco converte a unidade primária em um dispositivo de Armazenamento móvel. Essa opção fica disponível somente em dispositivos virtuais e incorre em encargos com base nos padrões de faturamento (por hora ou mensal) do dispositivo. Os encargos podem ser cancelados cancelando o dispositivo de Armazenamento móvel a qualquer momento depois de ter sido criado.</dd>
   </dl>

6. Clique em **Carregar imagem selecionada**.

7. Revise a configuração da imagem e clique em **Avançar** para continuar na próxima tela ou **Cancelar** para cancelar a ação.

   **Nota:** depois de clicar em **Avançar**, todas as portas de rede do dispositivo são sistematicamente encerradas e o dispositivo fica indisponível por até 15 minutos. Durante esse tempo, a ação pode ser cancelada a qualquer momento clicando em **Cancelar**. A próxima etapa deverá ser concluída dentro de 15 minutos após clicar em **Avançar** ou as etapas anteriores deverão ser concluídas novamente. Esse processo é ativado como uma proteção para assegurar que nenhum dado adicional seja incluído em um dispositivo entre a confirmação de configuração e a iniciação de Recarregamento de OS.

8. Clique em **Confirmar recarregamento de OS** para confirmar a ação e iniciar o processo de recarregamento OS. Clique em **Cancelar** para cancelar a ação.


## O que vem a seguir?
Depois de iniciar o processo de Recarregamento de OS, o dispositivo é colocado off-line e o processo de Recarregamento de OS começa.
O período no qual um recarregamento de S.O. ocorre varia com base na configuração atual e nova do dispositivo.
Durante o processo de configuração, o tempo mínimo para o Recarregamento de OS é exibido em cada tela.
O prazo exibido é uma estimativa feita pelo sistema e é dado como cortesia. Se o recarregamento levar mais de 24 horas, entre em contato com o Suporte IBM.

Quando o dispositivo retornar on-line, ele funcionará conforme especificado na nova configuração do Recarregamento de OS. Todos os dados salvos anteriormente no dispositivo são perdidos, mas poderão ser restaurados se tiver sido feito um backup do dispositivo antes de seu recarregamento. Caso não tenha sido feito backup dos dados, eles não poderão ser recuperados. 

Será necessário registrar novamente seu dispositivo com eVault. <!--using the folliwng link: ![External link icon](../icons/launch-glyph.svg "External link icon")](https://knowledgelayer.softlayer.com/procedure/how-do-i-re-register-evault){: new_window}.-->
