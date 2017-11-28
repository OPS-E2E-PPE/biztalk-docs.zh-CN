---
title: "如何查看应用程序的引用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, viewing
- applications, referencing
ms.assetid: 5f1026e1-c73e-495d-8160-9ba68f38b9d8
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 249e7432216368113e916118910acb6a4e11e415
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-view-the-references-of-an-application"></a><span data-ttu-id="f633c-102">如何查看应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="f633c-102">How to View the References of an Application</span></span>
<span data-ttu-id="f633c-103">本主题介绍如何使用 BizTalk Server 管理控制台查看当前应用程序引用的应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="f633c-103">This topic describes how to use the BizTalk Server Administration console to view the list of applications to which the current application has references.</span></span> <span data-ttu-id="f633c-104">有关如何添加引用的详细信息，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f633c-104">For more information about adding references, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span> <span data-ttu-id="f633c-105">您还可以查看引用了此应用程序的应用程序列表。</span><span class="sxs-lookup"><span data-stu-id="f633c-105">You can also view the list of applications that have references to this application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f633c-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="f633c-106">Prerequisites</span></span>  
 <span data-ttu-id="f633c-107">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f633c-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="f633c-108">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f633c-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-the-references-for-an-application"></a><span data-ttu-id="f633c-109">若要查看应用程序引用</span><span class="sxs-lookup"><span data-stu-id="f633c-109">To view the references for an application</span></span>  
  
1.  <span data-ttu-id="f633c-110">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="f633c-110">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="f633c-111">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击你想要查看，然后单击其引用的应用**属性**。</span><span class="sxs-lookup"><span data-stu-id="f633c-111">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click the application whose references you want to view, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f633c-112">在属性页的左窗格中，单击**引用**。</span><span class="sxs-lookup"><span data-stu-id="f633c-112">In the left pane of the properties page, click **References**.</span></span>  
  
     <span data-ttu-id="f633c-113">此应用程序引用的应用程序将在右窗格的上半部分列出。</span><span class="sxs-lookup"><span data-stu-id="f633c-113">The applications to which this application refers are listed in the upper section of the right pane.</span></span> <span data-ttu-id="f633c-114">引用此应用程序的应用程序将在右窗格的下半部分列出。</span><span class="sxs-lookup"><span data-stu-id="f633c-114">The applications that refer to this application are listed in the lower section of the right pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f633c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f633c-115">See Also</span></span>  
 [<span data-ttu-id="f633c-116">创建和修改 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="f633c-116">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)