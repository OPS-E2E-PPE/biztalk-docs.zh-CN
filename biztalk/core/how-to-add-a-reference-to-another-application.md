---
title: 如何添加对另一个应用程序的引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, referencing
ms.assetid: 6a177560-ee1f-403a-a68a-ade409a39a35
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9789cbc346530445d4204592f632dc4e48394ba0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343613"
---
# <a name="how-to-add-a-reference-to-another-application"></a>如何添加对另一个应用程序的引用
本主题介绍如何使用 BizTalk Server 管理控制台从一个应用程序到另一个应用程序添加的引用。 当您使用导入你的应用程序导入向导中，如中所述，还可以添加其他应用程序的引用[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。  
  
 当你想要在同一 BizTalk 组中的另一个应用程序中已存在的当前应用程序中使用项目时添加的引用。 这是因为大多数类型的项目必须是 BizTalk 组中唯一。 而不是将重复的项目添加到当前应用程序，您将添加对其他应用程序已包含的项目的引用。 有关详细信息，请参阅[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)。  
  
 不需要添加的引用，当你想要使用的虚拟目录或另一个应用程序中已存在的证书。 此外，我们建议不要执行此操作，因为它可以创建一个循环引用。  
  
 导入具有依存关系的应用程序时，可以同时导入的引用。 添加到另一个应用程序引用时，请记住，这会影响您部署这两个应用程序的方式。 有关详细信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-add-a-reference-to-another-application"></a>若要添加另一个应用程序的引用  
  
1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击想要创建的引用应用程序。 这是想要使用的项目的另一个应用程序中包含的应用程序。  
  
3. 指向**外**，然后单击**引用**。  
  
4. 在中**应用程序**，选择你想要添加的引用 （包含的应用程序的项目或你想要使用的项目），应用程序，然后单击复选框**确定**。  
  
    将引用添加到当前应用程序。 在控制台树中，手状图标添加到此应用程序，以指示它引用由其他应用中的一个或多个程序中引用的应用程序。  
  
    ![共享应用程序图标](../core/media/sharedapplicationicon.gif "SharedApplicationIcon")  
  
## <a name="see-also"></a>请参阅  
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)