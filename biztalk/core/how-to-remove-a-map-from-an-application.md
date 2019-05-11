---
title: 如何从应用程序中删除映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, maps
- deleting, maps
- managing [maps], deleting
- managing [maps], applications
ms.assetid: 27d9bb08-36f0-46ff-ae9a-2247be6e3f96
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07bfff864b35869c15922d0a907aa7bb30bc6912
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384405"
---
# <a name="how-to-remove-a-map-from-an-application"></a><span data-ttu-id="870a8-102">如何从应用程序中删除映射</span><span class="sxs-lookup"><span data-stu-id="870a8-102">How to Remove a Map from an Application</span></span>
<span data-ttu-id="870a8-103">本主题介绍如何使用 BizTalk Server 管理控制台从 BizTalk 应用程序中删除映射。</span><span class="sxs-lookup"><span data-stu-id="870a8-103">This topic describes how to use the BizTalk Server Administration console to remove a map from a BizTalk application.</span></span> <span data-ttu-id="870a8-104">您可能想要部署的映射的新版本后删除映射。</span><span class="sxs-lookup"><span data-stu-id="870a8-104">You might want to remove a map after deploying a new version of the map.</span></span> <span data-ttu-id="870a8-105">有关详细信息和更新应用程序项目的重要注意事项，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="870a8-105">For more information and important considerations for updating application artifacts, see [Updating BizTalk Applications](../core/updating-biztalk-applications.md).</span></span>  
  
 <span data-ttu-id="870a8-106">在删除映射中，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="870a8-106">When you remove a map, the following occurs:</span></span>  
  
-   <span data-ttu-id="870a8-107">从 BizTalk 管理数据库中删除该映射。</span><span class="sxs-lookup"><span data-stu-id="870a8-107">The map is deleted from the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="870a8-108">包含该映射的 BizTalk 程序集从 BizTalk 管理数据库中删除，但不是会从本地文件系统或全局程序集缓存 (GAC) 中，如果两个位置存在。</span><span class="sxs-lookup"><span data-stu-id="870a8-108">The BizTalk assembly that contains the map is deleted from the BizTalk Management database, but is not removed from the local file system or the global assembly cache (GAC), if it exists in these locations.</span></span>  
  
-   <span data-ttu-id="870a8-109">正在删除 BizTalk 程序集，因此删除所有项目程序集中包含删除了该的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="870a8-109">As a consequence of the BizTalk assembly being deleted, all artifacts contained in the assembly are removed deleted the BizTalk Management database as well.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="870a8-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="870a8-110">Prerequisites</span></span>  
 <span data-ttu-id="870a8-111">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="870a8-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="870a8-112">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="870a8-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-map"></a><span data-ttu-id="870a8-113">若要删除映射</span><span class="sxs-lookup"><span data-stu-id="870a8-113">To remove a map</span></span>  
  
1. <span data-ttu-id="870a8-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="870a8-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="870a8-115">在控制台树中，展开**BizTalk Server 管理**，展开包含该映射的 BizTalk 组删除，，然后展开包含该映射的应用程序。</span><span class="sxs-lookup"><span data-stu-id="870a8-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the map to remove, and then expand the application containing the map.</span></span>  
  
3. <span data-ttu-id="870a8-116">单击**Maps**文件夹，右键单击该映射，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="870a8-116">Click the **Maps** folder, right-click the map, and then click **Remove**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="870a8-117">若要删除多个映射，请按住 shift 键，单击每个映射以删除，右键单击其中一个映射，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="870a8-117">To remove multiple maps, hold down the shift key, click each map to remove, right-click one of the maps, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="870a8-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="870a8-118">See Also</span></span>  
 <span data-ttu-id="870a8-119">[管理映射](../core/managing-maps.md) </span><span class="sxs-lookup"><span data-stu-id="870a8-119">[Managing Maps](../core/managing-maps.md) </span></span>  
 <span data-ttu-id="870a8-120">[如何从应用程序删除 BizTalk 程序集](../core/how-to-remove-a-biztalk-assembly-from-an-application.md) </span><span class="sxs-lookup"><span data-stu-id="870a8-120">[How to Remove a BizTalk Assembly from an Application](../core/how-to-remove-a-biztalk-assembly-from-an-application.md) </span></span>  
 [<span data-ttu-id="870a8-121">取消部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="870a8-121">Undeploying BizTalk Applications</span></span>](../core/undeploying-biztalk-applications.md)