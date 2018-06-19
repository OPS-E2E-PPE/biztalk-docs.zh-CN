---
title: 配置标识符 (EDIFACT) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 097292f2-1aa5-42e4-aeee-c7d4cbdae17c
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 673501923385c956169670eb1dc61e667e611734
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233845"
---
# <a name="configuring-identifiers-edifact"></a>配置标识符 (EDIFACT)
在合作伙伴协议中，必须设置收件人引用密码，以确认交换不会被未经授权的收件人接收。  
  
> [!IMPORTANT]
>  以下属性禁用此页上，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
>   
>  -   **DestinationPartyName**下**其他协议冲突解决程序**部分。  
>   
>  仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-set-the-sender-recipient-and-recipient-password"></a>若要设置收件人的密码，发送方和接收方  
  
1.  创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**交换设置**部分中，单击**标识符**。  
  
3.  在**发件人 (UNB2)** 部分中，执行以下操作：  
  
    1.  有关**标识 (UNB2.1)**，输入一个最小值和最多 35 个字母数字值。 这是必填字段。  
  
    2.  有关**代码限定符 (UNB2.2)**，从下拉列表中选择一个值。 此字段为可选字段。  
  
    3.  有关**反向路由地址 (UNB2.3)**，输入一个字母数字值，该值最少包含一个字符，最多包含 14 个字符。 此字段为可选字段。  
  
4.  在**收件人 (UNB3)** 部分中，执行以下操作：  
  
    1.  有关**标识 (UNB3.1)**，输入一个最小值和最多 35 个字母数字值。 这是必填字段。  
  
    2.  有关**代码限定符 (UNB3.2)**，从下拉列表中选择一个值。 此字段为可选字段。  
  
    3.  有关**反向路由地址 (UNB3.3)**，输入一个字母数字值，该值最少包含一个字符，最多包含 14 个字符。 此字段为可选字段。  
  
    4.  如果需要，在**收件人引用密码 (UNB6)** 部分中，输入收件人引用密码值。 有关**值 (UNB6.1)**，输入一个最小值和最多 14 个字母数字值。 有关**限定符 (UNB6.2)**，输入最少包含一个字符，最多两个字符的一个字母数字值。 这些是可选字段。 如果这些值与所接收交换中的 UNB6.1 和 UNB6.2 字段不匹配，BizTalk Server 将挂起该交换。  
  
        > [!NOTE]
        >  组合**UNB6.1**和**UNB6.2**必须是唯一的。  
  
        > [!NOTE]
        >  如果同时为 UNB6.1 和 UNB6.2 输入值，应用更改，然后取消 UNB6.1，则 UNB6.2 中的值也将被删除，而且该字段将被禁用。  
  
5.  在**其他协议冲突解决程序**部分中，为**DestinationPartyName**属性，为目标方指定一个值。 此值还用于向协议解析出站消息。 有关详细信息，请参阅[协议解析和传出的 EDI 消息的架构确定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。  
  
    > [!NOTE]
    >  通常不需要设置**DestinationPartyName**属性。 此属性用作协议属性的一部分，以支持升级方案。 从 BizTalk Server 2006 R2 或 BizTalk Server 2009 升级时**DestinationPartyName**属性设置为在 BizTalk Server 2006 R2 或 BizTalk Server 2009 方的名称。  
  
6.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
    > [!IMPORTANT]
    >  如果你单击**确定**或**应用**在此阶段，你将收到错误。 这是因为你仍需要提供上 UNB2 和 UNB3 值**标识符**其他单向协议选项卡的选项卡。  
  
## <a name="see-also"></a>另请参阅  
 [配置交换设置 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)