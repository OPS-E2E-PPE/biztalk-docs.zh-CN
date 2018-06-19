---
title: 配置验证 （EDIFACT 交换设置） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55820ebc-fe21-48a3-8985-1bf4184176ac
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f87e762177e2938deaa957035e255af3f0d40eab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233077"
---
# <a name="configuring-validation-edifact-interchange-settings"></a>配置验证（EDIFACT-交换设置）
本部分说明如何防止处理重复控制编号。  
  
> [!IMPORTANT]
>  没有属性禁用此页上，即使你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-duplicate-validation"></a>若要配置重复验证  
  
1.  创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**交换设置**部分中，单击**验证**。  
  
3.  选择**交换控制编号 (UNB5)** 复选框以启用接收管道可阻止重复的交换。 如果选中此选项，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将检查所接收的交换的控制编号是否与接收的其他交换的控制编号匹配。 如果检测到匹配，则接收管道将不处理交换。  
  
4.  如果**交换控制编号 (UNB5)** 选中，则在**检查内重复的 unb5**字段中，输入天数，以检查重复的交换。  
  
5.  选择**交换中的组控制编号 (UNG5)** 以防止接收管道处理重复的组。  
  
6.  选择**事务集控制编号 (UNH1) 组中**以防止接收管道处理重复的事务设置。  
  
7.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置交换设置 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)