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
ms.openlocfilehash: 7ede4f048f8dd95fe052774c3e3f621133ce8e99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333869"
---
# <a name="how-to-suspend-resume-and-terminate-orchestration-instances"></a>如何暂停、 恢复和终止业务流程实例
本主题介绍如何暂停、 继续和终止一个或多个使用 BizTalk Server 管理控制台中运行的业务流程服务实例。 服务实例是实例的 BizTalk server 业务流程处理或的已序列化到 MessageBox 中以便进一步处理或跟踪。  
  
 下面介绍这三个操作的效果：  
  
-   **挂起。** 此操作可暂停服务实例。 进程内消息运行完成。 消息仍传送到服务实例，但不是会处理。  
  
-   **恢复。** 这将恢复挂起的实例的处理。  
  
> [!NOTE]
>  不能恢复从断点状态实例。 恢复此类实例可能会显示"挂起"状态，但该实例最终将失败。  
  
-   **终止。** 这将终止所有消息处理。 从 BizTalk Server 数据库中删除服务实例。 服务实例正在处理的消息也会删除，但还未终止的服务实例引用的任何消息除外。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须以 BizTalk Server Operators 组或 BizTalk Server Administrators 组的成员的身份登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-view-start-stop-or-terminate-an-instance-of-an-orchestration"></a>若要查看开始，停止或终止的业务流程实例  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 选择要显示组中心页的 BizTalk 组。  
  
3. 下**正在进行的工作**，单击**正在运行的服务实例**。  
  
    查询结果窗格中的页的下半部分中显示业务流程的所有的实例。  
  
4. 若要修改查询和查看业务流程的不同实例，请单击下面的框**值**有关**搜索**字段中，选择要查看，然后单击实例类型**运行查询**. 有关创建查询的详细信息，请参阅另请参阅下面的有关搜索的主题。  
  
5. 右键单击的实例，单击**挂起**，**恢复**，或**终止**。 此功能，可选择要恢复哪些实例。  
  
   > [!NOTE]
   >  若要执行多个实例上的操作，请按住 CTRL 键并单击所需的实例。 右键单击实例，然后单击**挂起**，**恢复**，或**终止**。  
  
    [服务实例状态](../core/service-instance-states.md)提供了有关挂起状态的详细信息。  
  
## <a name="see-also"></a>请参阅  
 [管理业务流程](../core/managing-orchestrations.md)   
 [如何搜索正在运行的服务实例](../core/how-to-search-for-running-service-instances.md)   
 [如何搜索挂起的服务实例](../core/how-to-search-for-suspended-service-instances.md)