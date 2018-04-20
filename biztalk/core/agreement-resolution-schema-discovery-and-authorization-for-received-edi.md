---
title: 协议解析、 架构发现和接收的 EDI 消息的授权 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 503e307c-4cb0-49b5-8751-82dcea203151
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de5f7fd9b022daf2d123de1c971797b53df202d5
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="agreement-resolution-schema-discovery-and-authorization-for-received-edi-messages"></a>接收到的 EDI 消息的协议解析、架构发现和授权
当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 收到 EDI 消息时，EDI 接收管道将执行贸易合作伙伴协议查找、架构发现和授权过程以确定如何处理消息。  
  
## <a name="agreement-resolution"></a>协议解析  
 EDI 接收管道执行贸易合作伙伴协议解析的方法是：通过执行一系列的步骤来确定消息中的标头字段与协议定义中的属性之间是否匹配。 一旦 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 确定协议，便可确定适用于交换的文档架构（见下文）。 它使用与匹配协议关联的属性及相关架构来验证并处理接收的消息。  
  
 若要执行协议解析，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将按照以下方式继续进行操作：  
  
1.  通过将数据交换标头中的发送方限定符和标识符及接收方限定符和标识符与协议属性中的相应内容进行匹配来解析协议。  
  
2.  如果第 1 步不成功，则仅通过将数据交换标头中的发送方限定符和标识符与协议属性中的相应内容进行匹配来解析协议。 此外，由于第一步未成功，因此可以放心地假定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会收到该消息。 因此，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会尝试将接收方限定符和标识符与以下值匹配：  
  
    -   值“BT”和“HostX12Recvr”（适用于 X12 编码的消息）以及  
  
    -   值“BT”和“HostEdifactRecvr”（适用于 EDIFACT 编码的消息）  
  
    > [!IMPORTANT]
    >  -   **BizTalk Server 2013 R2，2013年和 2010年**: ISA5、 ISA6、 ISA7、 ISA8、 UNB2.1、 UNB2.2、 UNB3.1 和 UNB3.2 字段是必需的协议设置中。  
    > -   **BizTalk Server 2009 和 2006 R2**: ISA7、 ISA8、 UNB3.1 和 UNB3.2 字段不是必需的方设置中。 如果这些字段保留为空，则 EDI 引擎将根据 ISA5、ISA6、UNB2.1 和 UNB2.2 的值提供解析。  
    > -   若要支持从 BizTalk Server 2009 和 2006 R2 解析到 BizTalk Server 的更新版本，请引入硬编码 ID（HostX12Recvr 和 HostEdifactRecvr）和限定符 (BT)。  
    > -   EDIFACT 消息应遵循 [UNECE 准则](http://www.unece.org/tradewelcome/areas-of-work/un-centre-for-trade-facilitation-and-e-business-uncefact/outputs/standards/unedifact/tradeedifactrules.html) 消息语法和规则。  
  
3.  如果第 2 步不成功，则使用后备协议属性。  
  
 在第一步中，对于 X12，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将使用以下值来进行匹配：  
  
-   ISA05（发送方限定符）  
  
-   ISA06（发送方标识符）  
  
-   ISA07（接收方限定符）  
  
-   ISA08（接收方标识符）  
  
 对于 EDIFACT，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将使用以下值进行匹配：  
  
-   UNB2.1（发送方标识符）  
  
-   UNB2.2（发送方限定符）  
  
-   UNB3.1（接收方标识符）  
  
-   UNB3.2（接收方限定符）  
  
 在中定义用于匹配的协议属性 **标识符** 的方向特定协议选项卡页 **协议属性** 对话框。  
  
 这四个接收端和发送端属性唯一标识贸易合作伙伴协议。 使用这四个属性可以更灵活地处理接收端。 例如，利用这种协议解析的方法，你可以向多个参与方发送确认，而无需创建多个发送端口。  
  
 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用所有这四个发送方和接收方限定符及标识符都不能解析协议，它将尝试只使用发送方限定符和标识符来解析协议。 对于 X12，这些字段为 ISA05 和 ISA06；对于 EDIFACT，这些字段为 UNB2.1 和 UNB2.2。 与发送者和接收者属性匹配[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与中定义的协议属性相匹配的交换标头中的值**标识符**方向特定协议选项卡页**协议属性**对话框。 如果只有发件人限定符和标识符用于解析协议，应的双向协议选项卡中定义的接收方限定符和标识符 **协议属性** 对话框。  
  
 如果找不到协议，则除非端口设置要求验证，否则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将使用备用贸易合作伙伴协议。 如果端口设置要求身份验证 (如果 **丢弃的消息，如果身份验证失败** 或 **身份验证失败时保留消息** 上所选 **常规** 页 **接收端口属性**)，协议是所必需的任何由接收端口收到的交换。 在这种情况下，如果未通过匹配交换标头与协议属性来解析协议，则不允许使用备用协议属性来确定协议。 交换将被视为与找不到协议时验证失败一样处理，并且会被挂起。  
  
> [!NOTE]
>  EDI 管道中的消息将转到协议解析中的后续步骤，直到该消息在协议处于启用状态的情况下通过相应步骤得到解析。 例如，如果消息在协议解析的第一步中得到解析，但协议处于禁用状态，则消息将转到后续步骤进行解析。  
  
## <a name="schema-discovery"></a>架构发现  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 确定解析为消息的协议之后，必须确定要用于验证和处理消息的架构。 它会使用在中标识的属性 **本地主机设置** 页 （发送方） 的单向协议选项卡 **协议属性** 对话框。  
  
 若要确定架构，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 必须先确定架构命名空间。 EDI 拆装器将使用与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 一起提供的标准架构的默认命名空间，或者确定要用于自定义架构的命名空间。  
  
 **本地主机设置** 的单向协议选项卡页 **协议属性** 对话框中，你可以设置的值网格来确定自定义的命名空间。 如果未找到匹配项是在该网格中，EDI 反汇编程序将使用默认命名空间中的 **目标命名空间** 字段标记为默认行。  
  
### <a name="x12-schema-discovery"></a>X12 架构发现  
 对于 X12 编码的消息，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可使用传入交换标头中的应用程序发送方标识符 (GS02) 和事务集 ID (ST01) 来确定自定义命名空间。 它尝试在 GS02 和 ST01 属性查找这些值与值之间的匹配 **自定义目标命名空间** 网格中的 **本地主机设置** 页 (下 **事务设置设置**) 的双向协议选项卡 **协议属性** 对话框。 如果它找到的匹配项，它将使用在同一行的网格中标识的目标命名空间来确定与我们验证和处理消息的架构。 如果目标命名空间不确定，则使用默认的目标命名空间。 如果没有命名空间标识中**目标命名空间**字段标记为默认行中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将使用它们的默认值X12编码消息的回退协议属性中标识的目标命名空间`http://schemas.microsoft.com/BizTalk/Edi/X12/2006`.  
  
 对于 X12 交换，在发现目标命名空间后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 便可使用以下信息来确定架构：  
  
-   刚发现的目标命名空间  
  
-   ST03（如果 GS07 == X - 公认标准委员会 X12）的前五个字符中的版本/发行版。 如果 ST03 不存在/无效或者没有产生架构解析，则版本将由 GS08 或 ISA12（如果 GS07 != X）的前五个字符来确定。  
  
-   ST01 中的 DocType。  
  
 EDI 拆装器将连接编码类型、版本/发行版和 DocType 来确定架构名称，例如“X12_00401_864”。 然后再连接目标命名空间与该架构名称，例如 `http://schemas.microsoft.com/BizTalk/Edi/X12/2006/X12#X12_00401_864`。  
  
 对于一个传入 HIPAA 837 交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持以下三种 HIPAA 837 架构：  
  
|837 架构|版本 4010 中的 GS08 值|版本 5010 中的 GS08/ST03 值|  
|----------------|--------------------------------|--------------------------------------|  
|Claim-Dental_837D|004010X097A1|005010X224A1|  
|Claim-Institutional_837I|004010X096A1|005010X223A1|  
|Claim-Professional_837P|004010X098A1|005010X222|  
  
> [!NOTE]
>  在 HIPAA 版本中，对于事务集 278（医疗保健服务审核），请求和响应对共享相同的 GS08 和 ST01 值。 根据 BHT02 字段中的触发器值，你可以区分版本 5010 中的 278 请求/响应：  
>   
>  1.  BHT02 中的任一值 01、13 和 36 都表示医疗保健服务审核请求  
> 2.  BHT02 中的 11 表示医疗保健服务审核响应  
  
### <a name="edifact-schema-discovery"></a>EDIFACT 架构发现  
 对于 EDIFACT 编码的消息，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 通过传入交换标头中的以下信息确定自定义命名空间：消息类型 (UNH2.1)、消息版本号 (UNH2.2)、消息发行版号 (UNH2.3)、指定代码 (UNH2.5)、功能组 ID (UNG2.1) 和应用程序发送代码限定符 (UNG2.2)。 它会尝试 UNH2.1、 UNH2.2、 UNH2.3、 UNH2.5、 UNG2.1，和 UNG2.2 中为属性查找这些值与值之间的匹配 **自定义目标命名空间** 网格 (下 **事务设置设置**) 的双向协议选项卡 **协议属性** 对话框。 如果它找到的匹配项，它将使用在同一行的网格中标识的目标命名空间来确定要用于验证和处理消息的架构。 如果目标命名空间不确定，则使用默认的目标命名空间。 如果没有命名空间标识中**目标命名空间**字段标记为默认行中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将使用的目标命名空间中的 EDIFACT 编码消息的回退协议属性标识它们的默认值为`http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006`.  
  
 对于 EDIFACT 交换，一旦发现目标命名空间，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 便可使用以下信息来确定架构：  
  
-   刚发现的目标命名空间。  
  
-   UNH2.2 中的消息版本号。  
  
-   UNH2.3 中的消息版本号。  
  
-   UNH2.1 中的消息类型。  
  
-   UNH2.5 中分配的代码。  
  
 EDI 拆装器将连接编码类型、版本号、发行版号和消息类型来确定架构名称，例如“EFACT_D94A_CONTEN”。 然后再连接目标命名空间与该架构名称，例如 `http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006/EFACT#EFACT_D94A_CONTEN`。  
  
 如果消息中存在 UNH2.5，则 EDI 拆装器将首先尝试使用 UNH2.5 的值作为架构名称的一部分（如“EFACT_D94A_CONTEN_TEST”）来查找匹配架构。 如果找不到任何匹配架构，则 EDI 拆装器将进行回退，以查找无 UNH2.5 值的架构。  
  
## <a name="authorization"></a>授权  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用消息中的字段来检查为协议定义的授权字段和安全字段的值。 如果存在不匹配项，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将挂起交换。 对于 EDIFACT 编码消息，这些字段是收件人引用密码（UNB6.1 和 UNB6.2）。 对于 X12 编码消息，这些字段是授权限定符和信息 (ISA1-2) 以及安全限定符和信息 (ISA3-4)。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 如何接收 EDI 消息](../core/how-biztalk-server-receives-edi-messages.md)