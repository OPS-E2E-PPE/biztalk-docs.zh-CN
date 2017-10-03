---
title: "如何更改应用程序的名称 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- naming conventions, renaming
- naming conventions, applications
- applications, renaming
ms.assetid: ae59c792-44bd-43e0-a4ae-e67bcad2e128
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4826688935bf18cd5288924d4544f484b3dcf0cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-name-of-an-application"></a><span data-ttu-id="6e5c1-102">如何更改应用程序的名称</span><span class="sxs-lookup"><span data-stu-id="6e5c1-102">How to Change the Name of an Application</span></span>
<span data-ttu-id="6e5c1-103">本主题介绍如何使用 BizTalk Server 管理控制台更改应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="6e5c1-103">This topic describes how to use the BizTalk Server Administration console to change the name of an application.</span></span> <span data-ttu-id="6e5c1-104">您使用的应用程序名称不能已存在于该组中。</span><span class="sxs-lookup"><span data-stu-id="6e5c1-104">The application name that you use cannot already exist in the group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e5c1-105">如果您为具有对重命名应用程序的引用的应用程序导出某一 .msi 文件，则在您导入该 .msi 文件时，该引用将不再有效。</span><span class="sxs-lookup"><span data-stu-id="6e5c1-105">If you have exported an .msi file for an application that has a reference to the renamed application, the reference will no longer function when you import the .msi file.</span></span> <span data-ttu-id="6e5c1-106">您将需要使用新的应用程序名称更新该引用。</span><span class="sxs-lookup"><span data-stu-id="6e5c1-106">You will need to update the reference with the new application name.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6e5c1-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="6e5c1-107">Prerequisites</span></span>  
 <span data-ttu-id="6e5c1-108">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="6e5c1-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="6e5c1-109">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="6e5c1-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-change-the-name-of-an-application"></a><span data-ttu-id="6e5c1-110">更改应用程序的名称</span><span class="sxs-lookup"><span data-stu-id="6e5c1-110">To change the name of an application</span></span>  
  
1.  <span data-ttu-id="6e5c1-111">单击**启动**，指向**程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="6e5c1-111">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6e5c1-112">在控制台树中，展开**BizTalk Server 管理**，右键单击你想要更改，然后单击其名称的应用**属性**。</span><span class="sxs-lookup"><span data-stu-id="6e5c1-112">In the console tree, expand  **BizTalk Server Administration**, right-click the application whose name you want to change, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="6e5c1-113">在**名称**框中，键入应用程序的新名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6e5c1-113">In the **Name** box, type a new name for the application, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e5c1-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e5c1-114">See Also</span></span>  
 [<span data-ttu-id="6e5c1-115">创建和修改 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="6e5c1-115">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)