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
ms.openlocfilehash: d9a09a2ed8f5f209549d7eb5246db4c4509eccd1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384020"
---
# <a name="how-to-search-for-running-service-instances"></a>如何搜索正在运行的服务实例
可以使用**查询**冻结在 BizTalk Server 管理控制台来搜索特定的选项卡，处于活动状态，在断点，计划，并在重试服务实例。  

## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 BizTalk Server Operators 组的成员的身份登录。  

### <a name="to-search-for-running-service-instances"></a>若要搜索的正在运行的服务实例  

1. 单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后单击 BizTalk 组。  

3. 在详细信息窗格中，单击**新查询**选项卡。  

4. 在中**查询表达式**组中，在**值**列中，选择**正在运行的服务实例**从下拉列表框。  

5. 在中**字段名**列，星号旁边的空下拉列表框中 (* *\\* * *)，选择一个或多项操作：  


   |          项          |                                                             Description                                                             |
   |------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
   |  **应用程序名称**  |                                                   BizTalk Server 应用程序。                                                   |
   |   **创建时间**    |                             查找运行指定日期之前或之后创建的服务实例。                              |
   |  **按结果进行分组**  |  可以通过应用程序、 主机名，挂起操作类型、 服务类、 服务实例状态或服务名称的结果进行分组。  |
   |     **Host Name**      |                                                    BizTalk 主机的名称。                                                    |
   |  **实例状态**   |             您可以搜索活动实例、 已冻结的实例，您可以随时运行的实例以及计划的实例。             |
   |  **最大匹配数**   |                                                  若要显示的匹配项的数目。                                                  |
   | **挂起的操作** |                      您可以搜索正在运行挂起或终止挂起的服务实例。                       |
   |   **服务类**    | 您可以搜索独立适配器;消息传送;消息传送和独立的适配器;MSMQT;业务流程;或路由故障报告。 |
   |    **服务名称**    |                                 您可以进行分组或筛选正在运行的服务名称的服务实例。                                  |
   |  **服务类型 ID**   |                                        您可以进行分组或筛选由服务的消息类型 id。                                         |


6. 完成**值**根据需要将所选内容中所做的列**字段名**列。  

7. 继续将其他行添加到查询根据需要，通过完成**字段名**，**运算符**，并**值**列，并单击**运行查询**。  

## <a name="see-also"></a>请参阅  
 [使用管理控制台的“查询”选项卡](../core/using-the-administration-console-query-tab.md)