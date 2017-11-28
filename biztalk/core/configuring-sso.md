---
title: "配置 SSO |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, command line utilities
- configuring, SSO
- SSO, interfaces
- SSOConfig [SSO]
- SSO, configuring
- SSOClient [SSO]
- SSO, tools
- SSOManage [SSO]
ms.assetid: 6f755735-9b48-4771-beec-ced844f3d532
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d729633717d709a83c10e9b50c55791029902010
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-sso"></a><span data-ttu-id="6f171-102">配置 SSO</span><span class="sxs-lookup"><span data-stu-id="6f171-102">Configuring SSO</span></span>
<span data-ttu-id="6f171-103">可以通过使用命令行实用工具、用户界面工具或者 COM 或 Microsoft .NET 接口来配置企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="6f171-103">You can configure Enterprise Single Sign-On by using command line utilities, UI tools, or COM or Microsoft .NET interfaces.</span></span>  
  
## <a name="sso-command-line-utilities"></a><span data-ttu-id="6f171-104">SSO 命令行实用工具</span><span class="sxs-lookup"><span data-stu-id="6f171-104">SSO command line utilities</span></span>  
 <span data-ttu-id="6f171-105">您可以使用三种不同的命令行实用工具来执行企业单一登录任务：</span><span class="sxs-lookup"><span data-stu-id="6f171-105">You use three different command line utilities to perform Enterprise Single Sign-On tasks:</span></span>  
  
 <span data-ttu-id="6f171-106">**SSOConfig。**</span><span class="sxs-lookup"><span data-stu-id="6f171-106">**SSOConfig.**</span></span> <span data-ttu-id="6f171-107">SSO 管理员可使用该工具来配置 SSO 数据库和管理主密钥。</span><span class="sxs-lookup"><span data-stu-id="6f171-107">Enables an SSO administrator to configure the SSO database and to manage the master secret.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f171-108">配置向导创建 SSO 数据库和主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="6f171-108">The Configuration Wizard creates the SSO database and the master secret server.</span></span>  
  
 <span data-ttu-id="6f171-109">**SSOManage。**</span><span class="sxs-lookup"><span data-stu-id="6f171-109">**SSOManage.**</span></span> <span data-ttu-id="6f171-110">SSO 管理员、SSO 关联管理员和应用程序管理员可使用该工具来更新 SSO 数据库，以添加、删除和管理应用程序，管理用户映射，以及为关联应用程序用户设置凭据。</span><span class="sxs-lookup"><span data-stu-id="6f171-110">Enables SSO administrators, SSO affiliate administrators, and application administrators to update the SSO database to add, delete and manage applications, administer user mappings, and to set credentials for the affiliate application users.</span></span> <span data-ttu-id="6f171-111">某些操作只能由 SSO 管理员来执行；或者只能由 SSO 管理员和 SSO 关联管理员来执行。</span><span class="sxs-lookup"><span data-stu-id="6f171-111">Some operations can be performed only by the SSO administrators, or, only by the SSO administrators and SSO affiliate administrators.</span></span> <span data-ttu-id="6f171-112">可由应用程序管理员执行的所有操作都可由 SSO 管理员和 SSO 关联管理员来执行。</span><span class="sxs-lookup"><span data-stu-id="6f171-112">All operations that can be performed by the Application Administrators can also be performed by the SSO Administrators and the SSO Affiliate Administrators.</span></span>  
  
 <span data-ttu-id="6f171-113">**SSOClient。**</span><span class="sxs-lookup"><span data-stu-id="6f171-113">**SSOClient.**</span></span> <span data-ttu-id="6f171-114">单一登录用户可以使用该工具来管理自己的用户映射以及设置自己的凭据。</span><span class="sxs-lookup"><span data-stu-id="6f171-114">Enables Single Sign-On users to manage their own user mappings and set their credentials.</span></span>  
  
 <span data-ttu-id="6f171-115">有关 SSO 帐户的详细信息，请参阅[SSO 用户组](../core/sso-user-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="6f171-115">For more information about the SSO accounts, see [SSO User Groups](../core/sso-user-groups.md).</span></span>  
  
## <a name="sso-ui-tools"></a><span data-ttu-id="6f171-116">SSO 用户界面工具</span><span class="sxs-lookup"><span data-stu-id="6f171-116">SSO UI tools</span></span>  
 <span data-ttu-id="6f171-117">**企业 SSO mmc 管理单元。**</span><span class="sxs-lookup"><span data-stu-id="6f171-117">**Enterprise SSO MMC Snap-in.**</span></span> <span data-ttu-id="6f171-118">SSO 管理员、SSO 关联管理员和应用程序管理员可使用该工具来更新 SSO 数据库，添加、删除和管理应用程序，管理用户映射，以及为关联应用程序用户设置凭据。</span><span class="sxs-lookup"><span data-stu-id="6f171-118">Enables SSO Administrators, SSO Affiliate Administrators, and Application Administrators to update the SSO database, to add, delete and manage applications, administer user mappings, and to set credentials for the affiliate application users.</span></span> <span data-ttu-id="6f171-119">只能由 SSO administrators，可以执行某些操作，或仅通过 SSO 管理员和 SSO affiliate 管理员。</span><span class="sxs-lookup"><span data-stu-id="6f171-119">Some operations can be performed only by the SSO administrators, or only by the SSO administrators and SSO affiliate administrators.</span></span> <span data-ttu-id="6f171-120">可以执行的应用程序管理员的所有操作还可以都执行的 SSO Administrators 和 SSO Affiliate Administrators。</span><span class="sxs-lookup"><span data-stu-id="6f171-120">All operations that can be performed by the Application Administrators can also be performed by the SSO Administrators and SSO Affiliate Administrators.</span></span>  
  
 <span data-ttu-id="6f171-121">**SSO 客户端实用工具。**</span><span class="sxs-lookup"><span data-stu-id="6f171-121">**SSO Client Utility.**</span></span> <span data-ttu-id="6f171-122">最终用户可使用该用户界面工具来管理自己映射以及设置自己的凭据。</span><span class="sxs-lookup"><span data-stu-id="6f171-122">Enables end users to manage their own mappings and set their credentials using the UI tool.</span></span>  
  
## <a name="sso-com-and-net-interfaces"></a><span data-ttu-id="6f171-123">SSO COM 和 .NET 接口</span><span class="sxs-lookup"><span data-stu-id="6f171-123">SSO COM and .NET interfaces</span></span>  
 <span data-ttu-id="6f171-124">企业单一登录提供有 COM 和 .NET 编程接口，使您能够创建自定义组件和创建脚本以便对 SSO 系统进行管理。</span><span class="sxs-lookup"><span data-stu-id="6f171-124">Enterprise Single Sign-On provides COM and .NET programmatic interfaces that enable you to create custom components, and to create scripts to facilitate the administration of the SSO system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f171-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f171-125">See Also</span></span>  
 [<span data-ttu-id="6f171-126">SSO 组件</span><span class="sxs-lookup"><span data-stu-id="6f171-126">SSO Components</span></span>](../core/sso-components.md)