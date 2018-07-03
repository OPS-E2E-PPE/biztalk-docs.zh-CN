---
title: 配置确认 (EDIFACT) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9436feb7-4c29-4b7c-b5c2-991660e6c1a9
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 269acfa79808f133f4332371d98e491fc8a0b2e1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991366"
---
# <a name="configuring-acknowledgements-edifact"></a>配置确认(EDIFACT)
在合作伙伴协议中，可以指定将何种类型的确认返回给参与方以及在发送确认时使用何种发送端口。 还可以指定是否对确认进行批处理、为确认使用哪个起始事务集参考编号以及是否为接受的事务集生成 SG1/SG4 循环。  
  
> [!IMPORTANT]
>  以下属性禁用此页上，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
> 
> - **生成为接受的事务集 SG1/SG4 循环 （如果未选中，将生成循环仅当 UCM.5 不等于 7）**。  
> 
>   仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a>配置 EDIFACT 确认 (CONTRL) 属性  
  
1.  创建 EDIFACT 编码协议，如中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2.  在单向协议选项卡下**交换设置**部分中，单击**确认**。  
  
3.  在中**EDIFACT 确认 (Control) 部分**，执行以下操作：  
  
    1.  选择**预期接收消息 (CONTRL)** 向交换发件人返回技术 (CONTRL) 确认。 如果**预期接收消息 (CONTRL)** ，则选择**进行批处理的消息 (CONTRL) 消息的接收**可单独发送每个确认，否则将对确认进行批处理。  
  
    2.  选择**确认 (CONTRL) 预期**向交换发件人返回功能 (CONTRL) 确认。 如果**确认 (CONTRL) 预期**，则选择**不批确认 (CONTRL)** 可单独发送每个功能确认，否则将进行批处理功能确认。  
  
4.  在中**事务集状态接受报告**部分中，若要强制在功能 CONTRL 确认中为接受的事务集 SG1/SG4 循环的生成选择**生成 SG1/SG4 循环接受事务集 （如果未选中，将生成循环仅当 UCM.5 不等于 7）**。 有关 SG1/SG4 循环的详细信息，请参阅[作为功能确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-functional-acknowledgment.md)。  
  
5.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置交换设置 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)