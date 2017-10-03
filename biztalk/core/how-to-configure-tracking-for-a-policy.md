---
title: "如何配置策略的跟踪 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, tracking
- HAT, policies
- managing [policies], tracking
- tracking, policies
- managing [policies], configuring
- policies, configuring
- configuring [HAT tracking], policies
- tracking, configuring
ms.assetid: f126e541-c183-4544-8b9d-ca07d2af303e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96fb7607bcdce8143901dabd3cdf6358f21a6a8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-policy"></a>如何配置策略的跟踪
本主题介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台为策略配置跟踪。 您可以选择相应的选项，以便在管理控制台上组中心页的查询视图中查看实例数据、条件结果、操作和议程更新。  
  
 有关创建和使用查询的详细信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。 有关跟踪的功能的消息和服务实例的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-tracking-for-a-policy"></a>为策略配置跟踪  
  
1.  单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开要为其配置跟踪的策略所属的 BizTalk 组和 BizTalk 应用程序。  
  
3.  单击**策略**，右键单击的策略，单击**属性**，然后单击**跟踪**。  
  
4.  下表中所述选择所需的跟踪选项，然后单击**确定**。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**快速活动**|选中此复选框可跟踪对其运行该策略的实例数据。|  
    |**条件计算**|选中此复选框可跟踪所选策略中条件的真/假结果。|  
    |**规则触发**|选中此复选框可跟踪该策略最终触发的操作。|  
    |**安排更新**|选中此复选框可跟踪议程更新。 议程包含一系列值为“True”并需要触发的操作。|  
  
## <a name="see-also"></a>另请参阅  
 [管理策略](../core/managing-policies.md)