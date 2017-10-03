---
title: "配置确认 (EDIFACT) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9436feb7-4c29-4b7c-b5c2-991660e6c1a9
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fe376437c2d6657acb98d548c2c1373b050d599
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-acknowledgements-edifact"></a>配置确认(EDIFACT)
在合作伙伴协议中，可以指定将何种类型的确认返回给参与方以及在发送确认时使用何种发送端口。 还可以指定是否对确认进行批处理、为确认使用哪个起始事务集参考编号以及是否为接受的事务集生成 SG1/SG4 循环。  
  
> [!IMPORTANT]
>  以下属性禁用此页上，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
>   
>  -   **生成 SG1/SG4 循环，用于接受的事务集 （如果未选中，循环将生成仅当 UCM.5 是否不等于 7）**。  
>   
>  仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a>配置 EDIFACT 确认 (CONTRL) 属性  
  
1.  创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**交换设置**部分中，单击**确认**。  
  
3.  在**EDIFACT ACK （控件） 部分**，执行以下操作：  
  
    1.  选择**收到预期消息 (CONTRL)**可向交换发件人返回技术 (CONTRL) 确认。 如果**收到预期消息 (CONTRL)** ，则选择**执行批量收到消息 (CONTRL) 消息**分别发送每个确认或离开清除进行批处理确认。  
  
    2.  选择**确认 (CONTRL) 预期**可向交换发件人返回功能 (CONTRL) 确认。 如果**确认 (CONTRL) 预期**，则选择**执行批量确认 (CONTRL)**分别发送每个功能确认或离开清除进行批处理功能确认。  
  
4.  在**事务集状态接受报告**部分，若要强制在功能 CONTRL 确认中为接受的事务集生成 SG1/SG4 循环选择**生成 SG1/SG4 循环接受事务集 （如果未选中，循环将生成仅当 UCM.5 是否不等于 7）**。 有关 SG1/SG4 循环的详细信息，请参阅[作为功能确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-functional-acknowledgment.md)。  
  
5.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置交换设置 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)