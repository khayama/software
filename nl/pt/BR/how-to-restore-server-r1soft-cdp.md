---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-08"

keywords: R1Soft

subcollection: software

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Restaurando um servidor com o R1Soft Tivoli Continuous Data Protection for Files

Use este processo para concluir uma [restauração bare metal](http://wiki.r1soft.com/display/CDP/Bare-Metal+Restore){:new_window} para um servidor virtual público ou privado (VSI) do {{site.data.keyword.BluSoftlayer_full}} se ocorrer uma falha do servidor que causa perda de dados ou de S.O.

Todos os blocos do sistema de arquivos que são submetidos a backup são restaurados, incluindo o S.O. e quaisquer arquivos que não foram excluídos dos backups. Não siga esse processo se você deseja restaurar um subconjunto de arquivos. Para restaurar apenas os arquivos, consulte [http://wiki.r1soft.com/display/CDP/Restoring+Files](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window}.

## Preparando o servidor R1Soft Tivoli Continuous Data Protection for Files Server

1. Abra uma janela do navegador e efetue login no servidor R1Soft Tivoli Continuous Data Protection for Files (as senhas de IP e de administrador estão disponíveis no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}).
2. Clique em **Pontos de recuperação** no portal de gerenciamento R1Soft Tivoli Continuous Data Protection for Files.
3. Selecione o **Servidor** que você deseja restaurar e o **Disco seguro** do qual você deseja restaurar.
4. Localize o ponto do qual você deseja restaurar na lista de pontos de recuperação.
5. Clique em **Restauração bare metal** (o ícone de blindagem) para iniciar o **Assistente de restauração**.
6. Clique em **Avançar** no **Assistente de restauração**.
7. Selecione os sistemas de arquivos a serem restaurados e clique em **Avançar**.
8. Selecione o host para o qual você deseja restaurar. Ele pode ser o host original ou um host diferente. (Nota: as etapas neste procedimento se recuperam para o mesmo servidor.)
9. Clique em **Avançar**.
10. Escolha a configuração de armazenamento a ser usada (use o que está no lugar no servidor ou escolha uma com base nos backups).
11. Selecione as **Tabelas de partições** que você deseja usar se você optou por escolher o layout do sistema de arquivos.
12. Mapeie seus sistemas de arquivos para os dispositivos de bloco corretos (tal como C:\ = /dev/sda1) e clique em **Avançar**.
13. Selecione as opções de restauração, como **Reinicializar após restauração**, **Verificar sistema de arquivos após restauração** e clique em **Avançar**.
14. Verifique suas opções e clique em **Restaurar** ou volte para mudar suas opções de restauração.

Uma janela aparece com o status da restauração atual

## Preparando o dispositivo para restauração

1. Abra uma janela do navegador e acesse [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Clique em **Dispositivos**, **Lista de dispositivos** e selecione o dispositivo a ser restaurado.
3. Clique em **Ações** e escolha **Inicializar por meio da imagem** para exibir uma lista de imagens privadas.
4. Escolha **Imagens públicas** no menu.
4. Escolha a imagem de inicialização do agente R1Soft apropriada para sua versão do servidor R1Soft (*r1soft-cdp-bootcd-server-4.0.0.iso*) e clique em **Inicializar por meio desta imagem**.
5. Clique em **Ações**, **Console do KVM** na página Detalhes do dispositivo para o servidor que está sendo restaurado. Após o console estar ativo e a imagem inicializada, você verá uma tela de carregador de inicialização Debian com algumas opções.
6. Pressione **Enter** para inicializar usando a opção padrão.
7. Digite netconfig no prompt r1soft-recovery depois que o S.O. for iniciado e pressione **Enter**.
8. Escolha **Sim** para configurar a rede.
9. Insira os detalhes de configuração de rede da página **Detalhes do dispositivo**.
10. Clique em **Sim** quando solicitado para reiniciar a rede.
11. **Opcional**: digite `passwd root` para configurar uma senha raiz para logins de SSH e digite `service ssh` start para permitir login de SSH, o que pode ser útil se o console do KVM estiver lento para responder.
12. Digite `service cdp-agent restart`. Esse comando inicia o agente do Tivoli Continuous Data Protection for Files, mesmo se ele ainda não estiver em execução.
13. Selecione **Inicializar por meio da imagem**. Um quadro aparece declarando que o dispositivo está configurado para inicializar por meio da imagem *r1soft-cdp-bootcd-agent-4.0.0.iso*. Será exibida uma pergunta sobre como descarregar a imagem e retornar ao iniciador normal.
14. Clique em **Sim** e o servidor será reinicializado por meio do disco do sistema

O servidor será executado por meio de um processo chkdsk ou fsck para verificar o disco e pode se reiniciar sozinho novamente. Após a conclusão do processo, seu servidor ou VM estará operacional com dados que são restaurados do ponto de restauração escolhido.
