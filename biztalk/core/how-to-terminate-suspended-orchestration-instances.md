---
title: "如何终止挂起的业务流程实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, terminating [HAT]
- messages, saving [HAT]
- HAT, saving messages
- HAT, terminating pipelines
- HAT, terminiating orchestrations
- orchestrations, terminating [HAT]
ms.assetid: b5d44cce-b05c-47f9-9015-5b10c2312bf1
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dc0160be5aeeef43b9595953893b4ea1af82c62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-terminate-suspended-orchestration-instances"></a>如何终止挂起的业务流程实例
可以从 BizTalk Server 管理控制台中的查询结果或预览窗格终止所有挂起的业务流程实例或端口。  
  
> [!NOTE]
>  有序传递发送端口的每个实例可能具有与之关联的多个消息。 为了防止意外终止或数据丢失，请确保您在终止某一实例前查看了所有此类关联。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 BizTalk Server Operators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-terminate-suspended-orchestration-instances"></a>终止挂起的业务流程实例  
  
1.  单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”，然后单击“BizTalk 组”。  
  
3.  在详细信息窗格中，单击**新查询**选项卡。  
  
4.  在**查询表达式**组中，在**值**列中，选择**挂起服务实例**从下拉列表框。  
  
5.  执行以下操作之一：  
  
    -   若要在终止单个实例中，**字段名称**旁边星号的空下拉列表框中的列，(**\***)，选择**服务名称**筛选器然后在**值**列中，指定服务名称。  
  
    -   若要在终止实例成批情况下，**字段名称**旁边星号的空下拉列表框中的列，(**\***)，选择**结果分组依据**，然后在**值**列中，指定服务名称。  
  
6.  单击**运行查询**。  
  
7.  在查询结果列表中，右键单击的业务流程实例或组你想要终止，然后单击的实例**终止实例**或**终止实例**。  
  
## <a name="see-also"></a>另请参阅  
 [调查业务流程、 端口和消息失败](../core/investigating-orchestration-port-and-message-failures.md)