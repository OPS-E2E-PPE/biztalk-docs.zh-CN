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
ms.openlocfilehash: d3a218ecf0bcd952962f32f620d25f8149003c86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335988"
---
# <a name="how-to-move-an-artifact-to-a-different-application"></a>如何将项目移到不同的应用程序
本主题介绍如何通过使用 BizTalk Server 管理控制台的移至应用程序命令将项目移动到 BizTalk 组中的另一个应用程序。 您可能想要执行此操作，如果您需要使用同一个 BizTalk 组中的不同应用程序中的一个应用程序中已存在的项目。  
  
 当移动项目，请记住以下重要事项：  
  
-   **应用程序必须位于同一组中。** 当你想要将项目移的应用程序是与应用程序想要将项目移到同一 BizTalk 组中，移至应用程序命令才有效。 如果你想要将项目移到另一个组中的应用程序，您可以将该项目导出从应用程序在其中它当前存在然后将其导入新的应用程序，或将项目添加到应用程序。 有关说明，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)，[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)，并[如何创建或添加项目](../core/how-to-create-or-add-an-artifact.md)。 您必须然后手动删除该项目从原始应用程序，如中所述[如何从应用程序中删除项目](../core/how-to-remove-an-artifact-from-an-application.md)。  
  
-   **移动项目也可能会移在其它依赖或依赖于它的项目。** 当将项目移到新的应用程序时，它在其具有依赖关系的任何其他项目也被移动，除非新的应用程序具有对包含移动的项目所依赖的项目的应用程序的引用。 此外，移动项目有依赖关系的任何项目被移动，除非其包含的应用程序具有对新应用程序的引用。 当移动项目，将显示一起移动的其他项目的列表。  
  
> [!NOTE]
>  如果需要两个或多个应用程序中使用相同的项目，您可能需要从想要使用到该项目当前所在的一个项目的应用程序创建的引用。 这是因为某些类型的项目必须是 BizTalk 组中唯一。 有关详细信息，请参阅[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)。 有关添加引用的说明，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。 请注意，添加对另一个应用程序的引用创建的应用程序之间的依赖项，并会影响您必须部署它们的方式。 有关背景信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-move-an-artifact-to-a-different-application"></a>若要将项目移到不同的应用程序  
  
1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，然后展开要从中移出项目的应用程序。  
  
3. 单击包含你想要移动，右键单击该项目，然后单击该项目的文件夹**移至应用程序**。  
  
4. 在中**目标应用程序**框，单击箭头，然后单击你想要将项目移到该应用的程序。  
  
    **移动项目**框将显示要移动，以及所有依赖的项目，将同时移动的项目。  
  
5. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)