---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft, restoring OS, restoring bare metal

subcollection: software

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Restaurando seu servidor por meio de uma imagem R1Soft
{: #restoring-your-server-from-an-r1soft-image}

Use este procedimento para concluir uma restauração para {{site.data.keyword.BluVirtServers_full}} ou {{site.data.keyword.BluBareMetServers_full}} público ou privado. Use esse processo se uma falha do servidor causar perda de dados ou de S.O. Esse processo restaura todos os blocos do sistema de arquivos cujo backup foi feito (incluindo o S.O. e quaisquer arquivos que não foram excluídos dos backups).

Não use esse processo se a restauração de um subconjunto de arquivos for o objetivo. Para restaurar apenas os arquivos, consulte [Wiki do R1Soft](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}.

## Restaurando seu dispositivo virtual
{: #restoring-your-virtual-device}

1. Clique no dispositivo que você deseja restaurar no [{{site.data.keyword.slportal}} ](https://control.softlayer.com/){:new_window}.
2. Clique no menu **Ações** e escolha **Inicializar por meio da imagem** e você obterá uma lista de imagens privadas.
3. Escolha **Imagens públicas** no menu.
4. Escolha a imagem de inicialização do agente R1Soft apropriada para sua versão do servidor R1Soft (serverbackup-centos-bootcd-agent.iso) e clique no link **Inicializar por meio desta imagem** à direita.
5. Na página **Detalhes do dispositivo** para o servidor que você está restaurando, clique em **Ações** > **Console do KVM**.
6. Após o console estar ativo e a imagem inicializada, você verá uma tela do carregador de inicialização Debian com algumas opções. Pressione a tecla Enter para inicializar por meio da opção padrão.
7. Depois que o S.O. for inicializado, digite `netconfig` e pressione **Enter**.
8. Escolha **Sim** para configurar a rede.
9. Insira detalhes de configuração de rede por meio dos detalhes do dispositivo no portal Controle.
10. Escolha **Sim** quando solicitado para reiniciar a rede.
11. Opcionalmente, digite `passed root` para configurar uma senha raiz para logins de SSH e digite service ssh start para permitir o login de SSH. Esta etapa poderá ser útil se o console do KVM estiver lento.
12. Digite `service cdp-agent restart` (Esse comando inicia o agente do Tivoli Continuous Data Protection for Files se ele ainda não estiver em execução).

## Restaurando seu dispositivo bare metal
{: #restoring-your-bare-metal-device}

1. Abra um chamado no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e solicite que inicializemos seu servidor bare metal no **modo de Restauração bare metal R1Soft**.
2. Usando a página **Detalhes do dispositivo** para o servidor que você está restaurando, efetue login no **console do IPMI KVM**.
3. Após o console estar ativo e a imagem inicializada, você verá uma tela do carregador de inicialização Debian com algumas opções. Pressione a tecla Enter para inicializar por meio da opção padrão.
4. Depois que o S.O. for inicializado, digite `netconfig` e pressione **Enter**.
5. Escolha **Sim** para configurar a rede.
6. Insira detalhes de configuração de rede por meio dos detalhes do dispositivo no portal Controle.
7. Escolha **Sim** quando solicitado para reiniciar a rede.
8. Opcionalmente, digite `passed root` para configurar uma senha raiz para logins de SSH e digite service ssh start para permitir o login de SSH. Esta etapa poderá ser útil se o console do KVM estiver lento.
9. Digite `service cdp-agent restart` (Esse comando inicia o agente do Tivoli Continuous Data Protection for Files se ele ainda não estiver em execução).

## Selecionando o servidor R1Soft e outros parâmetros e opções de restauração
{: #selecting-the-r1soft-server-and-other-restore-parameters-and-options}

Consulte a documentação do R1Soft para [Desempenhando uma restauração bare metal](http://wiki.r1soft.com/display/ServerBackup/Perform+a+bare-metal+restore). É necessário selecionar o servidor para restaurar e selecionar o sistema de arquivos, as tabelas de parte e outras opções de restauração.
