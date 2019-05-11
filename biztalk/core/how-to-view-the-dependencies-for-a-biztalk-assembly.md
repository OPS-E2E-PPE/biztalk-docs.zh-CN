---
title: 如何查看 BizTalk 程序集的依赖关系 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- viewing, dependencies
- assemblies, dependencies
- managing [assemblies], dependencies
- assemblies, viewing
- viewing, assemblies
- managing [assemblies], viewing
ms.assetid: 872abc99-8248-4397-9fcb-24a0ba6f4757
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 592d85210fc08835229cea3990c150680aed56bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383126"
---
# <a name="how-to-view-the-dependencies-for-a-biztalk-assembly"></a><span data-ttu-id="44190-102">如何查看 BizTalk 程序集的依赖关系</span><span class="sxs-lookup"><span data-stu-id="44190-102">How to View the Dependencies for a BizTalk Assembly</span></span>
<span data-ttu-id="44190-103">本主题介绍如何使用 BizTalk Server 管理控制台查看 BizTalk 程序集上具有依赖项的项目的列表。</span><span class="sxs-lookup"><span data-stu-id="44190-103">This topic describes how to use the BizTalk Server Administration console to view the list of artifacts that have dependencies on a BizTalk assembly.</span></span> <span data-ttu-id="44190-104">有关依赖关系以及它们如何影响应用程序部署的背景信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="44190-104">For background information about dependencies and how they affect application deployment, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="44190-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="44190-105">Prerequisites</span></span>  
 <span data-ttu-id="44190-106">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组或 BizTalk Operators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="44190-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group or BizTalk Operators group.</span></span> <span data-ttu-id="44190-107">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="44190-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-the-dependencies-of-a-biztalk-assembly"></a><span data-ttu-id="44190-108">若要查看 BizTalk 程序集的依赖关系</span><span class="sxs-lookup"><span data-stu-id="44190-108">To view the dependencies of a BizTalk assembly</span></span>  
  
1. <span data-ttu-id="44190-109">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="44190-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="44190-110">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开包含你想要查看依存关系的 BizTalk 程序集的 BizTalk 组，然后展开包含该 BizTalk 程序集的应用程序。</span><span class="sxs-lookup"><span data-stu-id="44190-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the BizTalk assembly for which you want to view dependencies, and then expand the application containing the BizTalk assembly.</span></span>  
  
3. <span data-ttu-id="44190-111">单击**资源**文件夹中，右键单击 BizTalk 程序集，然后依次**修改**。</span><span class="sxs-lookup"><span data-stu-id="44190-111">Click the **Resources** folder, right-click the BizTalk assembly, and then click **Modify**.</span></span>  
  
4. <span data-ttu-id="44190-112">单击**依赖项**选项卡。</span><span class="sxs-lookup"><span data-stu-id="44190-112">Click the **Dependencies** tab.</span></span>  
  
    <span data-ttu-id="44190-113">在列表中显示的名称和此 BizTalk 程序集具有依赖项的项目的状态。</span><span class="sxs-lookup"><span data-stu-id="44190-113">The name and status of the artifacts that have dependencies on this BizTalk assembly are displayed in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44190-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="44190-114">See Also</span></span>  
 [<span data-ttu-id="44190-115">管理 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="44190-115">Managing BizTalk Assemblies</span></span>](../core/managing-biztalk-assemblies.md)