---
title: 协议在 AS2 处理中的角色 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb6a6fe1-8fb4-4998-a1b4-aadad7e672c4
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4214fe58c10839bcabbd37437002072eae4ad6a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976902"
---
# <a name="the-role-of-agreements-in-as2-processing"></a>协议在 AS2 处理中的角色
组织使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 来从一个或多个贸易合作伙伴接收 AS2 消息，以及向其发送 AS2 消息。 然后贸易合作伙伴定义作为组织内业务实体的业务配置文件。 您在属于不同贸易合作伙伴的两个业务配置文件之间的双向贸易合作伙伴协议中设置 AS2 属性。  
  
 可在贸易合作伙伴管理 (TPM) 用户界面中创建贸易合作伙伴协议。 TPM 屏幕位于**参与方**节点的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 有关贸易合作伙伴如何的详细信息，业务配置文件和协议一起形成 TPM 解决方案，请参阅[贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)。  
  
## <a name="configuring-an-agreement-for-as2-processing"></a>为 AS2 处理配置协议  
 只要一个贸易合作伙伴接收来自另一个贸易伙伴的 AS2 消息或者将 AS2 消息发送至另一个贸易合作伙伴，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] AS2 接收管道或 AS2 发送管道都将按照这两个贸易合作伙伴之间的 AS2 协议属性来处理相应消息。 可配置用于定义 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将如何执行 AS2 通信（传入和传出）的 AS2 属性。  
  
> [!NOTE]
>  与 EDI 处理过程不同，如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法确定协议，它没有任何可以使用的备用 AS2 协议。 只有在确定了协议的情况下，AS2 接收或发送管道才将处理该消息。  
> 
> [!NOTE]
>  AS2 协议是独立于 EDI 协议配置的。 在接收文档时，在 AS2 处理过程中解析 AS2 协议，然后在 EDI 处理过程中单独解析 EDI 协议。 这两个协议共同构成合作关系。 有关详细信息请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。  
> 
> [!NOTE]
>  将定义参与方的一般情况（如名称和别名、发送端口以及签名证书）的属性指定为贸易合作伙伴的属性的一部分。  
  
 可以对 EDIINT/AS2 编码的消息或非 AS2 编码的 EDI 消息使用 HTTP/HTTPS 传输。 如果通过 HTTP/HTTPS 传输传送 EDIINT/AS2 编码的消息，则将应用协议的 EDI 属性。  
  
 本组织的签名证书中定义**证书**页**BizTalk 组-组属性**对话框。 此外，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 还使您能够通过将证书定义为协议属性的一部分，来覆盖 AS2 消息的默认签名证书。  若要定义特定协议的不同的证书，请使用**签名证书**页中的单向 AS2 协议**协议属性**对话框。 有关如何指定不同的证书的说明，请参阅[配置签名证书 (AS2)](../core/configuring-signature-certificates-as2.md)。  
  
## <a name="determining-an-agreement-for-as2-processing"></a>确定用于 AS2 处理的协议  
 当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收 AS2 编码的消息时，它会尝试通过将 AS2-From 标头与参与方的单向协议中的 AS2-From 协议设置匹配，来确定发送该消息的参与方。 当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送 AS2 编码的消息时，它会尝试通过将 AS2-To 标头与参与方的单向协议中的 AS2-To 协议属性匹配，来确定将接收该消息的参与方。 有关详细信息，请参阅[传入 AS2 消息的协议解析](../core/agreement-resolution-for-incoming-as2-messages.md)或[传出 AS2 消息的协议解析](../core/agreement-resolution-for-outgoing-as2-messages.md)。  
  
## <a name="see-also"></a>请参阅  
 [传入 AS2 消息的协议解析](../core/agreement-resolution-for-incoming-as2-messages.md)   
 [对传出 AS2 消息的协议解析](../core/agreement-resolution-for-outgoing-as2-messages.md)   
 [配置 AS2 属性](../core/configuring-as2-properties.md)