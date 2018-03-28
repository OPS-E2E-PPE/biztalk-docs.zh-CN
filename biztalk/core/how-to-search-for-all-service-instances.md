---
title: 如何搜索所有服务实例 |Microsoft 文档
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e96622fad23c28c0d4147f64a11cc540e88e7f97
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-search-for-all-service-instances"></a>如何搜索所有服务实例
你可以使用 **查询** 在 BizTalk Server 管理控制台中以搜索所有服务实例的选项卡。 如果存在任何正在运行的或挂起的实例，则无法取消登记特定的服务类型。 例如，在取消登记特定的服务类型之前，您可以搜索所有服务实例以确保没有正在运行的或挂起的实例。  
  
> [!NOTE]
>  在按 URI 进行分组和筛选时，结果中将仅显示发送和接收端口。 对于所显示的结果中未包含的业务流程，将不能按 URI 进行分组和筛选。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，则必须以 BizTalk Server Operators 组成员的身份登录。  
  
### <a name="to-search-for-all-service-instances"></a>搜索所有服务实例  
  
1.  单击 **启动**, ，单击 **所有程序**, ，单击 [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], ，然后单击 **BizTalk Server 管理**。  
  
2.  在控制台树中，展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”，然后单击“BizTalk 组”。  
  
3.  在详细信息窗格中，单击 **新查询** 选项卡。  
  
4.  在 **查询表达式** 组中，在 **值** 列中，选择 **正在进行中的所有服务实例** 从下拉列表框。  
  
5.  在 **字段名称** 旁边星号的空下拉列表框中的列，(**\***)，选择一个或多个以下︰  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**应用程序名称**|BizTalk Server 应用程序。|  
    |**创建时间**|查找在指定日期之前或之后创建的所有服务实例。|  
    |**按结果进行分组**|可以按应用程序、主机名称、服务类别、服务实例状态或服务名称对结果进行分组。|  
    |**主机名**|BizTalk 主机的名称。|  
    |**实例状态**|可以搜索所有正在运行的实例、所有挂起的实例、活动实例、已冻结的实例、准备运行的实例、计划的实例、已挂起但不可恢复的实例或已挂起并可恢复的实例。|  
    |**最大匹配数**|要显示的匹配数（必选）。 通常设置为 50，这是默认值。<br /><br /> 如果选择了“结果分组依据”，则会显示组数，而不显示记录总数。|  
    |**服务类**|可以搜索以下内容：独立适配器；消息传送；消息传送和独立适配器；MSMQT；业务流程；或路由故障报告。|  
    |**服务实例 ID**|可以按服务实例 ID 对服务实例进行分组或筛选。|  
    |**服务名称**|可以按服务名对服务实例进行分组或筛选。|  
    |**服务类型 ID**|可以按服务类型 ID 对服务实例进行分组或筛选。|  
  
6.  完成 **值** 列的适合于所选内容所做中 **字段名称** 列。  
  
7.  继续向视情况而定查询添加更多的行，通过完成 **字段名称**, ，**运算符**, ，和 **值** columns 和 then click **运行查询**。  
  
## <a name="see-also"></a>另请参阅  
 [使用管理控制台的“查询”选项卡](../core/using-the-administration-console-query-tab.md)