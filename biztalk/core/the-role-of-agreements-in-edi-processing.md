---
title: 协议在 EDI 处理中的角色 |Microsoft Docs
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
ms.openlocfilehash: f289a6cf08090628c73601eff672cf48f677428c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531213"
---
# <a name="the-role-of-agreements-in-edi-processing"></a>协议在 EDI 处理中的角色
组织使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来接收 EDI 消息，以及发送 EDI 消息，一个或多个贸易合作伙伴。 贸易合作伙伴，又定义是在组织内的业务实体的业务配置文件。 如何业务配置文件交换消息定义为一部分的贸易合作伙伴两个业务配置文件之间的协议。 有关详细信息，请参阅[贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)。  
  
 在贸易合作伙伴管理 (TPM) 用户界面中创建贸易合作伙伴协议。 TPM 屏幕位于**参与方**节点的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="configuring-an-agreement-for-edi-processing"></a>为 EDI 处理配置协议  
 将交换 EDI 消息使用的所有贸易合作伙伴[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须就通信参数达成。 它们执行此操作之后, 组织承载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须创建 TPM （包括贸易合作伙伴为本身） 中的贸易合作伙伴、 创建业务配置文件和业务配置文件之间的贸易合作伙伴协议。 作为贸易合作伙伴协议的一部分，设置的属性如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收 EDI 消息，并将 EDI 消息发送到贸易合作伙伴的业务配置文件。 他们一端其他贸易合作伙伴必须执行相同操作，并交换消息，配置必须兼容。  
  
 必须定义下列进行 EDI 通信的属性集。  
  
- 定义贸易合作伙伴，例如名称、 的一般情况的贸易合作伙伴属性发送端口以及签名证书。  
  
- 定义业务标识的业务配置文件属性。  
  
- EDI 属性作为贸易合作伙伴协议的一部分，它定义如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将处理来自贸易合作伙伴以及如何生成绑定到贸易合作伙伴的传出消息的传入消息。  
  
- AS2 属性作为贸易合作伙伴协议的一部分，它定义如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将执行传入和传出的 AS2 通信。 仅当通过 AS2 发送 EDI 消息时，这些属性会影响 EDI 通信。  
  
  > [!NOTE]
  >  单独指定 AS2 协议和 EDI 消息传递协议之间的相同业务配置文件。 两个协议共同形成合作关系。  
  
  贸易合作伙伴协议属性确定以下特定处理：  
  
- EDI 信封处理和生成  
  
- 确认处理和生成  
  
- 验证传入和传出 EDI 消息  
  
- 批处理创建  
  
- 状态报告  
  
  有关业务标识，可以有特定值，如**D-U-N-S (Dun & Bradstreet)**。 特定名称具有特定限定符，例如"01"表示 Duns。 如果业务标识名不是特定的"ZZ"用于 X12 编码的消息，"ZZZ"使用 EDIFACT 编码的消息，指示由单独实体双方定义的名称。 然后，值和限定符标识业务配置文件。 业务标识的名称是为仅供参考;它不用于 BizTalk 运行时处理。  
  
## <a name="determining-an-agreement-for-edi-processing"></a>确定用于 EDI 处理的协议  
 任何时候[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收 EDI 消息时，它会尝试确定消息解析到的贸易合作伙伴协议。 它尝试解析贸易合作伙伴协议之间消息的发送方限定符、 发送方标识符、 接收方限定符和接收方标识符定义为协议的一部分进行匹配。 此过程的更多详细信息，请参阅[协议解析、 架构发现和收到的 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。  
  
 任何时候[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会生成 EDI 消息发送时，它会尝试确定将向其发送消息的业务配置文件相关联的协议。 它会尝试来解析协议，从而将消息与使用以下任一协议相匹配：  
  
- 上下文属性 AgreementPartIdForSend  
  
- 上下文属性 AgreementNameForSend、 SenderPartyNameForSend 和 ReceiverPartyNameForSend  
  
- 发送方限定符和标识符和接收方限定符和标识符  
  
- 发送端口名称  
  
  此过程的更多详细信息，请参阅[协议解析和架构确定传出 EDI 消息的](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。  
  
## <a name="using-edi-global-properties"></a>使用 EDI 全局属性  
 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法确定协议传入或传出消息，它将使用回退协议来处理传入的交换或生成传出交换。 通过右键单击来设置备用协议**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，然后单击**X12 回退设置**（对于 X12 编码的消息） 或**EDIFACT 后备设置**（EDIFACT 编码的消息）。 有关全局属性的详细信息，请参阅[配置全局或后备协议属性](../core/configuring-global-or-fallback-agreement-properties.md)。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将使用后备协议，仅当它不能确定交换的协议。 如果已确定协议，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将不使用尚未针对两个贸易合作伙伴之间的协议定义的属性的备用协议属性值。  
  
 如果端口设置需要进行身份验证，则不使用备用协议。 如果接收端口的端口设置要求验证 (如果**身份验证失败时删除消息**或**身份验证失败时保留消息**上选择**常规**页的**接收端口属性**对话框)，协议是必需的接收端口接收的任何交换。 在这种情况下，不使用备用协议。 如果不存在的协议确定的交换，交换将被视为与身份验证失败，并且将被挂起。  
  
## <a name="see-also"></a>请参阅  
 [协议解析、 架构发现和接收的 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)   
 [协议解析和传出 EDI 消息的架构确定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)   
 [配置 EDI 属性](../core/configuring-edi-properties.md)   
 [配置全局或后备协议属性](../core/configuring-global-or-fallback-agreement-properties.md)   
 [EDI 参与方的已知问题](../core/known-issues-with-edi-parties.md)