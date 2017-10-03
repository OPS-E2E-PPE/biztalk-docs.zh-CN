---
title: "如何从应用程序中删除架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, schemas
- applications, schemas
- schemas, deleting
- managing [schemas], deleting
- managing [schemas], applications
- schemas, applications
ms.assetid: 17dd5869-b56c-4166-9f02-03e04e691eda
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6535764af00156325c006388a88803207329e5fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-a-schema-from-an-application"></a>如何从应用程序中删除架构
本主题介绍如何使用 BizTalk Server 管理控制台从应用程序中删除架构。 此过程也可以从 BizTalk 管理数据库中删除针对组的架构。 您可能要在部署某一架构的新版本后删除该架构。 有关详细信息和更新应用程序项目的重要注意事项，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。  
  
 在删除某一架构时，如果在应用程序中存在具有相同根命名空间的该架构的前一版本，则该前一版本将处于活动状态。  
  
 删除某一架构时，将发生以下情况：  
  
-   该架构将从 BizTalk 管理数据库中删除。  
  
-   将从 BizTalk 管理数据库中删除包含该架构的 BizTalk 程序集；但如果该程序集还存在于本地文件系统或全局程序集缓存 (GAC) 中，则不会将这两个位置中的该程序集删除。  
  
-   一旦删除该 BizTalk 程序集，该程序集中所包含的所有项目也将从 BizTalk 管理数据库中删除。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-remove-a-schema"></a>若要删除架构  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开包含架构的 BizTalk 组删除和包含架构的应用程序。  
  
3.  单击**架构**，右键单击的架构，然后单击**删除**。  
  
## <a name="see-also"></a>另请参阅  
 [管理架构](../core/managing-schemas.md)