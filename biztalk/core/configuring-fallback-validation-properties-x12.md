---
title: 配置回退验证属性 (X12) |Microsoft Docs
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
ms.openlocfilehash: e6ab5d688a0496ce55f1ae343ad48dba1ba901ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391103"
---
# <a name="configuring-fallback-validation-properties-x12"></a>配置回退验证属性 (X 12)
X12 交换验证生成后备设置定义如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]检查收到的交换中的重复控制编号。  
  
> [!NOTE]
>  此处所述的设置也适用于 HIPAA 交换验证。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-validation"></a>若要配置验证  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。  
  
2. 在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**交换设置**部分中，单击**验证**.  
  
3. 选择**交换控制编号**复选框以启用接收管道可阻止重复交换。 如果选择，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会检查收到的交换的交换控制编号 (ISA13) 与交换控制编号不匹配。 如果检测到匹配项，则接收管道将不处理交换。  
  
4. 如果**交换控制编号**处于选中状态，在**检查中的重复 ISA13**字段中，输入将使用特定执行检查是否有重复交换的天数交换控制编号。  
  
5. 选择**组控制编号**以阻止接收管道处理具有重复组控制编号 (GS6) 的交换。  
  
6. 选择**事务集控制编号**以阻止接收管道处理具有重复事务集控制编号 (ST2) 的交换。  
  
7. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [为交换处理配置 X12 后备协议属性](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)