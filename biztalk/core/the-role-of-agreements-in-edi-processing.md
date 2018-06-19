---
title: 协议在 EDI 处理过程中的角色 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d81b0449-6656-49f7-a781-5fd60031b3d5
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9986f22108382f1b1128079b8ff8c31902ca2979
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279933"
---
# <a name="the-role-of-agreements-in-edi-processing"></a>协议在 EDI 处理中的角色
组织使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 来从一个或多个贸易合作伙伴接收 EDI 消息，以及向其发送 EDI 消息。 然后贸易合作伙伴定义作为组织内业务实体的业务配置文件。 如何将业务配置文件交换消息定义为两个业务配置文件之间的贸易合作伙伴协议的一部分。 有关详细信息，请参阅[贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)。  
  
 在贸易合作伙伴管理 (TPM) 用户界面中创建一个贸易伙伴协议。 TPM 屏幕处于**方**节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="configuring-an-agreement-for-edi-processing"></a>为 EDI 处理配置协议  
 全部使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 交换 EDI 消息的贸易合作伙伴都必须就通信参数达成一致。 实现此目标之后，托管 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的组织必须在 TPM 中创建贸易合作伙伴，包括自己的贸易合作伙伴，创建业务配置文件，以及业务配置文件之间的贸易合作伙伴协议。 作为贸易合作伙伴协议的一部分，您可以就 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何从贸易合作伙伴的业务配置文件接收 EDI 消息，以及如何向其发送 EDI 消息来设置这些属性。 其他贸易合作伙伴也必须执行相同操作；若要交换消息，两端的配置必须兼容。  
  
 必须定义下列属性集，才能进行 EDI 通信。  
  
-   定义贸易合作伙伴的一般情况（如名称、发送端口以及签名证书）的贸易合作伙伴属性。  
  
-   定义业务标识的业务配置文件属性。  
  
-   作为贸易合作伙伴协议的一部分的 EDI 属性，定义了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将如何处理贸易合作伙伴的传入消息，以及如何生成将要发送到贸易合作伙伴的传出消息。  
  
-   作为贸易合作伙伴协议一部分的 AS2 属性，定义了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将如何执行传入和传出 AS2 通信。 仅当通过 AS2 发送 EDI 消息时，这些属性才会影响 EDI 通信。  
  
    > [!NOTE]
    >  将单独指定相同业务配置文件之间的 AS2 协议和 EDI 消息协议。 两个协议共同形成合作关系。  
  
 贸易合作伙伴协议属性确定以下特定处理：  
  
-   EDI 信封处理和生成  
  
-   确认处理和生成  
  
-   验证传入和传出的 EDI 消息  
  
-   批处理创建  
  
-   状态报告  
  
 对于业务标识，会有特定值，如**D-U-N-S （Bradstreet Dun)**。 特定名称具有特定限定符，例如“01”表示 Duns。 如果业务标识名不是特定的，则使用“ZZ”表示 X12 编码消息，使用“ZZZ”表示 EDIFACT 编码消息，指示由单独实体双方定义的名称。 然后，值和限定符标识业务配置文件。 业务标识名仅供参考；BizTalk 运行时在处理时不会使用业务标识名。  
  
## <a name="determining-an-agreement-for-edi-processing"></a>确定用于 EDI 处理的协议  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在接收 EDI 消息时都会尝试确定消息解析到的贸易合作伙伴协议。 它会通过将定义为协议一部分的发送方限定符、发送方标识符、接收方限定符、接收方标识符和消息进行匹配，以尝试解析贸易合作伙伴协议。 有关此过程的更多详细信息，请参阅[协议解析、 架构发现和接收 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在生成要发送的 EDI 消息时都会尝试确定与要接收该消息的业务配置文件相关联的协议。 它使用以下任何参数在消息和协议之间进行匹配，以尝试解析协议：  
  
-   上下文属性 AgreementPartIdForSend  
  
-   上下文属性 AgreementNameForSend、SenderPartyNameForSend 和 ReceiverPartyNameForSend  
  
-   发件人限定符和标识符，以及接收方限定符和标识符  
  
-   发送端口名称  
  
 有关此过程的更多详细信息，请参阅[协议解析和传出的 EDI 消息的架构确定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。  
  
## <a name="using-edi-global-properties"></a>使用 EDI 全局属性  
 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不能确定传入或传出消息的协议，它将使用备用协议来处理传入交换或生成传出交换。 后备协议设置，请右键单击**方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，单击**X12 回退设置**（对于 X12 编码消息） 或**EDIFACT 回退设置**（EDIFACT 编码消息）。 全局属性的详细信息，请参阅[配置全局或后备协议属性](../core/configuring-global-or-fallback-agreement-properties.md)。  
  
> [!NOTE]
>  只有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不能确定交换的协议时，才使用备用协议。 如果已确定协议，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将不会使用属性（没有为贸易合作伙伴之间的协议定义）的备用协议的属性值。  
  
 如果端口设置需要进行身份验证，则不会使用备用协议。 如果为接收端口的端口设置均需要身份验证 (如果**丢弃的消息，如果身份验证失败**或**身份验证失败时保留消息**上所选**常规**页**接收端口属性**对话框中)，协议是所必需的任何由接收端口收到的交换。 在这种情况下不使用备用协议。 如果未确定交换的协议，该交换将被视为验证失败，并且会被挂起。  
  
## <a name="see-also"></a>另请参阅  
 [协议解析、 架构发现和接收的 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)   
 [协议解析和传出的 EDI 消息的架构确定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)   
 [配置 EDI 属性](../core/configuring-edi-properties.md)   
 [配置全局或后备协议属性](../core/configuring-global-or-fallback-agreement-properties.md)   
 [EDI 方的已知的问题](../core/known-issues-with-edi-parties.md)