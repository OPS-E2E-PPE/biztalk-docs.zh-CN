---
title: 配置 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19825ec6f420b8ec3e30f5dead09ad1d901503f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355194"
---
# <a name="configuring-sso"></a><span data-ttu-id="6bf71-102">配置 SSO</span><span class="sxs-lookup"><span data-stu-id="6bf71-102">Configuring SSO</span></span>
<span data-ttu-id="6bf71-103">使用命令行实用程序、 用户界面工具，或者 COM 或 Microsoft.NET 接口可以配置企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="6bf71-103">You can configure Enterprise Single Sign-On by using command line utilities, UI tools, or COM or Microsoft .NET interfaces.</span></span>  
  
## <a name="sso-command-line-utilities"></a><span data-ttu-id="6bf71-104">SSO 命令行实用程序</span><span class="sxs-lookup"><span data-stu-id="6bf71-104">SSO command line utilities</span></span>  
 <span data-ttu-id="6bf71-105">使用三个不同的命令行实用程序来执行企业单一登录任务：</span><span class="sxs-lookup"><span data-stu-id="6bf71-105">You use three different command line utilities to perform Enterprise Single Sign-On tasks:</span></span>  
  
 <span data-ttu-id="6bf71-106">**SSOConfig。**</span><span class="sxs-lookup"><span data-stu-id="6bf71-106">**SSOConfig.**</span></span> <span data-ttu-id="6bf71-107">若要配置 SSO 数据库以及管理主密钥 SSO 管理员可使用。</span><span class="sxs-lookup"><span data-stu-id="6bf71-107">Enables an SSO administrator to configure the SSO database and to manage the master secret.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6bf71-108">配置向导创建 SSO 数据库和主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="6bf71-108">The Configuration Wizard creates the SSO database and the master secret server.</span></span>  
  
 <span data-ttu-id="6bf71-109">**SSOManage。**</span><span class="sxs-lookup"><span data-stu-id="6bf71-109">**SSOManage.**</span></span> <span data-ttu-id="6bf71-110">启用 SSO 管理员、 SSO 关联管理员和应用程序管理员，若要更新 SSO 数据库，添加、 删除和管理应用程序、 管理用户映射，并为关联应用程序用户设置凭据。</span><span class="sxs-lookup"><span data-stu-id="6bf71-110">Enables SSO administrators, SSO affiliate administrators, and application administrators to update the SSO database to add, delete and manage applications, administer user mappings, and to set credentials for the affiliate application users.</span></span> <span data-ttu-id="6bf71-111">只能由 SSO 管理员，可以执行一些操作，或只能由 SSO 管理员和 SSO 关联管理员。</span><span class="sxs-lookup"><span data-stu-id="6bf71-111">Some operations can be performed only by the SSO administrators, or, only by the SSO administrators and SSO affiliate administrators.</span></span> <span data-ttu-id="6bf71-112">此外可以通过 SSO Administrators 和 SSO Affiliate Administrators 执行应用程序管理员可以执行的所有操作。</span><span class="sxs-lookup"><span data-stu-id="6bf71-112">All operations that can be performed by the Application Administrators can also be performed by the SSO Administrators and the SSO Affiliate Administrators.</span></span>  
  
 <span data-ttu-id="6bf71-113">**SSOClient。**</span><span class="sxs-lookup"><span data-stu-id="6bf71-113">**SSOClient.**</span></span> <span data-ttu-id="6bf71-114">启用单一登录的用户来管理其自己的用户映射以及设置自己的凭据。</span><span class="sxs-lookup"><span data-stu-id="6bf71-114">Enables Single Sign-On users to manage their own user mappings and set their credentials.</span></span>  
  
 <span data-ttu-id="6bf71-115">有关 SSO 帐户的详细信息，请参阅[SSO 用户组](../core/sso-user-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="6bf71-115">For more information about the SSO accounts, see [SSO User Groups](../core/sso-user-groups.md).</span></span>  
  
## <a name="sso-ui-tools"></a><span data-ttu-id="6bf71-116">SSO 用户界面工具</span><span class="sxs-lookup"><span data-stu-id="6bf71-116">SSO UI tools</span></span>  
 <span data-ttu-id="6bf71-117">**企业 SSO mmc 管理单元。**</span><span class="sxs-lookup"><span data-stu-id="6bf71-117">**Enterprise SSO MMC Snap-in.**</span></span> <span data-ttu-id="6bf71-118">启用 SSO 管理员、 SSO 关联管理员和应用程序管理员，若要更新 SSO 数据库、 添加、 删除和管理应用程序、 管理用户映射，以及为关联应用程序用户设置凭据。</span><span class="sxs-lookup"><span data-stu-id="6bf71-118">Enables SSO Administrators, SSO Affiliate Administrators, and Application Administrators to update the SSO database, to add, delete and manage applications, administer user mappings, and to set credentials for the affiliate application users.</span></span> <span data-ttu-id="6bf71-119">只能由 SSO 管理员，可以执行一些操作，或只能由 SSO 管理员和 SSO 关联管理员。</span><span class="sxs-lookup"><span data-stu-id="6bf71-119">Some operations can be performed only by the SSO administrators, or only by the SSO administrators and SSO affiliate administrators.</span></span> <span data-ttu-id="6bf71-120">此外可以通过 SSO Administrators 和 SSO Affiliate Administrators 执行应用程序管理员可以执行的所有操作。</span><span class="sxs-lookup"><span data-stu-id="6bf71-120">All operations that can be performed by the Application Administrators can also be performed by the SSO Administrators and SSO Affiliate Administrators.</span></span>  
  
 <span data-ttu-id="6bf71-121">**SSO 客户端实用工具。**</span><span class="sxs-lookup"><span data-stu-id="6bf71-121">**SSO Client Utility.**</span></span> <span data-ttu-id="6bf71-122">使最终用户能够管理自己映射以及设置自己的凭据使用 UI 工具。</span><span class="sxs-lookup"><span data-stu-id="6bf71-122">Enables end users to manage their own mappings and set their credentials using the UI tool.</span></span>  
  
## <a name="sso-com-and-net-interfaces"></a><span data-ttu-id="6bf71-123">SSO COM 和.NET 接口</span><span class="sxs-lookup"><span data-stu-id="6bf71-123">SSO COM and .NET interfaces</span></span>  
 <span data-ttu-id="6bf71-124">企业单一登录提供 COM 和.NET 编程接口，使您能够创建自定义组件，以及创建脚本以促进 SSO 系统的管理。</span><span class="sxs-lookup"><span data-stu-id="6bf71-124">Enterprise Single Sign-On provides COM and .NET programmatic interfaces that enable you to create custom components, and to create scripts to facilitate the administration of the SSO system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bf71-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bf71-125">See Also</span></span>  
 [<span data-ttu-id="6bf71-126">SSO 组件</span><span class="sxs-lookup"><span data-stu-id="6bf71-126">SSO Components</span></span>](../core/sso-components.md)