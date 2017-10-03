---
title: "配置确认 (X12) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eec2dbff-5d04-4a38-bad0-33d040b6dd12
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edec872f4055bb2c06772d361f18345d4a4be2d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-acknowledgements-x12"></a>配置确认 (X 12)
在合作伙伴协议中，您可以指定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生成确认的方式，以响应从参与方接收的 X12 编码的交换，以及返回到参与方的确认类型。 您还可以指定是否批处理确认，以及是否为接收的事务集生成 AK2 循环。 本部分提供如何执行操作的说明。  
  
> [!NOTE]
>  此处所述的确认属性同样适用于 HIPAA 确认。  
  
> [!IMPORTANT]
>  以下属性禁用此页上，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
>   
>  -   **包括 AK2 循环，用于接受的事务集 （如果未选中，循环将生成仅当 AK501 是否不等于 A）**。  
>   
>  仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-x12-ack-properties"></a>配置 X12 确认属性  
  
1.  创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**交换设置**，单击**确认**。  
  
3.  选择**预期的 TA1**可向交换发件人返回技术 (TA1) 确认。 如果选择，选择**执行批量 TA1**分别发送每个技术确认或离开清除进行批处理的技术确认此复选框。  
  
4.  选择**997 预期**可向交换发件人返回功能 (997) 确认。 如果选择，选择**执行批量 997**分别发送每个功能确认或离开清除进行批处理功能确认此复选框。  
  
5.  若要启用在 997 确认中为接受的事务集生成 AK2 循环，请选择**包括 AK2 循环，用于接受的事务集 （如果未选中，循环将生成仅当 AK501 是否不等于 A）**。 有关 AK2 循环的详细信息，请参阅[X12 997 确认](../core/x12-997-acknowledgment.md)。  
  
6.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置交换设置 (X12)](../core/configuring-interchange-settings-x12.md)