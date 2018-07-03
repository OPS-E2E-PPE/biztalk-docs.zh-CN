---
title: 如何搜索订阅 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Query tab [Administration Console], subscriptions
- Query tab [Administration Console], searching
- subscriptions, viewing
- subscriptions, searching
ms.assetid: 95f8fd20-2750-412b-a67b-18976e7706e2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07230ace1e097d71e728110b8f2280e903ea67b8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023243"
---
# <a name="how-to-search-for-subscriptions"></a>如何搜索订阅
可以使用**查询**BizTalk Server 管理控制台来搜索订阅中的选项卡。 当希望查看系统中定义的所有订阅时，这就非常有用。 在排除路由故障时，您可以查看是不是由于某些订阅未正确设置而导致了路由故障。  

## <a name="prerequisites"></a>必要條件  
 若要执行此过程，则必须以 BizTalk Server Operators 组成员的身份登录。  

### <a name="to-search-for-subscriptions"></a>搜索订阅  

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。  

2. 在控制台树中，展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”，然后单击“BizTalk 组”。  

3. 在详细信息窗格中，单击**新查询**选项卡。  

4. 在中**查询表达式**组中，在**值**列中，选择**订阅**从下拉列表框。  

5. 在中**字段名**列，星号旁边的空下拉列表框中 (* *\\* * *)，选择一个或多项操作：  


   |          项           |                                    Description                                    |
   |-------------------------|-----------------------------------------------------------------------------------|
   |   **最大匹配数**   |                         要显示的匹配数。                         |
   | **服务实例 ID** |               您可以按服务实例 ID 对订阅进行筛选。                |
   |    **服务名称**     |                   您可以按服务名对订阅进行筛选。                   |
   |  **订阅类型**  | 您可以按“激活订阅”或“实例订阅”对订阅进行筛选。 |


6. 完成**值**根据需要将所选内容中所做的列**字段名**列。  

7. 继续将其他行添加到查询根据需要，通过完成**字段名**，**运算符**，并**值**列，并单击**运行查询**。  

## <a name="see-also"></a>请参阅  
 [使用管理控制台的“查询”选项卡](../core/using-the-administration-console-query-tab.md)