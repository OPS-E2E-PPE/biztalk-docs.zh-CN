---
title: SMTP 适配器安全建议 |Microsoft 文档
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
ms.openlocfilehash: ca1aeed0ad8c80cc32d333aeef37d1da6feabfc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276493"
---
# <a name="smtp-adapter-security-recommendations"></a>SMTP 适配器安全建议
使用 SMTP 适配器可以在运行 BizTalk Server 的服务器与其他应用程序之间通过简单邮件传输协议 (SMTP) 协议进行信息交换。 BizTalk Server 可以通过创建电子邮件并将其发送到指定的电子邮件地址来向其他应用程序发送消息。 只能将 SMTP 适配器用于发送消息。 有关 SMTP 适配器的详细信息，请参阅[SMTP 适配器](../core/smtp-adapter.md)。  
  
 在为运行 SMTP 适配器的主机实例配置服务帐户时，需要指定要对远程 SMTP 服务器使用的验证类型。 验证选项为：基本验证（明文）、NTLM（通过使用当前凭据）或无（如果 SMTP 服务器不要求验证）。  
  
 在使用 SMTP 适配器发送消息时，默认情况下，BizTalk Server 将以明文形式发送消息。 如果使用具有 S/MIME 编码器组件的管道，则可在将消息发送到 SMTP 服务器之前对该消息进行加密。 不过，SMTP 标头仍使用明文形式。  
  
 若要对 BizTalk Server 发送的电子邮件进行审核，则您应使用 SMTP 适配器连接到您自己的 SMTP 服务器，然后在其中对这些消息进行审核。  
  
 SMTP 适配器不支持安全套接字层 (SSL)。  
  
## <a name="see-also"></a>另请参阅  
 [用于接收和发送服务器端口](../core/ports-for-the-receive-and-send-servers.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)