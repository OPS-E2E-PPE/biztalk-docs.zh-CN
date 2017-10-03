---
title: "如何查看 BizTalk 程序集的依赖关系 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- viewing, dependencies
- assemblies, dependencies
- managing [assemblies], dependencies
- assemblies, viewing
- viewing, assemblies
- managing [assemblies], viewing
ms.assetid: 872abc99-8248-4397-9fcb-24a0ba6f4757
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99fbc09a5adb59691a4914a8ddc341c8034c8bb8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-view-the-dependencies-for-a-biztalk-assembly"></a>如何查看 BizTalk 程序集的依赖关系
本主题介绍如何使用 BizTalk Server 管理控制台来查看与 BizTalk 程序集有依存关系的项目的列表。 有关依赖关系以及它们如何影响应用程序部署的背景信息，请参阅[依赖关系和应用程序部署](../core/dependencies-and-application-deployment.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须以 BizTalk Server Administrators 组或 BizTalk  Operators 组成员的帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-view-the-dependencies-of-a-biztalk-assembly"></a>查看 BizTalk 程序集的依存关系  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、包含要查看依存关系的 BizTalk 程序集的 BizTalk 组和包含该 BizTalk 程序集的应用程序。  
  
3.  单击**资源**文件夹中，右键单击 BizTalk 程序集，并依次**修改**。  
  
4.  单击**依赖关系**选项卡。  
  
     与此 BizTalk 程序集有依存关系的项目的名称和状态将显示在列表中。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BizTalk 程序集](../core/managing-biztalk-assemblies.md)