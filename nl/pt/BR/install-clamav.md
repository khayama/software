---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-26"
---
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Instalando o ClamAV

Use este procedimento para instalar o ClamAV.

1. Efetue login no WHM em https://x.x.x.x:2087 (substitua x.x.x.x pelo IP de seu servidor)
2. Clique no ícone cPanel no lado direito da tela.
3. Clique no ícone **Gerenciar plug-ins** para visualizar a lista de plug-ins cPanel.
4. Na página **Módulos de complemento**, localize **clamavconnector**. Ative **Instalar e manter atualizado** e clique em **Salvar** no final da página.
A instalação levará em torno de vinte minutos para ser concluída.

**Notas**
A verificação de versão da biblioteca fica desativada por padrão. No entanto, o servidor deve ter zlib 1.2.2 ou superior instalado.

O licenciamento é a razão mais comum de falha da instalação de ClamAV. O complemento clamav é grátis, no entanto, é necessário registrar como uma licença profissional. Consulte https://www.clamav.net/ para obter mais informações. Depois de registrar corretamente sua licença, retorne para a etapa 4, desinstale e reinstale o clamavconnector.
