---
title: "如何从应用程序删除映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, maps
- deleting, maps
- managing [maps], deleting
- managing [maps], applications
ms.assetid: 27d9bb08-36f0-46ff-ae9a-2247be6e3f96
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8b264809306e2cda40cc44be1287b6c2426fb43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-a-map-from-an-application"></a>如何从应用程序中删除映射
本主题介绍如何使用 BizTalk Server 管理控制台从 BizTalk 应用程序中删除映射。 您可能要在部署某一映射的新版本后删除该映射。 有关详细信息和更新应用程序项目的重要注意事项，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。  
  
 删除某一映射时，将发生以下情况：  
  
-   该映射将从 BizTalk 管理数据库中删除。  
  
-   将从 BizTalk 管理数据库中删除包含该映射的 BizTalk 程序集；但如果该程序集还存在于本地文件系统或全局程序集缓存 (GAC) 中，则不会将这两个位置中的该程序集删除。  
  
-   一旦删除该 BizTalk 程序集，该程序集中所包含的所有项目也将从 BizTalk 管理数据库中删除。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-remove-a-map"></a>删除映射  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开包含地图的 BizTalk 组若要删除，，然后展开包含映射的应用程序。  
  
3.  单击**地图**文件夹，右键单击图，，然后单击**删除**。  
  
> [!NOTE]
>  若要删除多个映射，请按住 shift 键，单击以删除，右键单击其中一个映射，然后单击每个映射**删除**。  
  
## <a name="see-also"></a>另请参阅  
 [管理映射](../core/managing-maps.md)   
 [如何从应用程序删除 BizTalk 程序集](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)   
 [正在取消部署的 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)