---
title: "如何配置跟踪架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, configuring
- managing [schemas], configuring
- configuring [HAT tracking], schemas
- configuring, schemas
- configuring, tracking
- HAT, schemas
- managing [schemas], tracking
- schemas, tracking
- tracking, configuring
- tracking, schemas
ms.assetid: b5f69c98-8824-43b1-8f21-d84b60ac5431
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e15cb2210062901786b179ec75fe3880dea660b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-schema"></a>如何为架构配置跟踪
本主题介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台为架构配置跟踪。 若要配置跟踪，请指定要在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台的“组中心”页的查询视图中查看的消息属性。  
  
 有关创建和使用查询的详细信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。 有关跟踪的功能的消息事件和服务实例的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 若只查看跟踪选项，则可以 BizTalk Server Operators 组成员的身份登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-tracking-for-a-schema"></a>为架构配置跟踪  
  
1.  单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开包含你想要配置跟踪的架构的 BizTalk 组，然后展开包含架构的应用程序。  
  
3.  单击**架构**，右键单击的架构，然后单击**属性**。  
  
4.  在左窗格中，单击**跟踪**。  
  
5.  执行下列操作来指定的属性，用于跟踪消息，其中一项，然后单击**确定**:  
  
    -   选择**选择所有消息属性**复选框以将所有列出的属性。  
  
        > [!NOTE]
        >  此复选框仅对包含升级属性的架构可用。  
  
    -   选中所要使用的每个属性的复选框。  
  
        > [!NOTE]
        >  这是仅适用于包含提升的属性的架构。  
  
> [!NOTE]
>  您只应选择您所需要选项，因为跟踪消息将会增加系统的性能和存储的开销。  
  
## <a name="see-also"></a>另请参阅  
 [管理架构](../core/managing-schemas.md)