---
title: 如何删除对另一个应用程序的引用 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, references
ms.assetid: cc867706-7c56-4386-b7ec-9fd7cf6c83a4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de51adb1a9c42874025527ad458ecb6e3c311b3f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254357"
---
# <a name="how-to-remove-a-reference-to-another-application"></a><span data-ttu-id="c7399-102">如何删除对另一应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="c7399-102">How to Remove a Reference to Another Application</span></span>
<span data-ttu-id="c7399-103">本主题介绍如何使用 BizTalk Server 管理控制台从一个应用程序删除对另一应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="c7399-103">This topic describes how to use the BizTalk Server Administration console to remove a reference from one application to another application.</span></span> <span data-ttu-id="c7399-104">如果不再需要在当前应用程序中使用在同一 BizTalk 组中的另一应用程序中存在的项目，就要删除引用。</span><span class="sxs-lookup"><span data-stu-id="c7399-104">You remove a reference when you no longer need to use an artifact in the current application that exists in another application in the same BizTalk group.</span></span> <span data-ttu-id="c7399-105">添加引用的详细信息，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c7399-105">For more information on adding references, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
 <span data-ttu-id="c7399-106">如果当前应用程序中的项目仍然使用引用应用程序中的项目，删除引用的操作将失败。</span><span class="sxs-lookup"><span data-stu-id="c7399-106">If artifacts in the current application still use artifacts in the referenced application, the operation to remove the reference will fail.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="c7399-107">BizTalk Server 中的每个应用程序都自动包含对 BizTalk.System 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="c7399-107">Every application in BizTalk Server automatically contains a reference to the BizTalk.System application.</span></span> <span data-ttu-id="c7399-108">这是因为 BizTalk.System 包含的项目会被每一个 BizTalk 应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="c7399-108">This is because the artifacts that BizTalk.System contains are used by every BizTalk application.</span></span> <span data-ttu-id="c7399-109">绝不能删除对 BizTalk.System 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="c7399-109">You should never remove a reference to the BizTalk.System application.</span></span> <span data-ttu-id="c7399-110">如果删除了，则应用程序无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="c7399-110">If you do, your application may not function correctly.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c7399-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="c7399-111">Prerequisites</span></span>  
 <span data-ttu-id="c7399-112">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="c7399-112">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="c7399-113">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c7399-113">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-reference-to-another-application"></a><span data-ttu-id="c7399-114">删除对另一应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="c7399-114">To remove a reference to another application</span></span>  
  
1.  <span data-ttu-id="c7399-115">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="c7399-115">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c7399-116">在控制台树中，展开**BizTalk Server 管理**，右键单击你想要删除的引用 （引用另一个应用程序的一个），应用的程序，然后单击**属性**.</span><span class="sxs-lookup"><span data-stu-id="c7399-116">In the console tree, expand  **BizTalk Server Administration**, right-click the application from which you want to remove a reference (the one that refers to another application), and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="c7399-117">在属性页的左窗格中，单击**引用**。</span><span class="sxs-lookup"><span data-stu-id="c7399-117">In the left pane of the properties page, click **References**.</span></span>  
  
4.  <span data-ttu-id="c7399-118">在右窗格中，单击你不再想要引用来自此应用程序中，单击应用程序**删除**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c7399-118">In the right pane, click the application that you no longer want to reference from this application, click **Remove**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7399-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7399-119">See Also</span></span>  
 [<span data-ttu-id="c7399-120">创建和修改 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="c7399-120">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)