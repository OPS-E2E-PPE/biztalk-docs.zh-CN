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
ms.openlocfilehash: 6781ebc9c6cb0c3f7c68dfbbcff683193e15ac15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018548"
---
# <a name="how-to-add-a-reference-to-another-application"></a>如何添加对另一个应用程序的引用
本主题介绍如何使用 BizTalk Server 管理控制台从一个应用程序添加对另一应用程序的引用。 当您使用导入你的应用程序导入向导中，如中所述，还可以添加其他应用程序的引用[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。  
  
 如果需要在当前应用程序中使用在同一 BizTalk 组中的另一应用程序中已存在的项目，就要添加引用。 这是因为大多数类型的项目在一个 BizTalk 组中必须是唯一的。 您应该添加对已包含该项目的另一应用程序的引用，而不是向当前应用程序添加重复的项目。 有关详细信息，请参阅[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)。  
  
 当您需要使用在另一应用程序中已存在的虚拟目录或证书时，不一定要添加引用。 而且，我们不建议您添加引用，因为这样做会生成循环引用。  
  
 导入具有依存关系的应用程序时，也可以导入引用。 添加对另一应用程序的引用时，请记住，这会影响您部署这两个应用程序的方式。 有关详细信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-add-a-reference-to-another-application"></a>添加对其他应用程序的引用  
  
1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击要在其中创建引用的应用程序。 这是您要在其中使用已包含在另一应用程序中的项目的应用程序。  
  
3. 指向**外**，然后单击**引用**。  
  
4. 在中**应用程序**，选择你想要添加的引用 （包含的应用程序的项目或你想要使用的项目），应用程序，然后单击复选框**确定**。  
  
    引用即被添加到当前应用程序中。 在控制台树中，手状图标被添加到您从此应用程序引用的应用程序，以指示它已被一个或多个其他应用程序引用。  
  
    ![共享应用程序图标](../core/media/sharedapplicationicon.gif "SharedApplicationIcon")  
  
## <a name="see-also"></a>请参阅  
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)