---
title: 如何添加对另一个应用程序的引用 |Microsoft 文档
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
ms.openlocfilehash: 25668e7cfcb7d810d999c01eef28e5116b46c298
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-reference-to-another-application"></a><span data-ttu-id="ab56e-102">如何添加对另一个应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="ab56e-102">How to Add a Reference to Another Application</span></span>
<span data-ttu-id="ab56e-103">本主题介绍如何使用 BizTalk Server 管理控制台从一个应用程序添加对另一应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="ab56e-103">This topic describes how to use the BizTalk Server Administration console to add a reference from one application to another application.</span></span> <span data-ttu-id="ab56e-104">你还可以添加对其他应用程序的引用，当使用导入你的应用程序导入向导中中, 所述[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ab56e-104">You can also add a reference to the other application when you import your application by using the Import Wizard, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
 <span data-ttu-id="ab56e-105">如果需要在当前应用程序中使用在同一 BizTalk 组中的另一应用程序中已存在的项目，就要添加引用。</span><span class="sxs-lookup"><span data-stu-id="ab56e-105">You add a reference when you want to use an artifact in the current application that already exists in another application in the same BizTalk group.</span></span> <span data-ttu-id="ab56e-106">这是因为大多数类型的项目在一个 BizTalk 组中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ab56e-106">This is because most types of artifacts must be unique in a BizTalk group.</span></span> <span data-ttu-id="ab56e-107">您应该添加对已包含该项目的另一应用程序的引用，而不是向当前应用程序添加重复的项目。</span><span class="sxs-lookup"><span data-stu-id="ab56e-107">Rather than adding the duplicate artifact to the current application, you add a reference to the other application that already contains the artifact.</span></span> <span data-ttu-id="ab56e-108">有关详细信息，请参阅[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)。</span><span class="sxs-lookup"><span data-stu-id="ab56e-108">For more information, see [Artifacts That Must Be Unique in an Application or Group](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).</span></span>  
  
 <span data-ttu-id="ab56e-109">当您需要使用在另一应用程序中已存在的虚拟目录或证书时，不一定要添加引用。</span><span class="sxs-lookup"><span data-stu-id="ab56e-109">It is not necessary to add a reference when you want to use a virtual directory or a certificate that already exists in another application.</span></span> <span data-ttu-id="ab56e-110">而且，我们不建议您添加引用，因为这样做会生成循环引用。</span><span class="sxs-lookup"><span data-stu-id="ab56e-110">Furthermore, we recommend against doing this because it can create a circular reference.</span></span>  
  
 <span data-ttu-id="ab56e-111">导入具有依存关系的应用程序时，也可以导入引用。</span><span class="sxs-lookup"><span data-stu-id="ab56e-111">When you import an application that has dependencies, references can be imported as well.</span></span> <span data-ttu-id="ab56e-112">添加对另一应用程序的引用时，请记住，这会影响您部署这两个应用程序的方式。</span><span class="sxs-lookup"><span data-stu-id="ab56e-112">When adding a reference to another application, bear in mind that this affects the way you deploy both applications.</span></span> <span data-ttu-id="ab56e-113">有关详细信息，请参阅[依赖关系和应用程序部署](../core/dependencies-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="ab56e-113">For more information, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ab56e-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="ab56e-114">Prerequisites</span></span>  
 <span data-ttu-id="ab56e-115">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ab56e-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="ab56e-116">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ab56e-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-add-a-reference-to-another-application"></a><span data-ttu-id="ab56e-117">添加对其他应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="ab56e-117">To add a reference to another application</span></span>  
  
1.  <span data-ttu-id="ab56e-118">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="ab56e-118">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ab56e-119">在控制台树中，展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击要在其中创建引用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ab56e-119">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and right-click the application in which you want to create a reference.</span></span> <span data-ttu-id="ab56e-120">这是您要在其中使用已包含在另一应用程序中的项目的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ab56e-120">This is the application in which you want to use an artifact that is contained in another application.</span></span>  
  
3.  <span data-ttu-id="ab56e-121">指向**添加**，然后单击**引用**。</span><span class="sxs-lookup"><span data-stu-id="ab56e-121">Point to **Add** and then click **References**.</span></span>  
  
4.  <span data-ttu-id="ab56e-122">在**应用程序**，选择你想要添加的引用 （包含的应用程序的项目或你想要使用的项目），该应用程序，然后单击复选框**确定**。</span><span class="sxs-lookup"><span data-stu-id="ab56e-122">In **Applications**, select the check box of the application to which you want to add a reference (the application containing the artifact or artifacts that you want to use), and then click **OK**.</span></span>  
  
     <span data-ttu-id="ab56e-123">引用即被添加到当前应用程序中。</span><span class="sxs-lookup"><span data-stu-id="ab56e-123">The reference is added to the current application.</span></span> <span data-ttu-id="ab56e-124">在控制台树中，手状图标被添加到您从此应用程序引用的应用程序，以指示它已被一个或多个其他应用程序引用。</span><span class="sxs-lookup"><span data-stu-id="ab56e-124">In the console tree, a hand icon is added to the application that you referred from this application to indicate that it is referenced by one or more other applications.</span></span>  
  
     <span data-ttu-id="ab56e-125">![共享应用程序图标](../core/media/sharedapplicationicon.gif "SharedApplicationIcon")</span><span class="sxs-lookup"><span data-stu-id="ab56e-125">![Shared application icon](../core/media/sharedapplicationicon.gif "SharedApplicationIcon")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab56e-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab56e-126">See Also</span></span>  
 [<span data-ttu-id="ab56e-127">创建和修改 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="ab56e-127">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)