---
title: 如何使用 MSMQ 适配器配置证书 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 922a171d-705f-4465-acda-212aa3797c57
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f36e3d13920982f79fe693a306a8123f089c76e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297909"
---
# <a name="how-to-configure-certificates-with-an-msmq-adapter"></a>如何使用 MSMQ 适配器配置证书
MSMQ 发送适配器可以帮助保护与接受或需要客户端证书的服务器的连接。 如果指定客户端证书，则 MSMQ 发送适配器将连接与服务器需要或不接受客户端证书时使用的证书。 如果未指定客户端证书和目标服务器需要客户端证书、 发件人未经过身份验证和 MSMQ 发送适配器无法发送消息，并将遵循标准的重试逻辑。  
  
 MSMQ 发送适配器使用的客户端证书的个人存储中的所用的帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进程正在运行。 指定由其指纹的证书。 如果 MSMQ 发送适配器无法正常工作，以加载证书出于任何原因，已发送的消息，则挂起。  
  
 当使用 MSMQ 适配器发送加密或签名消息，将配置发送端口的证书指纹 MSMQ 传输属性。 在此属性中，指定要用于消息身份验证的证书的指纹。 此属性与“使用验证”属性结合使用，对消息进行验证。 使用“用户名”和“密码”属性可以访问队列。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，你必须登录为的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。  
  
### <a name="to-configure-biztalk-server-to-send-messages-over-an-msmq-connection"></a>若要配置 BizTalk Server 用于通过 MSMQ 连接发送消息  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建新的 MSMQ 发送端口或打开现有的 MSMQ 发送端口属性。  
  
2.  单击**配置**中**传输**部分**发送端口属性**对话框。  
  
3.  在**MSMQ 传输属性**对话框中，为**身份验证**，选择**True**。  
  
4.  有关**证书指纹**，输入适当的指纹。  
  
5.  单击**确定**，然后单击**确定**试。