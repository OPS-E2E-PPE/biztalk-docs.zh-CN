---
title: 如何使用 HTTP 适配器配置证书 |Microsoft 文档
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
ms.openlocfilehash: 6f74b0a88983ede90899dac908a5407f8406ec1e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297837"
---
# <a name="how-to-configure-certificates-with-an-http-adapter"></a>如何使用 HTTP 适配器配置证书
HTTP 发送适配器可以帮助保护与接受或需要客户端证书的服务器的连接。 如果指定客户端证书，则 HTTP 发送适配器将连接与服务器需要或不接受客户端证书时使用的证书。 如果未指定客户端证书，并且目标服务器需要客户端证书，发件人未经过身份验证和 HTTP 发送适配器无法发送消息，并遵循标准的重试逻辑。  
  
 HTTP 发送适配器使用的客户端证书位于运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 进程的帐户的个人存储中。 指定由其指纹的证书。 如果 HTTP 发送适配器无法正常工作，以加载证书出于任何原因，已发送的消息，则挂起。  
  
 当使用 HTTP 适配器发送加密或签名消息，配置 SSL 证书指纹发送端口的 HTTP 传输属性。 在此属性中，指定要用于消息身份验证的证书的指纹。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，你必须登录为的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。  
  
### <a name="to-configure-biztalk-server-to-send-messages-over-an-http-connection"></a>若要配置 BizTalk Server 用于通过 HTTP 连接发送消息  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建新的 HTTP 发送端口或为现有 HTTP 发送端口打开的属性。  
  
2.  单击**配置**中的传输部分**发送端口属性**对话框。  
  
3.  单击**身份验证**中**HTTP 传输属性**对话框。  
  
4.  在**身份验证类型**，选择**匿名**，**基本**，**摘要式**，或**Kerberos**。  
  
5.  如果身份验证类型为**基本**或**摘要式**，请选择**不使用单一登录**（在这种情况下必须指定用户名和密码） 或选择**使用单一登录**（在这种情况下，你必须对 Affiliate 应用程序进行选择）。  
  
6.  在**SSL 客户端证书指纹**，输入适当的指纹。  
  
7.  单击**确定**，然后单击**确定**试。