---
title: 配置回退验证属性 (EDIFACT) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b925d063-e24b-4cfb-acbd-dcadb511011d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad87f6419745515496a1c140df6159bdd903d3b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355533"
---
# <a name="configuring-fallback-validation-properties-edifact"></a>配置回退验证属性 (EDIFACT)
本部分将说明了如何防止处理重复控制编号。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-duplicate-validation"></a>若要配置重复验证  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 后备设置**。  
  
2. 在中**EDIFACT 后备设置**对话框中**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**验证**.  
  
3. 选择**交换控制编号 (UNB5)** 复选框以启用接收管道可阻止重复交换。 如果选择，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将检查接收交换的交换控制编号与接收的其他交换的交换控制编号不匹配。 如果检测到匹配项，则接收管道将不处理交换。  
  
4. 如果**交换控制编号 (UNB5)** 处于选中状态，在**检查重复的 UNB5 范围**字段中，输入天数，以检查是否有重复交换。  
  
5. 选择**交换中的组控制编号 (UNG5)** 以阻止接收管道处理重复的组。  
  
6. 选择**事务集控制编号 (UNH1) 组中**以阻止接收管道处理重复的事务设置。  
  
7. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [为交换处理配置 EDIFACT 后备协议属性](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)