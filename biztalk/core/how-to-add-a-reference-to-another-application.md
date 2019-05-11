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
# <a name="how-to-add-a-reference-to-another-application"></a><span data-ttu-id="f0192-102">如何添加对另一个应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="f0192-102">How to Add a Reference to Another Application</span></span>
<span data-ttu-id="f0192-103">本主题介绍如何使用 BizTalk Server 管理控制台从一个应用程序到另一个应用程序添加的引用。</span><span class="sxs-lookup"><span data-stu-id="f0192-103">This topic describes how to use the BizTalk Server Administration console to add a reference from one application to another application.</span></span> <span data-ttu-id="f0192-104">当您使用导入你的应用程序导入向导中，如中所述，还可以添加其他应用程序的引用[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f0192-104">You can also add a reference to the other application when you import your application by using the Import Wizard, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
 <span data-ttu-id="f0192-105">当你想要在同一 BizTalk 组中的另一个应用程序中已存在的当前应用程序中使用项目时添加的引用。</span><span class="sxs-lookup"><span data-stu-id="f0192-105">You add a reference when you want to use an artifact in the current application that already exists in another application in the same BizTalk group.</span></span> <span data-ttu-id="f0192-106">这是因为大多数类型的项目必须是 BizTalk 组中唯一。</span><span class="sxs-lookup"><span data-stu-id="f0192-106">This is because most types of artifacts must be unique in a BizTalk group.</span></span> <span data-ttu-id="f0192-107">而不是将重复的项目添加到当前应用程序，您将添加对其他应用程序已包含的项目的引用。</span><span class="sxs-lookup"><span data-stu-id="f0192-107">Rather than adding the duplicate artifact to the current application, you add a reference to the other application that already contains the artifact.</span></span> <span data-ttu-id="f0192-108">有关详细信息，请参阅[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)。</span><span class="sxs-lookup"><span data-stu-id="f0192-108">For more information, see [Artifacts That Must Be Unique in an Application or Group](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).</span></span>  
  
 <span data-ttu-id="f0192-109">不需要添加的引用，当你想要使用的虚拟目录或另一个应用程序中已存在的证书。</span><span class="sxs-lookup"><span data-stu-id="f0192-109">It is not necessary to add a reference when you want to use a virtual directory or a certificate that already exists in another application.</span></span> <span data-ttu-id="f0192-110">此外，我们建议不要执行此操作，因为它可以创建一个循环引用。</span><span class="sxs-lookup"><span data-stu-id="f0192-110">Furthermore, we recommend against doing this because it can create a circular reference.</span></span>  
  
 <span data-ttu-id="f0192-111">导入具有依存关系的应用程序时，可以同时导入的引用。</span><span class="sxs-lookup"><span data-stu-id="f0192-111">When you import an application that has dependencies, references can be imported as well.</span></span> <span data-ttu-id="f0192-112">添加到另一个应用程序引用时，请记住，这会影响您部署这两个应用程序的方式。</span><span class="sxs-lookup"><span data-stu-id="f0192-112">When adding a reference to another application, bear in mind that this affects the way you deploy both applications.</span></span> <span data-ttu-id="f0192-113">有关详细信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="f0192-113">For more information, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f0192-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="f0192-114">Prerequisites</span></span>  
 <span data-ttu-id="f0192-115">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f0192-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="f0192-116">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f0192-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-add-a-reference-to-another-application"></a><span data-ttu-id="f0192-117">若要添加另一个应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="f0192-117">To add a reference to another application</span></span>  
  
1. <span data-ttu-id="f0192-118">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="f0192-118">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="f0192-119">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击想要创建的引用应用程序。</span><span class="sxs-lookup"><span data-stu-id="f0192-119">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and right-click the application in which you want to create a reference.</span></span> <span data-ttu-id="f0192-120">这是想要使用的项目的另一个应用程序中包含的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f0192-120">This is the application in which you want to use an artifact that is contained in another application.</span></span>  
  
3. <span data-ttu-id="f0192-121">指向**外**，然后单击**引用**。</span><span class="sxs-lookup"><span data-stu-id="f0192-121">Point to **Add** and then click **References**.</span></span>  
  
4. <span data-ttu-id="f0192-122">在中**应用程序**，选择你想要添加的引用 （包含的应用程序的项目或你想要使用的项目），应用程序，然后单击复选框**确定**。</span><span class="sxs-lookup"><span data-stu-id="f0192-122">In **Applications**, select the check box of the application to which you want to add a reference (the application containing the artifact or artifacts that you want to use), and then click **OK**.</span></span>  
  
    <span data-ttu-id="f0192-123">将引用添加到当前应用程序。</span><span class="sxs-lookup"><span data-stu-id="f0192-123">The reference is added to the current application.</span></span> <span data-ttu-id="f0192-124">在控制台树中，手状图标添加到此应用程序，以指示它引用由其他应用中的一个或多个程序中引用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f0192-124">In the console tree, a hand icon is added to the application that you referred from this application to indicate that it is referenced by one or more other applications.</span></span>  
  
    <span data-ttu-id="f0192-125">![共享应用程序图标](../core/media/sharedapplicationicon.gif "SharedApplicationIcon")</span><span class="sxs-lookup"><span data-stu-id="f0192-125">![Shared application icon](../core/media/sharedapplicationicon.gif "SharedApplicationIcon")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0192-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0192-126">See Also</span></span>  
 [<span data-ttu-id="f0192-127">创建和修改 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="f0192-127">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)