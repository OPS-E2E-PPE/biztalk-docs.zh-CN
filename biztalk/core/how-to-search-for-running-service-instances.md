---
title: 如何搜索正在运行的服务实例 |Microsoft 文档
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8873747b39d6fa178b813d361b72ccf24f44b54a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-search-for-running-service-instances"></a>如何运行服务实例的搜索
你可以使用 **查询** 在 BizTalk Server 管理控制台中搜索特定的选项卡冻结中, 处于活动状态，断点，计划，并在重试服务实例。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，则必须以 BizTalk Server Operators 组成员的身份登录。  
  
### <a name="to-search-for-running-service-instances"></a>搜索正在运行的服务实例  
  
1.  单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”，然后单击“BizTalk 组”。  
  
3.  在详细信息窗格中，单击 **新查询** 选项卡。  
  
4.  在 **查询表达式** 组中，在 **值** 列中，选择 **运行服务实例** 从下拉列表框。  
  
5.  在 **字段名称** 旁边星号的空下拉列表框中的列，(**\***)，选择一个或多个以下︰  
  
    |项|Description|  
    |----------|-----------------|  
    |**应用程序名称**|BizTalk Server 应用程序。|  
    |**创建时间**|查找在指定日期之前或之后创建的正在运行的服务实例。|  
    |**按结果进行分组**|可以按应用程序、主机名称、挂起操作类型、服务类别、服务实例状态或服务名称对结果进行分组。|  
    |**主机名**|BizTalk 主机的名称。|  
    |**实例状态**|可以搜索活动实例、已冻结的实例、准备运行的实例以及计划的实例。|  
    |**最大匹配数**|要显示的匹配数。|  
    |**挂起的操作**|可以搜索状态为即将挂起或终止的正在运行的服务实例|  
    |**服务类**|可以搜索以下内容：独立适配器；消息传送；消息传送和独立适配器；MSMQT；业务流程；或路由故障报告。|  
    |**服务名称**|可以按服务名对正在运行的服务实例进行分组或筛选。|  
    |**服务类型 ID**|可以按服务类型 ID 对消息进行分组或筛选。|  
  
6.  完成 **值** 列的适合于所选内容所做中 **字段名称** 列。  
  
7.  继续向视情况而定查询添加更多的行，通过完成 **字段名称**, ，**运算符**, ，和 **值** columns 和 then click **运行查询**。  
  
## <a name="see-also"></a>另请参阅  
 [使用管理控制台的“查询”选项卡](../core/using-the-administration-console-query-tab.md)