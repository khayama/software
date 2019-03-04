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

# ClamAV のインストール

ClamAV をインストールするには、この手順を使用します。

1. https://x.x.x.x:2087 で WHM にログインします (x.x.x.x をサーバー IP に置き換えてください)
2. 画面の右端にある cPanel アイコンをクリックします。
3. **「プラグインの管理 (Manage Plugins)」**アイコンをクリックして、cPanel プラグインのリストを表示します。
4. **「アドオン・モジュール (Addon Modules)」**ページで **clamavconnector** を見つけます。**「インストールし、最新の状態を保つ (Install and keep Updated)」**を有効にし、ページの最下部にある**「保存 (Save)」**をクリックします。
インストールが完了するには約 20 分かかります。

**注:**
デフォルトでは、lib バージョン検査は無効になっています。ただし、サーバーには zlib 1.2.2 以上がインストールされている必要があります。

ClamAV のインストールが失敗する最も一般的な原因はライセンスです。clamav アドオンは無料ですが、プロフェッショナル・ライセンスとして登録する必要があります。詳しくは、https://www.clamav.net/ を参照してください。ライセンスを正しく登録した後、ステップ 4 に戻って、clamavconnector をアンインストールしてから再インストールしてください。
