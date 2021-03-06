---
title: 如何使用 MSMQ 适配器配置证书 |Microsoft Docs
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
ms.openlocfilehash: bd2e59f6e238d4af1e926ba7d85612520c402f9a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253570"
---
# <a name="how-to-configure-certificates-with-an-msmq-adapter"></a>如何使用 MSMQ 适配器配置证书
MSMQ 发送适配器可帮助保护与接受或不需要客户端证书的服务器的连接。 如果指定客户端证书，则 MSMQ 发送适配器将连接与服务器的要求或接受客户端证书时使用该证书。 如果未指定客户端证书和目标服务器需要客户端证书、 发件人未经过身份验证和 MSMQ 发送适配器无法发送消息，并按照标准的重试逻辑。  

 MSMQ 发送适配器使用的客户端证书所用的帐户的个人存储中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进程正在运行。 证书的指纹来指定。 如果 MSMQ 发送适配器无法加载证书出于任何原因，已发送的消息被挂起。  

 当使用 MSMQ 适配器发送加密或签名邮件时，配置发送端口的证书指纹 MSMQ 传输属性。 此属性中指定要用于消息身份验证的证书的指纹。 使用此属性结合使用身份验证属性对消息进行验证。 使用用户名和密码属性来访问队列。  

## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，您必须登录以成员的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  

### <a name="to-configure-biztalk-server-to-send-messages-over-an-msmq-connection"></a>若要配置 BizTalk Server 通过 MSMQ 连接发送消息  

1. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建新的 MSMQ 发送端口或打开现有的 MSMQ 发送端口的属性。  

2. 单击**配置**中**传输**一部分**发送端口属性**对话框。  

3. 在中**MSMQ 传输属性**对话框中，对于**身份验证**，选择**True**。  

4. 有关**证书指纹**，输入适当的指纹。  

5. 单击**确定**，然后单击**确定**试。
