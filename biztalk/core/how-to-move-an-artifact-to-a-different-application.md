---
title: 如何将项目移到不同的应用程序 |Microsoft 文档
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
ms.openlocfilehash: fdc28eb92b09d459ba5f05439572f07e3f35411f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254453"
---
# <a name="how-to-move-an-artifact-to-a-different-application"></a><span data-ttu-id="7aeb4-102">如何将项目移到不同的应用程序</span><span class="sxs-lookup"><span data-stu-id="7aeb4-102">How to Move an Artifact to a Different Application</span></span>
<span data-ttu-id="7aeb4-103">本主题介绍如何使用 BizTalk Server 管理控制台的“移至应用程序”命令，在 BizTalk 组内的应用程序间移动项目。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-103">This topic describes how to move an artifact from one application to another within a BizTalk group by using the Move To Application command of the BizTalk Server Administration console.</span></span> <span data-ttu-id="7aeb4-104">如果需要使用位于同一 BizTalk 组内的其他应用程序中已有的项目，可能就要进行这种移动。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-104">You might want to do this if you need to use an artifact that already exists in one application in a different application in the same BizTalk group.</span></span>  
  
 <span data-ttu-id="7aeb4-105">移动项目时，请注意以下重要事项：</span><span class="sxs-lookup"><span data-stu-id="7aeb4-105">When moving an artifact, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="7aeb4-106">**应用程序必须位于相同的组。**</span><span class="sxs-lookup"><span data-stu-id="7aeb4-106">**The applications must be in the same group.**</span></span> <span data-ttu-id="7aeb4-107">只有当项目的移出应用程序和移入应用程序属于同一组时，“移至应用程序”命令才有效。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-107">The Move To Application command only works if the application from which you want to move the artifact is in the same BizTalk group as the application to which you want to move the artifact.</span></span> <span data-ttu-id="7aeb4-108">如果要将项目移至不同组中的应用程序，您可以先将该项目从目前所在的应用程序中导出，然后将其导入新应用程序，也可以将该项目添加到目标应用程序中。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-108">If you want to move the artifact to an application in a different group, you can either export the artifact from the application in which it currently exists and then import it into the new application, or add the artifact to the application.</span></span> <span data-ttu-id="7aeb4-109">有关说明，请参阅[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)，[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)，和[如何创建或添加项目](../core/how-to-create-or-add-an-artifact.md)。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-109">For instructions, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md), [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md), and [How to Create or Add an Artifact](../core/how-to-create-or-add-an-artifact.md).</span></span> <span data-ttu-id="7aeb4-110">然后，你必须手动删除项目从原始应用程序中所述[如何从应用程序中删除项目](../core/how-to-remove-an-artifact-from-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-110">You must then manually remove the artifact from the original application, as described in [How to Remove an Artifact from an Application](../core/how-to-remove-an-artifact-from-an-application.md).</span></span>  
  
-   <span data-ttu-id="7aeb4-111">**移动项目可能同时移动的项目在其它依赖或依赖于它。**</span><span class="sxs-lookup"><span data-stu-id="7aeb4-111">**Moving an artifact may also move artifacts on which it depends or that depend on it.**</span></span> <span data-ttu-id="7aeb4-112">将项目移向新应用程序时，该项目所依赖的其他所有项目也会被移动，除非此新应用程序有对包含移动项目所依赖项目的应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-112">When you move an artifact to a new application, any other artifacts on which it has dependencies are also moved unless the new application has a reference to the application(s) containing the artifacts on which the moved artifact depends.</span></span> <span data-ttu-id="7aeb4-113">同样，依赖于移动项目的所有项目也会被移动，除非包含这些项目的应用程序有对新应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-113">Also, any artifacts that have dependencies on the moved artifact are moved unless the application(s) containing them have a reference to the new application.</span></span> <span data-ttu-id="7aeb4-114">当移动项目，你会看到的其他项目，也将被移动的列表。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-114">When moving an artifact, you are shown the list of other artifacts that will also be moved.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7aeb4-115">如果您要在两个或多个应用程序中使用同一个项目，可能需要创建从要使用该项目的应用程序到该项目当前所在应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-115">If you need to use the same artifact in two or more applications, you may need to create a reference from the application in which you want to use the artifact to the one currently containing the artifact.</span></span> <span data-ttu-id="7aeb4-116">这是因为某些类型的项目在一个 BizTalk 组中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-116">This is because certain types of artifacts must be unique in a BizTalk group.</span></span> <span data-ttu-id="7aeb4-117">有关详细信息，请参阅[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-117">For more information, see [Artifacts That Must Be Unique in an Application or Group](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).</span></span> <span data-ttu-id="7aeb4-118">有关添加引用的说明，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-118">For instructions on adding references, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span> <span data-ttu-id="7aeb4-119">请注意，添加对其他应用程序的引用会在应用程序间建立依赖关系，这会影响您部署这些应用程序的方式。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-119">Be aware that adding a reference to another application creates dependencies between the applications and affects the way you must deploy them.</span></span> <span data-ttu-id="7aeb4-120">有关背景信息，请参阅[依赖关系和应用程序部署](../core/dependencies-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-120">For background information, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7aeb4-121">先决条件</span><span class="sxs-lookup"><span data-stu-id="7aeb4-121">Prerequisites</span></span>  
 <span data-ttu-id="7aeb4-122">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-122">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="7aeb4-123">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-123">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-move-an-artifact-to-a-different-application"></a><span data-ttu-id="7aeb4-124">将项目移到其他应用程序</span><span class="sxs-lookup"><span data-stu-id="7aeb4-124">To move an artifact to a different application</span></span>  
  
1.  <span data-ttu-id="7aeb4-125">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-125">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="7aeb4-126">在控制台树中，依次展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、BizTalk 组和要从中移出项目的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-126">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, and then expand the application from which you want to move an artifact.</span></span>  
  
3.  <span data-ttu-id="7aeb4-127">单击包含你想要移动，右键单击该项目，然后单击该项目的文件夹**将移到应用程序**。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-127">Click the folder containing the artifact that you want to move, right-click the artifact, and then click **Move To Application**.</span></span>  
  
4.  <span data-ttu-id="7aeb4-128">在**目标应用程序**框中，单击箭头，，然后单击你要移动项目的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-128">In the **Destination application** box, click the arrow, and then click the application to which you want to move the artifact.</span></span>  
  
     <span data-ttu-id="7aeb4-129">**移动项目**框会显示移动，以及所有依赖的项目，也将被移动的项目。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-129">The **Moving Artifacts** box displays the artifact to move, along with all dependent artifacts, which will be moved as well.</span></span>  
  
5.  <span data-ttu-id="7aeb4-130">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="7aeb4-130">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aeb4-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7aeb4-131">See Also</span></span>  
 [<span data-ttu-id="7aeb4-132">创建和修改 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="7aeb4-132">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)