---
title: 协议解析、 架构发现和接收的 EDI 消息的授权 |Microsoft Docs
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
ms.openlocfilehash: e82722ddb6adfcd3e0f8c5d24050bb58471da378
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359640"
---
# <a name="agreement-resolution-schema-discovery-and-authorization-for-received-edi-messages"></a>协议解析、 架构发现和接收的 EDI 消息的授权
当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收 EDI 消息时，EDI 接收管道执行贸易合作伙伴协议查找、 架构发现和授权过程以确定如何处理该消息。  
  
## <a name="agreement-resolution"></a>协议解析  
 EDI 接收管道执行贸易合作伙伴协议解析，通过执行一系列步骤来确定是否存在消息中的标头字段与协议定义中的属性相匹配。 一次[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]已确定协议，它确定适用于交换 （见下文） 的文档架构。 它使用与匹配协议和相关的架构相关联的属性来验证并处理接收的消息。  
  
 若要执行协议解析[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]继续，如下所示：  
  
1. 通过匹配发送方限定符和标识符和接收方限定符和标识符与协议属性中的交换标头中来解析协议。  
  
2. 如果第 1 步不成功，进行匹配的发送方限定符和标识符与协议属性中交换标头中的来解析协议。 此外，因为第一步未成功，则可以安全地假定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将接收消息。 因此，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]尝试与接收方限定符和标识符与以下匹配：  
  
   -   值"BT"和"HostX12Recvr"（适用于 X12 编码的消息） 和  
  
   -   值"BT"和"HostEdifactRecvr"（适用于 EDIFACT 编码的消息）  
  
   > [!IMPORTANT]
   > - **BizTalk Server 2013 R2，2013年和 2010年**:ISA5、 ISA6、 ISA7、 ISA8、 UNB2.1、 UNB2.2、 UNB3.1 和 UNB3.2 字段是必需的协议设置中。  
   >   -   **BizTalk Server 2009 和 2006 R2**:ISA7、 ISA8、 UNB3.1 和 UNB3.2 字段不是参与方设置中必需的。 如果这些字段保留为空，则 EDI 引擎提供 ISA5、 ISA6、 UNB2.1 和 UNB2.2 的值为基础的解析。  
   >   -   若要支持从 BizTalk Server 2009 和 2006 R2 与较新版本的 BizTalk Server 的解决方法，硬编码 （HostX12Recvr 和 HostEdifactRecvr） 和限定符 (BT) 引入。  
   >   -   EDIFACT 消息应遵循[UNECE 准则](http://www.unece.org/tradewelcome/areas-of-work/un-centre-for-trade-facilitation-and-e-business-uncefact/outputs/standards/unedifact/tradeedifactrules.html)消息语法和规则。  
  
3. 如果第 2 步不成功，则使用后备协议属性。  
  
   在第一个步骤中，对于 X12，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将使用以下值来执行匹配：  
  
- ISA05 （发送方限定符）  
  
- ISA06 （发送方标识符）  
  
- ISA07 （接收方限定符）  
  
- ISA08 （接收方标识符）  
  
  对于 EDIFACT，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将使用以下值来执行匹配：  
  
- UNB2.1 （发送方标识符）  
  
- UNB2.2 （发送方限定符）  
  
- UNB3.1 （接收方标识符）  
  
- UNB3.2 （接收方限定符）  
  
  用于匹配的协议属性中定义**标识符**方向特定协议选项卡的页面**协议属性**对话框。  
  
  这四个接收方和发送端属性唯一地标识贸易合作伙伴协议。 使用四个属性可以更大的灵活性在接收端处理。 例如，这种协议解析的方法可能，可将发送到多个参与方，而无需创建多个确认的发送端口。  
  
  如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不能解析协议使用所有四个发送方和接收方限定符和标识符，它将尝试解析协议只使用发送方限定符和标识符。 对于 X12，这些字段为 ISA05 和 ISA06;对于 EDIFACT，这些字段为 UNB2.1 和 UNB2.2。 与发送方和接收方属性匹配一样[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]交换标头中的值匹配与协议属性中定义**标识符**的方向特定的协议选项卡页**协议属性**对话框。 如果只使用发送方限定符和标识符来解析协议，接收方限定符和标识符应未定义的双向协议选项卡中**协议属性**对话框。  
  
  如果不找到任何协议，则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用备用贸易合作伙伴协议中，除非端口设置要求身份验证。 如果端口设置要求验证 (如果**身份验证失败时删除消息**或**身份验证失败时保留消息**上选择**常规**页**接收端口属性**)，协议是必需的接收端口接收的任何交换。 在这种情况下，如果不通过匹配交换标头与协议属性来解析协议，使用后备协议属性来确定协议不是允许。 交换将被视为与身份验证已失败，如果不找到任何协议，并且将被挂起。  
  
> [!NOTE]
>  EDI 管道中的消息将转到后续步骤协议中解析直到该消息通过相应步骤得到处于启用状态的协议解析。 例如，如果消息的协议解析的第一步中得到解析，但协议处于禁用状态则消息将转到后续步骤进行解析。  
  
## <a name="schema-discovery"></a>架构发现  
 之后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]已确定解析消息，则它必须确定它应使用验证和处理消息的架构的协议。 它是使用中标识的属性**本地主机设置**页的单向 （发送端） 的协议选项卡**协议属性**对话框。  
  
 若要确定架构，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须首先确定架构命名空间。 EDI 拆装器将使用默认命名空间的标准架构附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，或者确定要用于自定义架构的命名空间。  
  
 **本地主机设置**页的单向协议选项卡**协议属性**对话框中，您可以设置网格的值来确定自定义的命名空间。 如果在该网格中不找到任何匹配项，EDI 拆装器将使用默认的命名空间中**目标命名空间**字段标记为默认行。  
  
### <a name="x12-schema-discovery"></a>X12 架构发现  
 对于 X12 编码的消息，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]确定自定义命名空间使用的应用程序发送方标识符 (GS02) 和事务集 ID (ST01) 从传入的交换标头。 它会尝试查找这些值与值之间的匹配中的 GS02 和 ST01 属性**自定义目标命名空间**中的网格**本地主机设置**页面 (下**事务集设置**) 的双向协议选项卡的**协议属性**对话框。 如果它找到的匹配项，它将使用网格的同一行中的目标命名空间来确定用于验证和处理消息的架构。 如果不确定的目标命名空间，则将使用默认目标命名空间。 如果在不确定任何命名空间**目标命名空间**字段标记为默认行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将使用默认情况下X12编码的消息，备用协议属性中标识的目标命名空间`http://schemas.microsoft.com/BizTalk/Edi/X12/2006`.  
  
 对于 X12 交换后发现的目标命名空间，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用以下信息来确定架构：  
  
- 只是发现的目标命名空间  
  
- 版本/发行版中的前五个字符的 ST03 (如果 GS07 = = X-公认标准委员会 X12)。 如果 ST03 不存在/无效或者不会产生架构解析，则版本由前五个字符的 GS08 或 ISA12 (如果 GS07 ！ = X)。  
  
- ST01 中的 DocType。  
  
  EDI 拆装器将连接编码类型、 版本/发行版和 DocType 来确定架构名称，例如，"X12_00401_864"。 它然后再连接目标命名空间与架构名称，例如， `http://schemas.microsoft.com/BizTalk/Edi/X12/2006/X12#X12_00401_864`。  
  
  对于传入 HIPAA 837 交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持三种 HIPAA 837 架构：  
  
|837 架构|版本 4010 中的 GS08 值|版本 5010 中的 GS08/ST03 值|  
|----------------|--------------------------------|--------------------------------------|  
|Claim-Dental_837D|004010X097A1|005010X224A1|  
|Claim-Institutional_837I|004010X096A1|005010X223A1|  
|Claim-Professional_837P|004010X098A1|005010X222|  
  
> [!NOTE]
>  在 HIPAA 版本中，为事务集 278 （医疗保健服务审核），请求和响应对的 GS08 和 ST01 共享相同的值。 具体取决于你可以区分 278 BHT02 字段中的触发器值请求 / 响应版本 5010 中：  
> 
> 1. 任一值 01、 13 和 36 BHT02 中的表示医疗保健服务审核请求  
>    2.  BHT02 中的 11 表示医疗保健服务审核响应  
  
### <a name="edifact-schema-discovery"></a>EDIFACT 架构发现  
 对于 EDIFACT 编码的消息，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]确定自定义命名空间： 使用消息类型 (UNH2.1)、 消息版本号 (UNH2.2)、 消息发行版号 (UNH2.3)、 分配的代码 (UNH2.5)、 功能组 ID (UNG2.1) 和应用程序发送代码从传入的交换标头中的限定符 (UNG2.2)。 它会尝试查找这些值与值之间的匹配中的 UNH2.1、 UNH2.2、 UNH2.3、 UNH2.5、 UNG2.1 和 UNG2.2 属性**自定义目标命名空间**网格 (下**事务集设置**)双向协议选项卡的**协议属性**对话框。 如果它找到的匹配项，它将使用网格的同一行中的目标命名空间来确定要用于验证和处理消息的架构。 如果不确定的目标命名空间，则将使用默认目标命名空间。 如果在不确定任何命名空间**目标命名空间**字段标记为默认行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将使用目标命名空间对于 EDIFACT 编码的消息，后备协议属性中默认情况下为`http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006`.  
  
 对于 EDIFACT 交换，一旦发现目标命名空间，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用以下信息来确定架构：  
  
- 只是发现的目标命名空间。  
  
- UNH2.2 中的消息版本数。  
  
- UNH2.3 中的消息发行版号。  
  
- UNH2.1 中的消息类型。  
  
- UNH2.5 中分配的代码。  
  
  EDI 拆装器将连接编码类型、 版本、 发布和消息类型来确定架构名称，例如，"EFACT_D94A_CONTEN"。 它然后再连接目标命名空间与架构名称，例如， `http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006/EFACT#EFACT_D94A_CONTEN`。  
  
  如果消息中存在 UNH2.5，则 EDI 拆装器将首先尝试使用 UNH2.5 的值作为架构名称，如"EFACT_D94A_CONTEN_TEST"的一部分找到的匹配架构。 如果不找到任何匹配架构，则 EDI 拆装器将回退到查找无 UNH2.5 值的架构。  
  
## <a name="authorization"></a>授权  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 检查为协议消息中的字段定义的授权和安全字段的值。 如果存在不匹配，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将挂起该交换。 对于 EDIFACT 编码的消息，这些字段是收件人引用密码 （UNB6.1 和 UNB6.2）。 对于 X12 编码的消息，这些字段是授权限定符和信息 (ISA1-2) 和安全限定符和信息 (ISA3-4)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何接收 EDI 消息](../core/how-biztalk-server-receives-edi-messages.md)