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
# <a name="how-to-move-an-artifact-to-a-different-application"></a><span data-ttu-id="bbf5c-102">如何将项目移到不同的应用程序</span><span class="sxs-lookup"><span data-stu-id="bbf5c-102">How to Move an Artifact to a Different Application</span></span>
<span data-ttu-id="bbf5c-103">本主题介绍如何通过使用 BizTalk Server 管理控制台的移至应用程序命令将项目移动到 BizTalk 组中的另一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-103">This topic describes how to move an artifact from one application to another within a BizTalk group by using the Move To Application command of the BizTalk Server Administration console.</span></span> <span data-ttu-id="bbf5c-104">您可能想要执行此操作，如果您需要使用同一个 BizTalk 组中的不同应用程序中的一个应用程序中已存在的项目。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-104">You might want to do this if you need to use an artifact that already exists in one application in a different application in the same BizTalk group.</span></span>  
  
 <span data-ttu-id="bbf5c-105">当移动项目，请记住以下重要事项：</span><span class="sxs-lookup"><span data-stu-id="bbf5c-105">When moving an artifact, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="bbf5c-106">**应用程序必须位于同一组中。**</span><span class="sxs-lookup"><span data-stu-id="bbf5c-106">**The applications must be in the same group.**</span></span> <span data-ttu-id="bbf5c-107">当你想要将项目移的应用程序是与应用程序想要将项目移到同一 BizTalk 组中，移至应用程序命令才有效。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-107">The Move To Application command only works if the application from which you want to move the artifact is in the same BizTalk group as the application to which you want to move the artifact.</span></span> <span data-ttu-id="bbf5c-108">如果你想要将项目移到另一个组中的应用程序，您可以将该项目导出从应用程序在其中它当前存在然后将其导入新的应用程序，或将项目添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-108">If you want to move the artifact to an application in a different group, you can either export the artifact from the application in which it currently exists and then import it into the new application, or add the artifact to the application.</span></span> <span data-ttu-id="bbf5c-109">有关说明，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)，[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)，并[如何创建或添加项目](../core/how-to-create-or-add-an-artifact.md)。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-109">For instructions, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md), [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md), and [How to Create or Add an Artifact](../core/how-to-create-or-add-an-artifact.md).</span></span> <span data-ttu-id="bbf5c-110">您必须然后手动删除该项目从原始应用程序，如中所述[如何从应用程序中删除项目](../core/how-to-remove-an-artifact-from-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-110">You must then manually remove the artifact from the original application, as described in [How to Remove an Artifact from an Application](../core/how-to-remove-an-artifact-from-an-application.md).</span></span>  
  
-   <span data-ttu-id="bbf5c-111">**移动项目也可能会移在其它依赖或依赖于它的项目。**</span><span class="sxs-lookup"><span data-stu-id="bbf5c-111">**Moving an artifact may also move artifacts on which it depends or that depend on it.**</span></span> <span data-ttu-id="bbf5c-112">当将项目移到新的应用程序时，它在其具有依赖关系的任何其他项目也被移动，除非新的应用程序具有对包含移动的项目所依赖的项目的应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-112">When you move an artifact to a new application, any other artifacts on which it has dependencies are also moved unless the new application has a reference to the application(s) containing the artifacts on which the moved artifact depends.</span></span> <span data-ttu-id="bbf5c-113">此外，移动项目有依赖关系的任何项目被移动，除非其包含的应用程序具有对新应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-113">Also, any artifacts that have dependencies on the moved artifact are moved unless the application(s) containing them have a reference to the new application.</span></span> <span data-ttu-id="bbf5c-114">当移动项目，将显示一起移动的其他项目的列表。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-114">When moving an artifact, you are shown the list of other artifacts that will also be moved.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbf5c-115">如果需要两个或多个应用程序中使用相同的项目，您可能需要从想要使用到该项目当前所在的一个项目的应用程序创建的引用。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-115">If you need to use the same artifact in two or more applications, you may need to create a reference from the application in which you want to use the artifact to the one currently containing the artifact.</span></span> <span data-ttu-id="bbf5c-116">这是因为某些类型的项目必须是 BizTalk 组中唯一。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-116">This is because certain types of artifacts must be unique in a BizTalk group.</span></span> <span data-ttu-id="bbf5c-117">有关详细信息，请参阅[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-117">For more information, see [Artifacts That Must Be Unique in an Application or Group](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).</span></span> <span data-ttu-id="bbf5c-118">有关添加引用的说明，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-118">For instructions on adding references, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span> <span data-ttu-id="bbf5c-119">请注意，添加对另一个应用程序的引用创建的应用程序之间的依赖项，并会影响您必须部署它们的方式。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-119">Be aware that adding a reference to another application creates dependencies between the applications and affects the way you must deploy them.</span></span> <span data-ttu-id="bbf5c-120">有关背景信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-120">For background information, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bbf5c-121">先决条件</span><span class="sxs-lookup"><span data-stu-id="bbf5c-121">Prerequisites</span></span>  
 <span data-ttu-id="bbf5c-122">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-122">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="bbf5c-123">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-123">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-move-an-artifact-to-a-different-application"></a><span data-ttu-id="bbf5c-124">若要将项目移到不同的应用程序</span><span class="sxs-lookup"><span data-stu-id="bbf5c-124">To move an artifact to a different application</span></span>  
  
1. <span data-ttu-id="bbf5c-125">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-125">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="bbf5c-126">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，然后展开要从中移出项目的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-126">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, and then expand the application from which you want to move an artifact.</span></span>  
  
3. <span data-ttu-id="bbf5c-127">单击包含你想要移动，右键单击该项目，然后单击该项目的文件夹**移至应用程序**。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-127">Click the folder containing the artifact that you want to move, right-click the artifact, and then click **Move To Application**.</span></span>  
  
4. <span data-ttu-id="bbf5c-128">在中**目标应用程序**框，单击箭头，然后单击你想要将项目移到该应用的程序。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-128">In the **Destination application** box, click the arrow, and then click the application to which you want to move the artifact.</span></span>  
  
    <span data-ttu-id="bbf5c-129">**移动项目**框将显示要移动，以及所有依赖的项目，将同时移动的项目。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-129">The **Moving Artifacts** box displays the artifact to move, along with all dependent artifacts, which will be moved as well.</span></span>  
  
5. <span data-ttu-id="bbf5c-130">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="bbf5c-130">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbf5c-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbf5c-131">See Also</span></span>  
 [<span data-ttu-id="bbf5c-132">创建和修改 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="bbf5c-132">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)