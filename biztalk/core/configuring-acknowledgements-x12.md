---
title: 配置确认 (X12) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eec2dbff-5d04-4a38-bad0-33d040b6dd12
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cd9497c6367ae757206ba91d60575476fbfd05e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356322"
---
# <a name="configuring-acknowledgements-x12"></a>配置确认 (X 12)
在合作伙伴协议中，您可以指定如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]响应从参与方和类型的确认返回到参与方接收的 X12 编码交换而生成确认。 此外可以指定是否批处理确认，以及是否为接受的事务集生成 AK2 循环。 本部分将说明了如何执行此操作。  
  
> [!NOTE]
>  此处所述的确认属性同样适用于 HIPAA 确认。  
> 
> [!IMPORTANT]
>  以下属性禁用此页上，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
> 
> - **为接受的事务集包含 AK2 循环 （如果未选中，将生成循环仅当 AK501 不等于 A）**。  
> 
>   仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用这些属性。 例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-x12-ack-properties"></a>若要配置 X12 确认属性  
  
1.  创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2.  在单向协议选项卡下**交换设置**，单击**确认**。  
  
3.  选择**预期的 TA1**向交换发件人返回技术 (TA1) 确认。 如果选择，选择**不对 TA1 进行批处理**单独发送每个技术确认，否则将技术确认进行批处理的清除此复选框。  
  
4.  选择**预期的 997**向交换发件人返回功能 (997) 确认。 如果选择，选择**不对 997 进行批处理**单独发送每个功能确认，或清除对功能确认进行批处理复选框。  
  
5.  若要启用在 997 确认中为接受的事务集生成 AK2 循环，请选择**接受的事务集包含 AK2 循环 （如果未选中，将生成循环仅当 AK501 不等于 A）**。 有关 AK2 循环的详细信息，请参阅[X12 997 确认](../core/x12-997-acknowledgment.md)。  
  
6.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置交换设置 (X12)](../core/configuring-interchange-settings-x12.md)