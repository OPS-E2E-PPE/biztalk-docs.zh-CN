---
title: 配置标识符 (EDIFACT) |Microsoft Docs
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
ms.openlocfilehash: 2c50743c237c66edcba1e6609dcd1ab9cb0081bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997214"
---
# <a name="configuring-identifiers-edifact"></a>配置标识符 (EDIFACT)
在合作伙伴协议中，必须设置收件人引用密码，以确认交换不会被未经授权的收件人接收。  
  
> [!IMPORTANT]
>  以下属性禁用此页上，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
> 
> - **DestinationPartyName**下**其他协议解析程序**部分。  
> 
>   仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-set-the-sender-recipient-and-recipient-password"></a>若要设置发件人、 收件人和收件人密码  
  
1.  创建 EDIFACT 编码协议，如中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2.  在单向协议选项卡下**交换设置**部分中，单击**标识符**。  
  
3.  在中**发件人 (UNB2)** 部分中，执行以下操作：  
  
    1.  有关**标识 (UNB2.1)**，输入一个最小值和最多为 35 的字母数字值。 这是必填字段。  
  
    2.  有关**代码限定符 (UNB2.2)**，从下拉列表中选择一个值。 此字段为可选字段。  
  
    3.  有关**反向路由地址 (UNB2.3)**，输入包含最少一个字符，最多为 14 个字符的字母数字值。 此字段为可选字段。  
  
4.  在中**收件人 (UNB3)** 部分中，执行以下操作：  
  
    1.  有关**标识 (UNB3.1)**，输入一个最小值和最多为 35 的字母数字值。 这是必填字段。  
  
    2.  有关**代码限定符 (UNB3.2)**，从下拉列表中选择一个值。 此字段为可选字段。  
  
    3.  有关**反向路由地址 (UNB3.3)**，输入包含最少一个字符，最多为 14 个字符的字母数字值。 此字段为可选字段。  
  
    4.  如果需要，在**收件人引用密码 (UNB6)** 部分中，输入收件人引用密码的值。 有关**值 (UNB6.1)**，输入一个最小值和最多 14 个字母数字值。 有关**限定符 (UNB6.2)**，输入包含最少一个字符，最多两个字符的字母数字值。 这些是可选字段。 如果这些值与所接收交换中的 UNB6.1 和 UNB6.2 字段不匹配，BizTalk Server 将挂起该交换。  
  
        > [!NOTE]
        >  组合**UNB6.1**并**UNB6.2**必须是唯一的。  
  
        > [!NOTE]
        >  如果同时为 UNB6.1 和 UNB6.2 输入值，应用更改，然后取消 UNB6.1，则 UNB6.2 中的值也将被删除，而且该字段将被禁用。  
  
5.  在中**其他协议解析程序**部分中，对于**DestinationPartyName**属性，为目标参与方指定一个值。 此值还用于向协议解析出站消息。 有关详细信息，请参阅[协议解析和架构确定传出 EDI 消息的](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。  
  
    > [!NOTE]
    >  通常不需要设置**DestinationPartyName**属性。 此属性用作协议属性的一部分，以支持升级方案。 从 BizTalk Server 2006 R2 或 BizTalk Server 2009 升级时**DestinationPartyName**属性设置为在 BizTalk Server 2006 R2 或 BizTalk Server 2009 中参与方的名称。  
  
6.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
    > [!IMPORTANT]
    >  如果单击**确定**或**应用**在此阶段，会收到错误。 这是因为你仍需要提供上的 UNB2 和 UNB3 值**标识符**其他单向协议选项卡的选项卡。  
  
## <a name="see-also"></a>请参阅  
 [配置交换设置 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)