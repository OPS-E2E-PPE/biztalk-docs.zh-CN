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
ms.openlocfilehash: b6b5b93332f74743c4798f0ce821794d29e5262c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394054"
---
# <a name="the-role-of-agreements-in-as2-processing"></a>协议在 AS2 处理中的角色
组织使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来接收 AS2 消息，以及发送 AS2 消息，一个或多个贸易合作伙伴。 贸易合作伙伴，又定义是在组织内的业务实体的业务配置文件。 在两个业务配置文件属于不同贸易合作伙伴之间的双向贸易合作伙伴协议中设置 AS2 属性。  
  
 贸易合作伙伴管理 (TPM) 用户界面中，可以创建贸易合作伙伴协议。 TPM 屏幕位于**参与方**节点的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 有关贸易合作伙伴如何的详细信息，业务配置文件和协议一起形成 TPM 解决方案，请参阅[贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)。  
  
## <a name="configuring-an-agreement-for-as2-processing"></a>为 AS2 处理配置协议  
 任何时候贸易合作伙伴接收 AS2 消息，或向另一个贸易合作伙伴发送 AS2 消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]AS2 接收管道或 AS2 发送管道将处理该消息根据两个贸易之间的 AS2 协议属性合作伙伴。 可以配置的 AS2 属性的定义方式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将执行传入和传出的 AS2 通信。  
  
> [!NOTE]
>  不同于在 EDI 处理中，有没有备用 AS2 协议的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如果它无法确定协议，可以使用。 AS2 接收或发送管道将处理该消息，仅当确定了协议。  
> 
> [!NOTE]
>  AS2 协议在 EDI 协议中单独配置。 当接收文档，AS2 协议在 AS2 处理过程中得到解决，然后 EDI 协议可解析单独在 EDI 处理过程。 这两个协议共同构成合作关系。 有关详细信息请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。  
> 
> [!NOTE]
>  这些属性用于定义常规方面的参与方，如名称和别名、 发送端口和签名证书指定为贸易合作伙伴的属性的一部分。  
  
 可用于 HTTP/HTTPS 传输 EDIINT/AS2 编码的消息或非 EDI AS2 编码的消息通过。 如果通过 HTTP/HTTPS 传输传送 EDIINT/AS2 编码的消息，将应用协议的 EDI 属性。  
  
 本组织的签名证书中定义**证书**页**BizTalk 组-组属性**对话框。 此外，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使你可以覆盖默认值通过定义为协议属性的一部分的证书签名的 AS2 消息的证书。  若要定义特定协议的不同的证书，请使用**签名证书**页中的单向 AS2 协议**协议属性**对话框。 有关如何指定不同的证书的说明，请参阅[配置签名证书 (AS2)](../core/configuring-signature-certificates-as2.md)。  
  
## <a name="determining-an-agreement-for-as2-processing"></a>确定用于 AS2 处理的协议  
 时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收 AS2 编码的消息，它会尝试确定参与方发送消息的匹配 AS2-From 标头与 AS2-从参与方的单向协议中的协议设置。 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送 AS2 编码的消息，它会尝试确定将通过匹配 AS2 接收该消息的参与方-To 标头与 AS2-To 协议属性中的参与方的单向协议。 有关详细信息，请参阅[传入 AS2 消息的协议解析](../core/agreement-resolution-for-incoming-as2-messages.md)或[传出 AS2 消息的协议解析](../core/agreement-resolution-for-outgoing-as2-messages.md)。  
  
## <a name="see-also"></a>请参阅  
 [传入 AS2 消息的协议解析](../core/agreement-resolution-for-incoming-as2-messages.md)   
 [对传出 AS2 消息的协议解析](../core/agreement-resolution-for-outgoing-as2-messages.md)   
 [配置 AS2 属性](../core/configuring-as2-properties.md)