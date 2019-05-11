---
title: SMTP 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, about SMTP adapters
- SMTP adapters, authenticating
- send adapters, SMTP adapters
- authenticating, SMTP adapters
- SMTP adapters
- SMTP adapters, send adapters
ms.assetid: b712f76d-3ce4-4780-9627-951e5951bd8a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76d3451ab6eb6d9dc52538f5b1b9289e2cb99d7a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314490"
---
# <a name="smtp-adapter"></a>SMTP 适配器
使用简单邮件传输协议 (SMTP) 适配器运行通过 SMTP 协议的 Microsoft BizTalk Server 和其他应用程序的服务器之间交换信息。 BizTalk Server 可以通过创建一封电子邮件并将它传递到指定的电子邮件地址，对其他应用程序发送消息。 在内部，SMTP 发送适配器创建基于 SMTP 的电子邮件消息，并将其发送到目标电子邮件地址。 目标电子邮件地址是 SMTP 适配器的属性。 配置 SMTP 发送端口时，BizTalk 浏览器中公开此属性。  
  
 SMTP 适配器支持的通配符字符**TO**， **FROM**，**抄送**并**使用者**属性，并将它们解析为其实际值。 如果中的通配符**TO**， **FROM**，并**CC**无法解析属性，SMTP 传输记录错误并将消息置于挂起队列或将该消息重定向到备份传输。 如果不能在中解析的通配符**使用者**属性，将消息发送与**主题**属性中指定的属性 （例如，"消息 %messageid%")。  
  
 默认情况下，SMTP 消息的消息文本为纯文本。 若要在消息正文中使用 HTML，可以配置的适配器的消息文本中使用某一 HTML 文件的内容。  
  
 有关 SMTP 安全问题的详细信息，请参阅[SMTP 适配器的安全建议](../core/smtp-adapter-security-recommendations.md)。  
  
 SMTP 适配器包含只有一个适配器，发送适配器。 发送适配器控制使用 SMTP 适配器的发送端口。  
  
 本主题讨论通过 SMTP 发送适配器消息流。  
  
 **SMTP 发送适配器**  
  
 SMTP 从服务器发送适配器获取消息，并将它们发布到 SMTP 服务器发送这些电子邮件收件人。 从 BizTalk 消息对象正文部分、 指定的文件，或配置适配器时是可用的对话框中输入文本，将 SMTP 发送适配器获取消息内容。  
  
 SMTP 发送适配器将消息成功发布到 SMTP 服务器上后，SMTP 发送适配器从 MessageBox 数据库中删除该消息。  
  
 SMTP 发送适配器可以请求送达通知和阅读回执通过 SMTP 发送适配器发送的消息。 SMTP 适配器将通知和阅读回执传送到指定对 SMTP 地址**从**标头。  
  
 **SMTP 服务器的身份验证**  
  
 如果需要 SMTP 服务器身份验证，则 SMTP 发送适配器将使用以下身份验证类型之一：  
  
-   **基本。** SMTP 服务器使用用户提供的凭据进行身份验证。  
  
-   **进程帐户 (NTLM)。** SMTP 服务器使用当前进程凭据进行身份验证。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置 SMTP 适配器](../core/configuring-the-smtp-adapter.md)  
  
-   [配置 SMTP 适配器时的限制](../core/restrictions-when-configuring-the-smtp-adapter.md)  
  
-   [SMTP 适配器的安全建议](../core/smtp-adapter-security-recommendations.md)