---
title: "如何从应用程序中删除架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, schemas
- applications, schemas
- schemas, deleting
- managing [schemas], deleting
- managing [schemas], applications
- schemas, applications
ms.assetid: 17dd5869-b56c-4166-9f02-03e04e691eda
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6535764af00156325c006388a88803207329e5fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-a-schema-from-an-application"></a><span data-ttu-id="61ce4-102">如何从应用程序中删除架构</span><span class="sxs-lookup"><span data-stu-id="61ce4-102">How to Remove a Schema from an Application</span></span>
<span data-ttu-id="61ce4-103">本主题介绍如何使用 BizTalk Server 管理控制台从应用程序中删除架构。</span><span class="sxs-lookup"><span data-stu-id="61ce4-103">This topic describes how to use the BizTalk Server Administration console to remove a schema from an application.</span></span> <span data-ttu-id="61ce4-104">此过程也可以从 BizTalk 管理数据库中删除针对组的架构。</span><span class="sxs-lookup"><span data-stu-id="61ce4-104">This procedure removes the schema from the BizTalk Management database for the group as well.</span></span> <span data-ttu-id="61ce4-105">您可能要在部署某一架构的新版本后删除该架构。</span><span class="sxs-lookup"><span data-stu-id="61ce4-105">You might want to remove a schema after deploying a new version of the schema.</span></span> <span data-ttu-id="61ce4-106">有关详细信息和更新应用程序项目的重要注意事项，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="61ce4-106">For more information and important considerations for updating application artifacts, see [Updating BizTalk Applications](../core/updating-biztalk-applications.md).</span></span>  
  
 <span data-ttu-id="61ce4-107">在删除某一架构时，如果在应用程序中存在具有相同根命名空间的该架构的前一版本，则该前一版本将处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="61ce4-107">When you remove a schema, and a previous version of the schema having the same root namespace exists in the application, the previous version will become active.</span></span>  
  
 <span data-ttu-id="61ce4-108">删除某一架构时，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="61ce4-108">When you remove a schema, the following occurs:</span></span>  
  
-   <span data-ttu-id="61ce4-109">该架构将从 BizTalk 管理数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="61ce4-109">The schema is deleted from the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="61ce4-110">将从 BizTalk 管理数据库中删除包含该架构的 BizTalk 程序集；但如果该程序集还存在于本地文件系统或全局程序集缓存 (GAC) 中，则不会将这两个位置中的该程序集删除。</span><span class="sxs-lookup"><span data-stu-id="61ce4-110">The BizTalk assembly that contains the schema is deleted from the BizTalk Management database, but is not removed from the local file system or the global assembly cache (GAC), if it exists in these locations.</span></span>  
  
-   <span data-ttu-id="61ce4-111">一旦删除该 BizTalk 程序集，该程序集中所包含的所有项目也将从 BizTalk 管理数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="61ce4-111">As a consequence of the BizTalk assembly being deleted, all artifacts contained in the assembly are removed deleted the BizTalk Management database as well.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="61ce4-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="61ce4-112">Prerequisites</span></span>  
 <span data-ttu-id="61ce4-113">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="61ce4-113">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="61ce4-114">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="61ce4-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-schema"></a><span data-ttu-id="61ce4-115">若要删除架构</span><span class="sxs-lookup"><span data-stu-id="61ce4-115">To remove a schema</span></span>  
  
1.  <span data-ttu-id="61ce4-116">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="61ce4-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="61ce4-117">在控制台树中，展开**BizTalk Server 管理**，展开包含架构的 BizTalk 组删除和包含架构的应用程序。</span><span class="sxs-lookup"><span data-stu-id="61ce4-117">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the schema to remove and the application containing the schema.</span></span>  
  
3.  <span data-ttu-id="61ce4-118">单击**架构**，右键单击的架构，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="61ce4-118">Click **Schemas**, right-click the schema, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61ce4-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61ce4-119">See Also</span></span>  
 [<span data-ttu-id="61ce4-120">管理架构</span><span class="sxs-lookup"><span data-stu-id="61ce4-120">Managing Schemas</span></span>](../core/managing-schemas.md)