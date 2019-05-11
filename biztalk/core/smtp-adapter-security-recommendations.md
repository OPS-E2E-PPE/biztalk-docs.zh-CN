---
title: SMTP 适配器的安全建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], security
- SMTP adapters, security
- security, SMTP adapters
ms.assetid: 45f13744-a0eb-4b4e-85cd-6b862b384ad5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1b89406529c2a112d667888a67df02e9ab9a693
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314406"
---
# <a name="smtp-adapter-security-recommendations"></a>SMTP 适配器的安全建议
SMTP 适配器用于运行 BizTalk Server 和其他应用程序通过简单邮件传输协议 (SMTP) 协议的服务器之间交换信息。 BizTalk Server 可以通过创建一封电子邮件并将它传递到指定的电子邮件地址，对其他应用程序发送消息。 您可以使用 SMTP 适配器仅用于发送消息。 有关 SMTP 适配器的详细信息，请参阅[SMTP 适配器](../core/smtp-adapter.md)。  
  
 在配置为运行 SMTP 适配器的主机实例的服务帐户时，需要指定想要使用远程 SMTP 服务器的身份验证的类型。 如果 SMTP 服务器不要求身份验证，身份验证选项是基本身份验证 （明文）、 NTLM （通过使用当前凭据） 或 none。  
  
 当使用 SMTP 适配器发送一条消息时，BizTalk Server 将消息以明文形式发送默认情况下。 如果使用具有 S/MIME 编码器组件的管道，可以加密消息前将其发送到 SMTP 服务器。 但是，SMTP 标头是仍以明文形式。  
  
 如果你想要审核的 BizTalk Server 发送的电子邮件消息，您应使用 SMTP 适配器连接到您自己的 SMTP 服务器，然后可以审核消息。  
  
 SMTP 适配器不支持安全套接字层 (SSL)。  
  
## <a name="see-also"></a>请参阅  
 [用于接收和发送服务器端口](../core/ports-for-the-receive-and-send-servers.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)