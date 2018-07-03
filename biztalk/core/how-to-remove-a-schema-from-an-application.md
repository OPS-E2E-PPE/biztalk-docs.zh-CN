---
title: 如何从应用程序中删除架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, schemas
- applications, schemas
- schemas, deleting
- managing [schemas], deleting
- managing [schemas], applications
- schemas, applications
ms.assetid: 17dd5869-b56c-4166-9f02-03e04e691eda
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0693d94736c4ef3d8ad5ee561ed6b42650c90ab3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985430"
---
# <a name="how-to-remove-a-schema-from-an-application"></a><span data-ttu-id="8a261-102">如何从应用程序中删除架构</span><span class="sxs-lookup"><span data-stu-id="8a261-102">How to Remove a Schema from an Application</span></span>
<span data-ttu-id="8a261-103">本主题介绍如何使用 BizTalk Server 管理控制台从应用程序中删除架构。</span><span class="sxs-lookup"><span data-stu-id="8a261-103">This topic describes how to use the BizTalk Server Administration console to remove a schema from an application.</span></span> <span data-ttu-id="8a261-104">此过程也可以从 BizTalk 管理数据库中删除针对组的架构。</span><span class="sxs-lookup"><span data-stu-id="8a261-104">This procedure removes the schema from the BizTalk Management database for the group as well.</span></span> <span data-ttu-id="8a261-105">您可能要在部署某一架构的新版本后删除该架构。</span><span class="sxs-lookup"><span data-stu-id="8a261-105">You might want to remove a schema after deploying a new version of the schema.</span></span> <span data-ttu-id="8a261-106">有关详细信息和更新应用程序项目的重要注意事项，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="8a261-106">For more information and important considerations for updating application artifacts, see [Updating BizTalk Applications](../core/updating-biztalk-applications.md).</span></span>  
  
 <span data-ttu-id="8a261-107">在删除某一架构时，如果在应用程序中存在具有相同根命名空间的该架构的前一版本，则该前一版本将处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="8a261-107">When you remove a schema, and a previous version of the schema having the same root namespace exists in the application, the previous version will become active.</span></span>  
  
 <span data-ttu-id="8a261-108">删除某一架构时，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="8a261-108">When you remove a schema, the following occurs:</span></span>  
  
-   <span data-ttu-id="8a261-109">该架构将从 BizTalk 管理数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="8a261-109">The schema is deleted from the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="8a261-110">将从 BizTalk 管理数据库中删除包含该架构的 BizTalk 程序集；但如果该程序集还存在于本地文件系统或全局程序集缓存 (GAC) 中，则不会将这两个位置中的该程序集删除。</span><span class="sxs-lookup"><span data-stu-id="8a261-110">The BizTalk assembly that contains the schema is deleted from the BizTalk Management database, but is not removed from the local file system or the global assembly cache (GAC), if it exists in these locations.</span></span>  
  
-   <span data-ttu-id="8a261-111">一旦删除该 BizTalk 程序集，该程序集中所包含的所有项目也将从 BizTalk 管理数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="8a261-111">As a consequence of the BizTalk assembly being deleted, all artifacts contained in the assembly are removed deleted the BizTalk Management database as well.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8a261-112">必要條件</span><span class="sxs-lookup"><span data-stu-id="8a261-112">Prerequisites</span></span>  
 <span data-ttu-id="8a261-113">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="8a261-113">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="8a261-114">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="8a261-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-schema"></a><span data-ttu-id="8a261-115">若要删除某一架构</span><span class="sxs-lookup"><span data-stu-id="8a261-115">To remove a schema</span></span>  
  
1. <span data-ttu-id="8a261-116">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="8a261-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="8a261-117">在控制台树中，展开**BizTalk Server 管理**，展开包含该架构的 BizTalk 组删除和包含该架构的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8a261-117">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the schema to remove and the application containing the schema.</span></span>  
  
3. <span data-ttu-id="8a261-118">单击**架构**，右键单击该架构，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="8a261-118">Click **Schemas**, right-click the schema, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a261-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a261-119">See Also</span></span>  
 [<span data-ttu-id="8a261-120">管理架构</span><span class="sxs-lookup"><span data-stu-id="8a261-120">Managing Schemas</span></span>](../core/managing-schemas.md)