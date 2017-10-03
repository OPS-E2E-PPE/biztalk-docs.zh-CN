---
title: "如何挂起业务流程实例或端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, suspending
- instances, suspending
- suspending
- HAT, suspending orchestrations
- HAT, suspending pipelines
- suspending, ports
- suspending, orchestrations
- orchestrations, suspending
- HAT, suspending ports
- suspending, instances
- ports, suspending
ms.assetid: cacc7e58-7d3e-4d6b-adb0-618fdc4f0d89
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62d91c8d1e02b7283a430f7c82c572b6a989d108
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-suspend-orchestration-instances-or-ports"></a>如何挂起业务流程实例或端口
可以从 BizTalk Server 管理控制台中的查询结果列表中挂起业务流程实例或端口。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 BizTalk Server Operators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-suspend-orchestration-instances-or-ports"></a>挂起业务流程实例或端口  
  
1.  单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，然后单击 BizTalk 组。  
  
3.  在详细信息窗格中，单击**新查询**选项卡。  
  
4.  在**查询表达式**组中，在**值**列中，选择**运行服务实例**从下拉列表框。  
  
5.  执行以下操作之一：  
  
    -   若要在中暂停的单个实例，**字段名称**旁边星号的空下拉列表框中的列，(**\***)，选择**服务名称**筛选器和然后在**值**列中，指定服务名称。  
  
    -   若要在中暂停成批情况下，实例**字段名称**旁边星号的空下拉列表框中的列，(**\***)，选择**结果分组依据**然后在**值**列中，指定服务名称。  
  
6.  单击**运行查询**。  
  
7.  在查询结果列表中，右键单击你想要挂起，，然后单击活动的业务流程的一个或多个端口**挂起实例**或**挂起实例**。  
  
## <a name="see-also"></a>另请参阅  
 [调查业务流程、 端口和消息失败](../core/investigating-orchestration-port-and-message-failures.md)