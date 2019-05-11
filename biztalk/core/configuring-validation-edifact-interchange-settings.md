---
title: 配置验证 （EDIFACT-交换设置） |Microsoft Docs
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
ms.openlocfilehash: 5999d52c8896a750810edfa64c0874c8d0948fef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355033"
---
# <a name="configuring-validation-edifact-interchange-settings"></a>配置验证 （EDIFACT-交换设置）
本部分将说明了如何防止处理重复控制编号。  
  
> [!IMPORTANT]
>  没有属性禁用此页上，即使您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-duplicate-validation"></a>若要配置重复验证  
  
1. 创建 EDIFACT 编码协议，如中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2. 在单向协议选项卡下**交换设置**部分中，单击**验证**。  
  
3. 选择**交换控制编号 (UNB5)** 复选框以启用接收管道可阻止重复交换。 如果选择，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将检查接收交换的交换控制编号与接收的其他交换的交换控制编号不匹配。 如果检测到匹配项，则接收管道将不处理交换。  
  
4. 如果**交换控制编号 (UNB5)** 处于选中状态，在**检查重复的 UNB5 范围**字段中，输入天数，以检查是否有重复交换。  
  
5. 选择**交换中的组控制编号 (UNG5)** 以阻止接收管道处理重复的组。  
  
6. 选择**事务集控制编号 (UNH1) 组中**以阻止接收管道处理重复的事务设置。  
  
7. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置交换设置 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)