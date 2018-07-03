---
title: 如何将项目移到不同的应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, moving
- applications, artifacts
ms.assetid: 861e7782-0566-4478-a0bd-f8ced1ea6d56
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a76da726672d122935d6c7b393b403f11bb9068
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993502"
---
# <a name="how-to-move-an-artifact-to-a-different-application"></a>如何将项目移到不同的应用程序
本主题介绍如何使用 BizTalk Server 管理控制台的“移至应用程序”命令，在 BizTalk 组内的应用程序间移动项目。 如果需要使用位于同一 BizTalk 组内的其他应用程序中已有的项目，可能就要进行这种移动。  
  
 移动项目时，请注意以下重要事项：  
  
-   **应用程序必须位于同一组中。** 只有当项目的移出应用程序和移入应用程序属于同一组时，“移至应用程序”命令才有效。 如果要将项目移至不同组中的应用程序，您可以先将该项目从目前所在的应用程序中导出，然后将其导入新应用程序，也可以将该项目添加到目标应用程序中。 有关说明，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)，[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)，并[如何创建或添加项目](../core/how-to-create-or-add-an-artifact.md)。 您必须然后手动删除该项目从原始应用程序，如中所述[如何从应用程序中删除项目](../core/how-to-remove-an-artifact-from-an-application.md)。  
  
-   **移动项目也可能会移在其它依赖或依赖于它的项目。** 将项目移向新应用程序时，该项目所依赖的其他所有项目也会被移动，除非此新应用程序有对包含移动项目所依赖项目的应用程序的引用。 同样，依赖于移动项目的所有项目也会被移动，除非包含这些项目的应用程序有对新应用程序的引用。 当移动项目，将显示一起移动的其他项目的列表。  
  
> [!NOTE]
>  如果您要在两个或多个应用程序中使用同一个项目，可能需要创建从要使用该项目的应用程序到该项目当前所在应用程序的引用。 这是因为某些类型的项目在一个 BizTalk 组中必须是唯一的。 有关详细信息，请参阅[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)。 有关添加引用的说明，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。 请注意，添加对其他应用程序的引用会在应用程序间建立依赖关系，这会影响您部署这些应用程序的方式。 有关背景信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-move-an-artifact-to-a-different-application"></a>将项目移到其他应用程序  
  
1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，依次展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、BizTalk 组和要从中移出项目的应用程序。  
  
3. 单击包含你想要移动，右键单击该项目，然后单击该项目的文件夹**移至应用程序**。  
  
4. 在中**目标应用程序**框，单击箭头，然后单击你想要将项目移到该应用的程序。  
  
    **移动项目**框将显示要移动，以及所有依赖的项目，将同时移动的项目。  
  
5. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)