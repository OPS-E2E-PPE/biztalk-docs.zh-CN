---
title: "配置回退验证属性 (EDIFACT) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b925d063-e24b-4cfb-acbd-dcadb511011d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf0e103eb2e20bb64973cd207ed2a55c2f91e58d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-validation-properties-edifact"></a>配置回退验证属性 (EDIFACT)
本部分说明如何防止处理重复控制编号。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-duplicate-validation"></a>若要配置重复验证  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 回退设置**。  
  
2.  在**EDIFACT 回退设置**对话框中，在**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**验证**.  
  
3.  选择**交换控制编号 (UNB5)**复选框以启用接收管道可阻止重复的交换。 如果选中此选项，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将检查所接收的交换的控制编号是否与接收的其他交换的控制编号匹配。 如果检测到匹配，则接收管道将不处理交换。  
  
4.  如果**交换控制编号 (UNB5)**选中，则在**检查内重复的 unb5**字段中，输入天数，以检查重复的交换。  
  
5.  选择**交换中的组控制编号 (UNG5)**以防止接收管道处理重复的组。  
  
6.  选择**事务集控制编号 (UNH1) 组中**以防止接收管道处理重复的事务设置。  
  
7.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [为交换处理配置 EDIFACT 回退协议属性](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)