---
title: 配置回退验证属性 (X12) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a64431d-373a-4d63-9b83-cbb323620152
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc6eb44f2ee4c2f9c63011dc14be41380c245996
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233149"
---
# <a name="configuring-fallback-validation-properties-x12"></a>配置回退验证属性 (X 12)
X12 交换验证生成后备设置定义 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何检查收到的交换中重复的控制编号。  
  
> [!NOTE]
>  此处所述的设置也适用于 HIPAA 交换验证。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-validation"></a>若要配置验证  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 回退设置**。  
  
2.  在**X12 回退设置**对话框中，在**X12 协议页**选项卡上，在**交换设置**部分中，单击**验证**.  
  
3.  选择**交换控制编号**复选框以启用接收管道可阻止重复的交换。 如果选中此选项，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将检查所接收交换的交换控制编号 (ISA13) 是否与交换控制编号匹配。 如果检测到匹配，则接收管道将不处理交换。  
  
4.  如果**交换控制编号**选中，则在**检查内重复的 isa13**字段中，输入将使用特定执行的检查重复的交换的天数交换控制编号。  
  
5.  选择**组控制编号**以防止接收管道处理具有重复组控制编号 (GS6) 的交换。  
  
6.  选择**事务集控制编号**以防止接收管道处理具有重复事务集控制编号 (ST2) 的交换。  
  
7.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置 X12 回退协议属性交换处理](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)