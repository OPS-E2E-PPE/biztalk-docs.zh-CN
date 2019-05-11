---
title: 如何查看应用程序的引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, viewing
- applications, referencing
ms.assetid: 5f1026e1-c73e-495d-8160-9ba68f38b9d8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fef2390710a90a9b03f9e6b791e873a358414b50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383085"
---
# <a name="how-to-view-the-references-of-an-application"></a><span data-ttu-id="5c46f-102">如何查看应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="5c46f-102">How to View the References of an Application</span></span>
<span data-ttu-id="5c46f-103">本主题介绍如何使用 BizTalk Server 管理控制台来查看当前应用程序可以引用的应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="5c46f-103">This topic describes how to use the BizTalk Server Administration console to view the list of applications to which the current application has references.</span></span> <span data-ttu-id="5c46f-104">有关添加引用的详细信息，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。</span><span class="sxs-lookup"><span data-stu-id="5c46f-104">For more information about adding references, see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span> <span data-ttu-id="5c46f-105">此外可以查看应用程序具有对此应用程序的引用的列表。</span><span class="sxs-lookup"><span data-stu-id="5c46f-105">You can also view the list of applications that have references to this application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5c46f-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="5c46f-106">Prerequisites</span></span>  
 <span data-ttu-id="5c46f-107">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="5c46f-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="5c46f-108">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="5c46f-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-the-references-for-an-application"></a><span data-ttu-id="5c46f-109">若要查看应用程序引用</span><span class="sxs-lookup"><span data-stu-id="5c46f-109">To view the references for an application</span></span>  
  
1. <span data-ttu-id="5c46f-110">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="5c46f-110">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="5c46f-111">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击你想要查看，请单击其引用的应用程序**属性**。</span><span class="sxs-lookup"><span data-stu-id="5c46f-111">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click the application whose references you want to view, and click **Properties**.</span></span>  
  
3. <span data-ttu-id="5c46f-112">在属性页的左窗格中，单击**引用**。</span><span class="sxs-lookup"><span data-stu-id="5c46f-112">In the left pane of the properties page, click **References**.</span></span>  
  
    <span data-ttu-id="5c46f-113">在右窗格的上半部分列出了此应用程序引用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5c46f-113">The applications to which this application refers are listed in the upper section of the right pane.</span></span> <span data-ttu-id="5c46f-114">在右窗格的下半部分列出了引用此应用程序的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5c46f-114">The applications that refer to this application are listed in the lower section of the right pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c46f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c46f-115">See Also</span></span>  
 [<span data-ttu-id="5c46f-116">创建和修改 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="5c46f-116">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)