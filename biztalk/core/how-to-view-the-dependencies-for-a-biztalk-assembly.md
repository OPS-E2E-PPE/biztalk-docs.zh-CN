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
ms.openlocfilehash: b02a773ff51c35de2505336137dfa6c4c11c0825
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001214"
---
# <a name="how-to-view-the-dependencies-for-a-biztalk-assembly"></a><span data-ttu-id="c213b-102">如何查看 BizTalk 程序集的依赖关系</span><span class="sxs-lookup"><span data-stu-id="c213b-102">How to View the Dependencies for a BizTalk Assembly</span></span>
<span data-ttu-id="c213b-103">本主题介绍如何使用 BizTalk Server 管理控制台来查看与 BizTalk 程序集有依存关系的项目的列表。</span><span class="sxs-lookup"><span data-stu-id="c213b-103">This topic describes how to use the BizTalk Server Administration console to view the list of artifacts that have dependencies on a BizTalk assembly.</span></span> <span data-ttu-id="c213b-104">有关依赖关系以及它们如何影响应用程序部署的背景信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="c213b-104">For background information about dependencies and how they affect application deployment, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c213b-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="c213b-105">Prerequisites</span></span>  
 <span data-ttu-id="c213b-106">若要执行本主题中的过程，必须以 BizTalk Server Administrators 组或 BizTalk  Operators 组成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="c213b-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group or BizTalk Operators group.</span></span> <span data-ttu-id="c213b-107">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c213b-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-the-dependencies-of-a-biztalk-assembly"></a><span data-ttu-id="c213b-108">查看 BizTalk 程序集的依存关系</span><span class="sxs-lookup"><span data-stu-id="c213b-108">To view the dependencies of a BizTalk assembly</span></span>  
  
1. <span data-ttu-id="c213b-109">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="c213b-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="c213b-110">在控制台树中，依次展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、包含要查看依存关系的 BizTalk 程序集的 BizTalk 组和包含该 BizTalk 程序集的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c213b-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the BizTalk assembly for which you want to view dependencies, and then expand the application containing the BizTalk assembly.</span></span>  
  
3. <span data-ttu-id="c213b-111">单击**资源**文件夹中，右键单击 BizTalk 程序集，然后依次**修改**。</span><span class="sxs-lookup"><span data-stu-id="c213b-111">Click the **Resources** folder, right-click the BizTalk assembly, and then click **Modify**.</span></span>  
  
4. <span data-ttu-id="c213b-112">单击**依赖项**选项卡。</span><span class="sxs-lookup"><span data-stu-id="c213b-112">Click the **Dependencies** tab.</span></span>  
  
    <span data-ttu-id="c213b-113">与此 BizTalk 程序集有依存关系的项目的名称和状态将显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="c213b-113">The name and status of the artifacts that have dependencies on this BizTalk assembly are displayed in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c213b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c213b-114">See Also</span></span>  
 [<span data-ttu-id="c213b-115">管理 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="c213b-115">Managing BizTalk Assemblies</span></span>](../core/managing-biztalk-assemblies.md)