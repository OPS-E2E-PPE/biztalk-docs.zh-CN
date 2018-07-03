---
title: 如何暂停、 恢复和终止业务流程实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], resuming
- orchestrations, terminating
- managing [orchestrations], suspending
- orchestrations, resuming
- orchestrations, suspending
- managing [orchestrations], terminating
ms.assetid: 7b373dad-57d5-4696-9b29-a6c351d44fa8
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88ad7a5b278f8f972a518af40d527ff312d0d237
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980390"
---
# <a name="how-to-suspend-resume-and-terminate-orchestration-instances"></a>如何暂停、恢复和终止业务流程实例
本主题介绍如何使用 BizTalk Server 管理控制台来暂停、恢复和终止业务流程的一个或多个正在运行的服务实例。 服务实例是实例的 BizTalk server 业务流程处理或的已序列化到 MessageBox 中以便进一步处理或跟踪。  
  
 下面描述了这三个操作的影响：  
  
-   **挂起。** 这将暂停服务实例的运行。 进程内消息将运行到结束。 消息仍传送到服务实例，但不会予以处理。  
  
-   **恢复。** 这将恢复挂起的实例的处理。  
  
> [!NOTE]
>  不能从断点状态恢复某一实例。 恢复此类实例可能会显示“挂起”状态，但该实例最终将失败。  
  
-   **终止。** 这将终止所有消息处理。 该服务实例将从 BizTalk Server 数据库中删除。 服务实例正在处理的消息也被删除，但未终止的服务实例引用的消息除外。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，则必须以 BizTalk Server Operators 组或 BizTalk Server Administrators 组成员的身份登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-view-start-stop-or-terminate-an-instance-of-an-orchestration"></a>查看业务流程实例的启动、停止或终止  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 选择“BizTalk 组”以显示“组中心”页。  
  
3. 下**正在进行的工作**，单击**正在运行的服务实例**。  
  
    此页下半部分的“查询结果”面板将显示该业务流程的所有实例。  
  
4. 若要修改查询和查看业务流程的不同实例，请单击下面的框**值**有关**搜索**字段中，选择要查看，然后单击实例类型**运行查询**. 有关创建查询的详细信息，请参阅“另请参见”下面的有关搜索的主题。  
  
5. 右键单击的实例，单击**挂起**，**恢复**，或**终止**。 使用此功能可以选择要恢复哪些实例。  
  
   > [!NOTE]
   >  若要对多个实例执行该操作，请在按住 CTRL 键的同时单击所需实例。 右键单击实例，然后单击**挂起**，**恢复**，或**终止**。  
  
    [服务实例状态](../core/service-instance-states.md)提供了有关挂起状态的详细信息。  
  
## <a name="see-also"></a>请参阅  
 [管理业务流程](../core/managing-orchestrations.md)   
 [如何搜索正在运行的服务实例](../core/how-to-search-for-running-service-instances.md)   
 [如何搜索挂起的服务实例](../core/how-to-search-for-suspended-service-instances.md)