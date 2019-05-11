---
title: 如何从应用程序中删除映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, maps
- deleting, maps
- managing [maps], deleting
- managing [maps], applications
ms.assetid: 27d9bb08-36f0-46ff-ae9a-2247be6e3f96
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07bfff864b35869c15922d0a907aa7bb30bc6912
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384405"
---
# <a name="how-to-remove-a-map-from-an-application"></a>如何从应用程序中删除映射
本主题介绍如何使用 BizTalk Server 管理控制台从 BizTalk 应用程序中删除映射。 您可能想要部署的映射的新版本后删除映射。 有关详细信息和更新应用程序项目的重要注意事项，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。  
  
 在删除映射中，将发生以下情况：  
  
-   从 BizTalk 管理数据库中删除该映射。  
  
-   包含该映射的 BizTalk 程序集从 BizTalk 管理数据库中删除，但不是会从本地文件系统或全局程序集缓存 (GAC) 中，如果两个位置存在。  
  
-   正在删除 BizTalk 程序集，因此删除所有项目程序集中包含删除了该的 BizTalk 管理数据库。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-remove-a-map"></a>若要删除映射  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开包含该映射的 BizTalk 组删除，，然后展开包含该映射的应用程序。  
  
3. 单击**Maps**文件夹，右键单击该映射，然后单击**删除**。  
  
> [!NOTE]
>  若要删除多个映射，请按住 shift 键，单击每个映射以删除，右键单击其中一个映射，然后单击**删除**。  
  
## <a name="see-also"></a>请参阅  
 [管理映射](../core/managing-maps.md)   
 [如何从应用程序删除 BizTalk 程序集](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)   
 [取消部署 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)