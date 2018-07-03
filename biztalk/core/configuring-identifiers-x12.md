---
title: 配置标识符 (X12) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 665698d1-c46c-4149-9715-381b4966dd92
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc9b4b5a6b2632c797ff655899b118536dbdde4e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003078"
---
# <a name="configuring-identifiers-x12"></a>配置标识符 (X12)
在合作伙伴协议中，你必须设置 X12 授权和安全属性，以确认交换不被通过接收未经授权的收件人。  
  
> [!NOTE]
>  此处所述的交换处理属性也适用于 HIPAA 交换。  
> 
> [!IMPORTANT]
>  以下属性禁用此页上，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
> 
> - **DestinationPartyName**下**其他协议解析程序**部分。  
> 
>   仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-set-sender-receiver-and-security-properties"></a>设置发送方、接收方和安全属性  
  
1. 创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2. 在单向协议选项卡下**交换设置**部分中，单击**标识符**。  
  
3. 输入值**ISA1-2 （授权限定符和信息）**。 选择的值**授权限定符 (ISA1)** 从关联的下拉列表。 如果此值不是**00**，对于**值 (ISA2)** 文字框中，输入一个字母数字字符的最小值和最多 10 个。 此字段为可选字段。 如果您确实要指定这些值，请确保它们与接收的交换中的 ISA1 和 ISA2 字段相匹配，否则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将挂起交换。  
  
4. 输入值**ISA3-4 （安全限定符和信息）**。 选择的值**安全限定符 (ISA3)** 从下拉列表。 如果此值不是**00**，对于**值 (ISA4)** 文字框中，输入一个字母数字值的最小值和最多 10 个。 此字段为可选字段。 如果这些值与所接收交换中的 ISA3 和 ISA4 字段不匹配，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将挂起该交换。  
  
   > [!NOTE]
   >  值**03 – 密码 （用于向后兼容性）**，是为了向后兼容包含[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]和将在未来版本中删除。  
  
5. 输入的值**ISA5-6 （发送方限定符和标识符）**。 选择从限定符的值**发件人 Id 限定符 (ISA5)** 下拉列表。 对于标识符，在**值 (ISA6)** 文字框中，输入最少一个字母数字字符、 最多包含 15 个字符。  
  
6. 输入的值**ISA7-8 （接收方限定符和标识符）**。 选择从限定符的值**发件人 Id 限定符 (ISA7)** 下拉列表。 对于标识符，在**值 (ISA8)** 文字框中，输入最少一个字母数字字符、 最多包含 15 个字符。  
  
7. 在中**其他协议解析程序**部分中，对于**DestinationPartyName**属性，为目标参与方指定一个值。 此值还用于向协议解析出站消息。 有关详细信息，请参阅[协议解析和架构确定传出 EDI 消息的](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。  
  
   > [!NOTE]
   >  通常不需要设置**DestinationPartyName**属性。 此属性用作协议属性的一部分，以支持升级方案。 从 BizTalk Server 2006 R2 或 BizTalk Server 2009 升级时**DestinationPartyName**属性设置为在 BizTalk Server 2006 R2 或 BizTalk Server 2009 中参与方的名称。  
  
8. 单击**Apply**以接受更改，或单击**确定**以输入和验证所做的更改，然后关闭对话框。  
  
   > [!IMPORTANT]
   >  如果单击**确定**或**应用**在此阶段，会收到错误。 这是因为你仍需要提供 ISA5 到 ISA8 值上**标识符**其他单向协议选项卡的选项卡。  
  
## <a name="see-also"></a>请参阅  
 [配置交换设置 (X12)](../core/configuring-interchange-settings-x12.md)