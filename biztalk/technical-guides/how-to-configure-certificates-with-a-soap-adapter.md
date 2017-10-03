---
title: "如何使用 SOAP 适配器配置证书 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20ee05c5-9cea-456d-bff6-49dd249f0ff4
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e382fa9084fd728e04efa29900fb0222d8b05ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-certificates-with-a-soap-adapter"></a>如何使用 SOAP 适配器配置证书
SOAP 发送适配器可以帮助保护与接受或需要客户端证书的服务器的连接。 如果指定了客户端证书，则在连接要求或接受客户端证书的服务器时，SOAP 发送适配器将使用该证书。 如果未指定客户端证书和目标服务器需要客户端证书、 发件人未经过身份验证和发送 SOAP 适配器无法发送消息，并将遵循标准的重试逻辑。  
  
 SOAP 发送适配器使用的客户端证书位于运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 进程的帐户的个人存储中。 SOAP 适配器根据证书的指纹来指定证书。 如果 SOAP 发送适配器由于某种原因无法加载证书，则会挂起该适配器正在发送的消息。  
  
 当使用 SOAP 适配器发送加密或签名消息，将配置发送端口的客户端证书指纹 SOAP 传输属性。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，你必须登录为的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。  
  
### <a name="to-configure-biztalk-server-to-send-messages-over-a-soap-connection"></a>若要配置 BizTalk Server 用于通过 SOAP 连接发送消息  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建新的 SOAP 发送端口或打开现有的 SOAP 发送端口属性。  
  
2.  单击**配置**中**传输**部分**发送端口属性**对话框。  
  
3.  上**常规**选项卡上，在**身份验证类型**，选择**匿名**，**基本**，**摘要式**，或**NTLM**。  
  
4.  如果身份验证类型为**基本**或**摘要式**，请选择**不使用单一登录**（在这种情况下必须指定用户名和密码） 或选择**使用单一登录**（在这种情况下，你必须对 Affiliate 应用程序进行选择）。  
  
5.  在**SSL 客户端证书指纹**，输入适当的指纹。  
  
6.  单击**确定**，然后单击**确定**试。