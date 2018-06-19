---
title: 配置验证 （X12 交换设置） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdad7016-1d66-4d11-b620-c28368f00133
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0edfe66791fa5c041c66a3adddde61730afe54ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233269"
---
# <a name="configuring-validation-x12-interchange-settings"></a>配置验证（X 12 交换设置）
X12 交换验证生成设置定义 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何检查收到的交换中重复的控制编号。  
  
> [!NOTE]
>  此处所述的设置也适用于 HIPAA 交换验证。  
  
> [!IMPORTANT]
>  没有属性禁用此页上，即使你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-validation"></a>若要配置验证  
  
1.  创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**交换设置**部分中，单击**验证**。  
  
3.  选择**交换控制编号**复选框以启用接收管道可阻止重复的交换。 如果选中此选项，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将检查所接收交换的交换控制编号 (ISA13) 是否与交换控制编号匹配。 如果检测到匹配，则接收管道将不处理交换。  
  
4.  如果**交换控制编号**选中，则在**检查内重复的 isa13**字段中，输入将使用特定执行的检查重复的交换的天数交换控制编号。  
  
5.  选择**组控制编号**以防止接收管道处理具有重复组控制编号 (GS6) 的交换。  
  
6.  选择**事务集控制编号**以防止接收管道处理具有重复事务集控制编号 (ST2) 的交换。  
  
7.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置交换设置 (X12)](../core/configuring-interchange-settings-x12.md)