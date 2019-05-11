---
title: 配置验证 （X12-交换设置） |Microsoft Docs
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
ms.openlocfilehash: 0782546e8d016aba2f8ccc4bcd5b7ad5e81412de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355087"
---
# <a name="configuring-validation-x12-interchange-settings"></a>配置验证（X 12 交换设置）
X12 交换验证生成设置定义如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]检查收到的交换中的重复控制编号。  
  
> [!NOTE]
>  此处所述的设置也适用于 HIPAA 交换验证。  
  
> [!IMPORTANT]
>  没有属性禁用此页上，即使您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-validation"></a>若要配置验证  
  
1. 创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2. 在单向协议选项卡下**交换设置**部分中，单击**验证**。  
  
3. 选择**交换控制编号**复选框以启用接收管道可阻止重复交换。 如果选择，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会检查收到的交换的交换控制编号 (ISA13) 与交换控制编号不匹配。 如果检测到匹配项，则接收管道将不处理交换。  
  
4. 如果**交换控制编号**处于选中状态，在**检查中的重复 ISA13**字段中，输入将使用特定执行检查是否有重复交换的天数交换控制编号。  
  
5. 选择**组控制编号**以阻止接收管道处理具有重复组控制编号 (GS6) 的交换。  
  
6. 选择**事务集控制编号**以阻止接收管道处理具有重复事务集控制编号 (ST2) 的交换。  
  
7. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置交换设置 (X12)](../core/configuring-interchange-settings-x12.md)