---
title: 如何搜索所有服务实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- Query tab [Administration Console], searching
- service instances, searching
- instances, services
ms.assetid: 48cb885c-aaf1-44e8-9810-2e70cf63db81
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbc3bc4383d3f2bd36a18adfdac33cca80482a72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334806"
---
# <a name="how-to-search-for-all-service-instances"></a>如何搜索所有服务实例
可以使用**查询**BizTalk Server 管理控制台来搜索所有服务实例中的选项卡。 如果有任何正在运行或挂起的实例，不能取消登记特定的服务类型。 例如，可以取消登记特定的服务类型之前，您可以搜索所有服务实例，以确保不存在任何正在运行或挂起的实例。  

> [!NOTE]
>  在结果中显示时按 URI 分组和筛选仅发送和接收端口。 不能为业务流程，这不包括在显示的结果按 URI 分组和筛选。  

## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 BizTalk Server Operators 组的成员的身份登录。  

### <a name="to-search-for-all-service-instances"></a>若要搜索所有服务实例  

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后单击 BizTalk 组。  

3. 在详细信息窗格中，单击**新查询**选项卡。  

4. 在中**查询表达式**组中，在**值**列中，选择**正在进行中的所有服务实例**从下拉列表框。  

5. 在中**字段名**列，星号旁边的空下拉列表框中 (* *\\* * *)，选择一个或多项操作：  


   |        使用此选项         |                                                                                                              执行的操作                                                                                                              |
   |-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  **应用程序名称**   |                                                                                                   BizTalk Server 应用程序。                                                                                                    |
   |    **创建时间**    |                                                                                查找指定日期之前或之后创建的所有服务实例。                                                                                |
   |  **按结果进行分组**   |                                                              可以通过应用程序、 主机名、 服务类、 服务实例状态或服务名称的结果进行分组。                                                               |
   |      **Host Name**      |                                                                                                    BizTalk 主机的名称。                                                                                                     |
   |   **实例状态**   | 您可以搜索所有正在运行的实例、 所有挂起的实例、 活动实例、 已冻结的实例，实例已准备好运行，计划的实例、 已挂起但不可恢复的实例或已挂起和恢复的实例。 |
   |   **最大匹配数**   |               到匹配项的数目显示 （必需）。 这通常设置为 50，默认值。<br /><br /> 当包含结果分组依据时，这将显示组数，不记录的总数。               |
   |    **服务类**    |                                                 您可以搜索独立适配器;消息传送;消息传送和独立的适配器;MSMQT;业务流程;或路由故障报告。                                                  |
   | **服务实例 ID** |                                                                                  您可以进行分组或筛选的服务实例的服务实例 id。                                                                                   |
   |    **服务名称**     |                                                                                      您可以进行分组或筛选由服务名称的服务实例。                                                                                      |
   |   **服务类型 ID**   |                                                                                    您可以进行分组或筛选的服务实例的服务类型 id。                                                                                     |


6. 完成**值**根据需要将所选内容中所做的列**字段名**列。  

7. 继续将其他行添加到查询根据需要，通过完成**字段名**，**运算符**，并**值**列，并单击**运行查询**。  

## <a name="see-also"></a>请参阅  
 [使用管理控制台的“查询”选项卡](../core/using-the-administration-console-query-tab.md)