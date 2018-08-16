---
title: 如何搜索正在运行的服务实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service instances, viewing
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- Query tab [Administration Console], searching
- service instances, searching
- service instances, running
ms.assetid: fc65bf33-c013-4e6a-b9fd-b4536811e7b4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c61b94b440810fc948ae7e9e51c1897204d28c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023931"
---
# <a name="how-to-search-for-running-service-instances"></a>如何搜索正在运行的服务实例
可以使用**查询**冻结在 BizTalk Server 管理控制台来搜索特定的选项卡，处于活动状态，在断点，计划，并在重试服务实例。  

## <a name="prerequisites"></a>必要條件  
 若要执行此过程，则必须以 BizTalk Server Operators 组成员的身份登录。  

### <a name="to-search-for-running-service-instances"></a>搜索正在运行的服务实例  

1. 单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台树中，展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”，然后单击“BizTalk 组”。  

3. 在详细信息窗格中，单击**新查询**选项卡。  

4. 在中**查询表达式**组中，在**值**列中，选择**正在运行的服务实例**从下拉列表框。  

5. 在中**字段名**列，星号旁边的空下拉列表框中 (* *\\* * *)，选择一个或多项操作：  


   |          项          |                                                             Description                                                             |
   |------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
   |  **应用程序名称**  |                                                   BizTalk Server 应用程序。                                                   |
   |   **创建时间**    |                             查找在指定日期之前或之后创建的正在运行的服务实例。                              |
   |  **按结果进行分组**  |  可以按应用程序、主机名称、挂起操作类型、服务类别、服务实例状态或服务名称对结果进行分组。  |
   |     **Host Name**      |                                                    BizTalk 主机的名称。                                                    |
   |  **实例状态**   |             可以搜索活动实例、已冻结的实例、准备运行的实例以及计划的实例。             |
   |  **最大匹配数**   |                                                  要显示的匹配数。                                                  |
   | **挂起的操作** |                      可以搜索状态为即将挂起或终止的正在运行的服务实例                       |
   |   **服务类**    | 可以搜索以下内容：独立适配器；消息传送；消息传送和独立适配器；MSMQT；业务流程；或路由故障报告。 |
   |    **服务名称**    |                                 可以按服务名对正在运行的服务实例进行分组或筛选。                                  |
   |  **服务类型 ID**   |                                        可以按服务类型 ID 对消息进行分组或筛选。                                         |


6. 完成**值**根据需要将所选内容中所做的列**字段名**列。  

7. 继续将其他行添加到查询根据需要，通过完成**字段名**，**运算符**，并**值**列，并单击**运行查询**。  

## <a name="see-also"></a>请参阅  
 [使用管理控制台的“查询”选项卡](../core/using-the-administration-console-query-tab.md)