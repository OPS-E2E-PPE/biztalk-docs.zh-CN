---
title: 如何使用 HTTP 适配器配置证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc2f454f-22b5-4113-9a23-e00a816d5e48
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 520204a6c0f411f8f622838b846a3af41b6c60a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007094"
---
# <a name="how-to-configure-certificates-with-an-http-adapter"></a>如何使用 HTTP 适配器配置证书
HTTP 发送适配器可帮助保护与接受或不需要客户端证书的服务器的连接。 如果指定客户端证书，则 HTTP 发送适配器将连接与服务器的要求或接受客户端证书时使用该证书。 如果未指定客户端证书和目标服务器需要客户端证书，发送方未经过身份验证和 HTTP 发送适配器将无法发送消息，并遵循标准的重试逻辑。  

 HTTP 发送适配器使用的客户端证书位于运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 进程的帐户的个人存储中。 证书的指纹来指定。 如果 HTTP 发送适配器无法加载证书出于任何原因，已发送的消息被挂起。  

 当使用 HTTP 适配器发送加密或签名邮件时，配置 SSL 证书指纹的发送端口的 HTTP 传输属性。 此属性中指定要用于消息身份验证的证书的指纹。  

## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，您必须登录以成员的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  

### <a name="to-configure-biztalk-server-to-send-messages-over-an-http-connection"></a>若要配置 BizTalk Server 通过 HTTP 连接发送消息  

1. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建一个新的 HTTP 发送端口或打开现有 HTTP 发送端口的属性。  

2. 单击**配置**中的传输部分**发送端口属性**对话框。  

3. 单击**身份验证**中**HTTP 传输属性**对话框。  

4. 在中**身份验证类型**，选择**Anonymous**，**基本**，**摘要**，或**Kerberos**。  

5. 如果身份验证类型为**基本**或**摘要**，选择**不使用单一登录**（在这种情况下必须指定用户名和密码），或选择**使用单一登录**（在这种情况下必须选择关联应用程序）。  

6. 在中**SSL 客户端证书指纹**，输入适当的指纹。  

7. 单击**确定**，然后单击**确定**试。
