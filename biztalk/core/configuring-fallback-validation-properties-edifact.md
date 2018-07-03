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
ms.openlocfilehash: 4276ad1b5ae995cfb6370377d7d1671ede09bd52
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975446"
---
# <a name="configuring-fallback-validation-properties-edifact"></a>配置回退验证属性 (EDIFACT)
本部分说明如何防止处理重复控制编号。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-duplicate-validation"></a>若要配置重复验证  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 后备设置**。  
  
2. 在中**EDIFACT 后备设置**对话框中**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**验证**.  
  
3. 选择**交换控制编号 (UNB5)** 复选框以启用接收管道可阻止重复交换。 如果选中此选项，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将检查所接收的交换的控制编号是否与接收的其他交换的控制编号匹配。 如果检测到匹配，则接收管道将不处理交换。  
  
4. 如果**交换控制编号 (UNB5)** 处于选中状态，在**检查重复的 UNB5 范围**字段中，输入天数，以检查是否有重复交换。  
  
5. 选择**交换中的组控制编号 (UNG5)** 以阻止接收管道处理重复的组。  
  
6. 选择**事务集控制编号 (UNH1) 组中**以阻止接收管道处理重复的事务设置。  
  
7. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [为交换处理配置 EDIFACT 后备协议属性](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)