---
title: 如何恢复已挂起的业务流程实例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- instances, resuming [HAT]
- HAT, resuming orchestrations
- HAT, resuming pipelines
- orchestrations, resuming
- resuming, pipelines
- resuming, orchestrations
- HAT, debug mode
ms.assetid: da133183-68d9-48d1-9601-8f6d4d5b8898
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6696547ce3e918dc8d84b7cfcb4f24e31c8b70a0
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22316889"
---
# <a name="how-to-resume-suspended-orchestration-instances"></a>如何恢复挂起的业务流程实例
如果你已挂起被列为“可恢复的挂起”的业务流程实例，则可以尝试从查询结果或预览窗格中恢复该业务流程实例。 只有在导致业务流程实例挂起的根本问题也得到解决后，才能成功恢复该业务流程实例。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 BizTalk Server Operators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-resume-suspended-orchestration-instances"></a>恢复挂起的业务流程实例  
  
1.  单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 **BizTalk Server 管理**, ，然后单击 BizTalk 组。  
  
3.  在详细信息窗格中，单击 **新查询** 选项卡。  
  
4.  在 **查询表达式** 组中，在 **值** 列中，选择 **挂起服务实例** 从下拉列表框。  
  
5.  执行以下操作之一：  
  
    -   若要在中恢复的单个实例， **字段名称** 旁边星号的空下拉列表框中的列，(**\***)，选择 **服务名称** 筛选器，然后在 **值** 列中，指定服务名称。  
  
    -   若要在恢复实例成批情况下， **字段名称** 旁边星号的空下拉列表框中的列，(**\***)，选择 **结果分组依据** 然后在 **值** 列中，指定服务名称。  
  
6.  单击 **运行查询**。  
  
7.  在查询结果列表中，右键单击你想要恢复，然后单击该业务流程实例**恢复实例**或**恢复实例**。 这允许你选择要恢复的实例。  
  
     [服务实例状态](../core/service-instance-states.md)提供有关详细信息上挂起状态。  
  
## <a name="see-also"></a>另请参阅  
 [调查业务流程、端口和消息失败](../core/investigating-orchestration-port-and-message-failures.md)
