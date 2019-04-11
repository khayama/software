---
copyright:
  years: 1994, 2017
lastupdated: "2017-09-26"

keywords: ClamAV

subcollection: software
---
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 安装 ClamAV
{: #installing-clamav}

使用此过程安装 ClamAV。

1. 登录到 `https://x.x.x.x:2087`（将 x.x.x.x 替换为您的服务器 IP）上的 WHM 
2. 单击屏幕最右侧的 cPanel 图标。
3. 单击**管理插件**图标，以查看 cPanel 插件的列表。
4. 在**附加模块**页面上，找到 **clamavconnector**。启用**安装并保持更新**，然后单击页面最下方的**保存**。
完成安装需要二十分钟左右。

**注：**缺省情况下，会禁用 lib 版本检查。但是，服务器已安装 zlib 1.2.2 或更高版本。

许可问题是 ClamAV 安装失败的最常见原因。clamav 附加组件免费，但您需要注册为专业版许可证。有关更多信息，请参阅 https://www.clamav.net/。正确注册许可证之后，回到步骤 4，卸载然后重新安装 clamavconnector。
