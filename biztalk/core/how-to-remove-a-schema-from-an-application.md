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
ms.openlocfilehash: 1c6af6da4606b8a6138bfbed257ac71b492293b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384347"
---
# <a name="how-to-remove-a-schema-from-an-application"></a><span data-ttu-id="eaaf5-102">如何从应用程序中删除架构</span><span class="sxs-lookup"><span data-stu-id="eaaf5-102">How to Remove a Schema from an Application</span></span>
<span data-ttu-id="eaaf5-103">本主题介绍如何使用 BizTalk Server 管理控制台从应用程序中删除架构。</span><span class="sxs-lookup"><span data-stu-id="eaaf5-103">This topic describes how to use the BizTalk Server Administration console to remove a schema from an application.</span></span> <span data-ttu-id="eaaf5-104">此过程从组以及 BizTalk 管理数据库中删除架构。</span><span class="sxs-lookup"><span data-stu-id="eaaf5-104">This procedure removes the schema from the BizTalk Management database for the group as well.</span></span> <span data-ttu-id="eaaf5-105">您可能想要部署新架构版本后删除架构。</span><span class="sxs-lookup"><span data-stu-id="eaaf5-105">You might want to remove a schema after deploying a new version of the schema.</span></span> <span data-ttu-id="eaaf5-106">有关详细信息和更新应用程序项目的重要注意事项，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="eaaf5-106">For more information and important considerations for updating application artifacts, see [Updating BizTalk Applications](../core/updating-biztalk-applications.md).</span></span>  
  
 <span data-ttu-id="eaaf5-107">当删除某一架构，并在应用程序中存在具有相同根命名空间的架构的旧版本时，以前的版本将处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="eaaf5-107">When you remove a schema, and a previous version of the schema having the same root namespace exists in the application, the previous version will become active.</span></span>  
  
 <span data-ttu-id="eaaf5-108">在删除架构，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="eaaf5-108">When you remove a schema, the following occurs:</span></span>  
  
-   <span data-ttu-id="eaaf5-109">从 BizTalk 管理数据库中删除架构。</span><span class="sxs-lookup"><span data-stu-id="eaaf5-109">The schema is deleted from the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="eaaf5-110">包含架构的 BizTalk 程序集从 BizTalk 管理数据库中删除，但不是会从本地文件系统或全局程序集缓存 (GAC) 中，如果两个位置存在。</span><span class="sxs-lookup"><span data-stu-id="eaaf5-110">The BizTalk assembly that contains the schema is deleted from the BizTalk Management database, but is not removed from the local file system or the global assembly cache (GAC), if it exists in these locations.</span></span>  
  
-   <span data-ttu-id="eaaf5-111">正在删除 BizTalk 程序集，因此删除所有项目程序集中包含删除了该的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="eaaf5-111">As a consequence of the BizTalk assembly being deleted, all artifacts contained in the assembly are removed deleted the BizTalk Management database as well.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eaaf5-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="eaaf5-112">Prerequisites</span></span>  
 <span data-ttu-id="eaaf5-113">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="eaaf5-113">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="eaaf5-114">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="eaaf5-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-schema"></a><span data-ttu-id="eaaf5-115">若要删除某一架构</span><span class="sxs-lookup"><span data-stu-id="eaaf5-115">To remove a schema</span></span>  
  
1. <span data-ttu-id="eaaf5-116">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="eaaf5-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="eaaf5-117">在控制台树中，展开**BizTalk Server 管理**，展开包含该架构的 BizTalk 组删除和包含该架构的应用程序。</span><span class="sxs-lookup"><span data-stu-id="eaaf5-117">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the schema to remove and the application containing the schema.</span></span>  
  
3. <span data-ttu-id="eaaf5-118">单击**架构**，右键单击该架构，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="eaaf5-118">Click **Schemas**, right-click the schema, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaaf5-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="eaaf5-119">See Also</span></span>  
 [<span data-ttu-id="eaaf5-120">管理架构</span><span class="sxs-lookup"><span data-stu-id="eaaf5-120">Managing Schemas</span></span>](../core/managing-schemas.md)