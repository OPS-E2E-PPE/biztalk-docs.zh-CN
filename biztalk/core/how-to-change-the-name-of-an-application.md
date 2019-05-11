---
title: 如何更改应用程序的名称 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- naming conventions, renaming
- naming conventions, applications
- applications, renaming
ms.assetid: ae59c792-44bd-43e0-a4ae-e67bcad2e128
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0937e286e0416fbc4d56d155428872144034febc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342449"
---
# <a name="how-to-change-the-name-of-an-application"></a><span data-ttu-id="53222-102">如何更改应用程序的名称</span><span class="sxs-lookup"><span data-stu-id="53222-102">How to Change the Name of an Application</span></span>
<span data-ttu-id="53222-103">本主题介绍如何使用 BizTalk Server 管理控制台来更改应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="53222-103">This topic describes how to use the BizTalk Server Administration console to change the name of an application.</span></span> <span data-ttu-id="53222-104">您使用的应用程序名称不能已存在的组中。</span><span class="sxs-lookup"><span data-stu-id="53222-104">The application name that you use cannot already exist in the group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53222-105">如果你已导出具有已重命名应用程序的引用的应用程序的.msi 文件，该引用将不再起作用时导入.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="53222-105">If you have exported an .msi file for an application that has a reference to the renamed application, the reference will no longer function when you import the .msi file.</span></span> <span data-ttu-id="53222-106">你将需要使用新的应用程序名称更新该引用。</span><span class="sxs-lookup"><span data-stu-id="53222-106">You will need to update the reference with the new application name.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="53222-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="53222-107">Prerequisites</span></span>  
 <span data-ttu-id="53222-108">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="53222-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="53222-109">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="53222-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-change-the-name-of-an-application"></a><span data-ttu-id="53222-110">若要更改应用程序的名称</span><span class="sxs-lookup"><span data-stu-id="53222-110">To change the name of an application</span></span>  
  
1. <span data-ttu-id="53222-111">单击**启动**，依次指向**程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="53222-111">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="53222-112">在控制台树中，展开**BizTalk Server 管理**，右键单击你想要更改，然后单击其名称的应用程序**属性**。</span><span class="sxs-lookup"><span data-stu-id="53222-112">In the console tree, expand  **BizTalk Server Administration**, right-click the application whose name you want to change, and click **Properties**.</span></span>  
  
3. <span data-ttu-id="53222-113">在中**名称**框中，键入该应用程序的新名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="53222-113">In the **Name** box, type a new name for the application, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53222-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="53222-114">See Also</span></span>  
 [<span data-ttu-id="53222-115">创建和修改 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="53222-115">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)