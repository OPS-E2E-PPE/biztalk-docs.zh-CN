---
title: 配置标识符 (X12) |Microsoft 文档
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
ms.openlocfilehash: c4cbe3ce7badc9258e823034e5ed443d6f3d60e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234133"
---
# <a name="configuring-identifiers-x12"></a>配置标识符 (X12)
在合作伙伴协议，你必须设置 X12 授权和安全的属性，以验证该交换未在由接收未经授权的收件人。  
  
> [!NOTE]
>  此处所述的交换处理属性也适用于 HIPAA 交换。  
  
> [!IMPORTANT]
>  以下属性禁用此页上，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
>   
>  -   **DestinationPartyName**下**其他协议冲突解决程序**部分。  
>   
>  仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-set-sender-receiver-and-security-properties"></a>设置发送方、接收方和安全属性  
  
1.  创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**交换设置**部分中，单击**标识符**。  
  
3.  输入值**ISA1-2 （授权限定符和信息）**。 选择的值**授权限定符 (ISA1)** 从关联的下拉列表。 如果此值为以外**00**，为**值 (ISA2)** 文本框中，输入一个字母数字字符的最小值和最多 10 个。 此字段为可选字段。 如果您确实要指定这些值，请确保它们与接收的交换中的 ISA1 和 ISA2 字段相匹配，否则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将挂起交换。  
  
4.  输入值**ISA3 4 （安全限定符和信息）**。 选择的值**安全限定符 (ISA3)** 从下拉列表。 如果此值为以外**00**，为**值 (ISA4)** 文本框中，输入一个字母数字值的最小值和最多 10 个。 此字段为可选字段。 如果这些值与所接收交换中的 ISA3 和 ISA4 字段不匹配，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将挂起该交换。  
  
    > [!NOTE]
    >  值**03-密码 （适用于向后兼容性）**，包含是为了向后兼容性[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]和将在未来版本中删除。  
  
5.  输入的值**ISA5-6 （发件人限定符和标识符）**。 选择从限定符值**发件人 Id 限定符 (ISA5)** 下拉列表。 标识符，在**值 (ISA6)** 文本框中，输入一个字母数字字符的最小值和最多包含 15 个字符。  
  
6.  输入的值**ISA7-8 （收件人限定符和标识符）**。 选择从限定符值**发件人 Id 限定符 (ISA7)** 下拉列表。 标识符，在**值 (ISA8)** 文本框中，输入一个字母数字字符的最小值和最多包含 15 个字符。  
  
7.  在**其他协议冲突解决程序**部分中，为**DestinationPartyName**属性，为目标方指定一个值。 此值还用于向协议解析出站消息。 有关详细信息，请参阅[协议解析和传出的 EDI 消息的架构确定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。  
  
    > [!NOTE]
    >  通常不需要设置**DestinationPartyName**属性。 此属性用作协议属性的一部分，以支持升级方案。 从 BizTalk Server 2006 R2 或 BizTalk Server 2009 升级时**DestinationPartyName**属性设置为在 BizTalk Server 2006 R2 或 BizTalk Server 2009 方的名称。  
  
8.  单击**应用**接受所做的更改，或单击**确定**以输入和验证所做的更改，然后关闭对话框。  
  
    > [!IMPORTANT]
    >  如果你单击**确定**或**应用**在此阶段，你将收到错误。 这是因为你仍需要为 ISA8 值提供 ISA5**标识符**其他单向协议选项卡的选项卡。  
  
## <a name="see-also"></a>另请参阅  
 [配置交换设置 (X12)](../core/configuring-interchange-settings-x12.md)