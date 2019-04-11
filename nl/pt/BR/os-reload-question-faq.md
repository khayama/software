---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-25"

keywords: OS Reload, Operating System, cpsrvd email

subcollection: software

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:faq: data-hd-content-type='faq'}

# FAQ
{: #faqs}

## O Sistema Operacional (OS) pode ser mudado no dispositivo?
{: #can-the-operating-system-os-be-changed-on-the-device-}

É possível mudar seu OS e o software instalado recarregando um OS <!--[OS Reload](perform-os-reload-device.html){:new_window}-->. Depois que você seleciona Recarregamento de OS no dispositivo, o sistema exibe um link para uma página que permite atualizar o software no sistema. É possível atualizar o OS, o Painel de controle, os pacotes de Antivírus e o software de banco de dados nessa página.

## Você fornece recarregamentos complementares do OS?
{: #do-you-provide-complimentary-os-reloads-}

Os recarregamentos automatizados de OS são gratuitos, incluindo recarregamentos de OS customizados, tal como mudança de sistemas operacionais, adição ou remoção de painéis de controle, edição de partição e outras opções. Abra o Portal do cliente para obter mais informações.

## Como posso controlar o status do recarregamento de OS?
{: #how-can-i-track-the-status-of-the-os-reload-}

Em Hardware no Portal do cliente, há uma seção Notas para cada um de seus servidores. A seção Notas inclui links para informações sobre a etapa atual do recarregamento e o tempo estimado para concluir essa parte do recarregamento.

## Um S.O. pode recarregar discos secundários?
{: #can-an-os-reload-erase-secondary-disks-}

Um recarregamento de OS apenas formata o disco primário no sistema. Todos os outros discos permanecem sozinhos. Isso funciona da mesma forma ao recarregar de um modelo de imagem. Se o modelo contiver mais de um disco, apenas o disco primário será formatado. Nenhuma mudança é feita nos outros discos.

## Por que meu e-mail cpsrvd falhou?
{: #why-did-my-cpsrvd-email-fail-}

Na maioria dos casos, quando você obtiver um e-mail que declare que **cpsrvd failed**, ele será enviado imediatamente após uma reinicialização. Esse erro ocorre quando chkservd tenta validar o processo cpsrvd. A validação falha porque o processo não foi iniciado.

Se você receber um e-mail do serviço chkservd indicando que o cpsrvd falhou, será possível ignorar a mensagem na maioria dos casos. No entanto, se você receber 5 ou mais dessas mensagens em uma linha ou se receber mais de 4 em um dia após as reinicializações, abra um chamado de suporte
