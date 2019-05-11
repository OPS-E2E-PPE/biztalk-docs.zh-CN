---
title: 如何从应用程序中删除架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, schemas
- applications, schemas
- schemas, deleting
- managing [schemas], deleting
- managing [schemas], applications
- schemas, applications
ms.assetid: 17dd5869-b56c-4166-9f02-03e04e691eda
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c6af6da4606b8a6138bfbed257ac71b492293b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384347"
---
# <a name="how-to-remove-a-schema-from-an-application"></a>如何从应用程序中删除架构
本主题介绍如何使用 BizTalk Server 管理控制台从应用程序中删除架构。 此过程从组以及 BizTalk 管理数据库中删除架构。 您可能想要部署新架构版本后删除架构。 有关详细信息和更新应用程序项目的重要注意事项，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。  
  
 当删除某一架构，并在应用程序中存在具有相同根命名空间的架构的旧版本时，以前的版本将处于活动状态。  
  
 在删除架构，将发生以下情况：  
  
-   从 BizTalk 管理数据库中删除架构。  
  
-   包含架构的 BizTalk 程序集从 BizTalk 管理数据库中删除，但不是会从本地文件系统或全局程序集缓存 (GAC) 中，如果两个位置存在。  
  
-   正在删除 BizTalk 程序集，因此删除所有项目程序集中包含删除了该的 BizTalk 管理数据库。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-remove-a-schema"></a>若要删除某一架构  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开包含该架构的 BizTalk 组删除和包含该架构的应用程序。  
  
3. 单击**架构**，右键单击该架构，然后单击**删除**。  
  
## <a name="see-also"></a>请参阅  
 [管理架构](../core/managing-schemas.md)