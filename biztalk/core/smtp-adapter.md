---
title: "SMTP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SMTP adapters, about SMTP adapters
- SMTP adapters, authenticating
- send adapters, SMTP adapters
- authenticating, SMTP adapters
- SMTP adapters
- SMTP adapters, send adapters
ms.assetid: b712f76d-3ce4-4780-9627-951e5951bd8a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0d0d16bf266d0b636aa9955b5c25b37d9ab54d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="smtp-adapter"></a>SMTP 适配器
使用简单邮件传输协议 (SMTP) 适配器可以通过 SMTP 协议在运行 Microsoft BizTalk Server 的服务器和其他应用程序之间交换信息。 BizTalk Server 可以通过创建电子邮件并将其发送到指定的电子邮件地址来向其他应用程序发送消息。 SMTP 发送适配器可在内部创建基于 SMTP 的电子邮件，并将其发送到目标电子邮件地址。 目标电子邮件地址是 SMTP 适配器的一个属性。 在您配置 SMTP 发送端口时，BizTalk 浏览器将公开此属性。  
  
 SMTP 适配器支持的通配符字符**收件人**， **FROM**， **CC**和**主题**属性，并将其解析为其实际值。 如果中的通配符字符**收件人**， **FROM**，和**CC**属性无法解决，SMTP 传输记录错误并将消息放入挂起的队列或将该消息重定向到备份传输。 如果在中无法解析的通配符字符**主题**属性，不会发送该消息**主题**完全如下所示的属性 （例如，"消息 %messageid%") 指定的属性。  
  
 默认情况下，SMTP 消息文本为纯文本格式。 若要在消息正文中使用 HTML 格式，则可以将该适配器配置为对消息文本使用 HTML 文件内容。  
  
 有关 SMTP 安全问题的详细信息，请参阅[SMTP 适配器安全建议](../core/smtp-adapter-security-recommendations.md)。  
  
 SMTP 适配器仅由一个适配器组成，即发送适配器。 该发送适配器控制使用 SMTP 适配器的发送端口。  
  
 本主题将介绍消息通过 SMTP 发送适配器的流程。  
  
 **SMTP 发送适配器**  
  
 SMTP 发送适配器可获取来自服务器的消息，并将这些消息发布到 SMTP 服务器，该服务器可将这些消息发送给电子邮件收件人。 SMTP 发送适配器获取的消息内容可来自 BizTalk 消息对象的正文部分、指定的文件或配置适配器时在可用对话框中输入的文本。  
  
 在 SMTP 发送适配器将消息成功发布到 SMTP 服务器之后，SMTP 发送适配器将从 MessageBox 数据库中删除该消息。  
  
 SMTP 发送适配器可以对通过 SMTP 发送适配器发送的消息请求送达通知和阅读回执。 SMTP 适配器提供的通知和读取回执的 SMTP 上指定的地址到**从**标头。  
  
 **SMTP 服务器的身份验证**  
  
 若要对 SMTP 服务器进行验证，则 SMTP 发送适配器可使用以下验证类型之一：  
  
-   **基本。** SMTP 服务器使用用户提供的凭据进行验证。  
  
-   **进程帐户 (NTLM)。** SMTP 服务器使用当前进程凭据进行验证。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置 SMTP 适配器](../core/configuring-the-smtp-adapter.md)  
  
-   [配置 SMTP 适配器时的限制](../core/restrictions-when-configuring-the-smtp-adapter.md)  
  
-   [SMTP 适配器安全建议](../core/smtp-adapter-security-recommendations.md)