---
title: 单一登录： 事件 10519 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e709957e-a690-4a44-a863-07b2a55dae7b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 928892ff1d0ee461a26095ddc7a72fd3accecf10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271005"
---
# <a name="single-sign-on-event-10519"></a><span data-ttu-id="23e35-102">单一登录： 事件 10519</span><span class="sxs-lookup"><span data-stu-id="23e35-102">Single Sign-On: Event 10519</span></span>
## <a name="details"></a><span data-ttu-id="23e35-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="23e35-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23e35-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="23e35-104">Product Name</span></span>|<span data-ttu-id="23e35-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="23e35-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="23e35-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="23e35-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="23e35-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="23e35-107">Event ID</span></span>|<span data-ttu-id="23e35-108">10519</span><span class="sxs-lookup"><span data-stu-id="23e35-108">10519</span></span>|  
|<span data-ttu-id="23e35-109">事件源</span><span class="sxs-lookup"><span data-stu-id="23e35-109">Event Source</span></span>|<span data-ttu-id="23e35-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="23e35-110">ENTSSO</span></span>|  
|<span data-ttu-id="23e35-111">组件</span><span class="sxs-lookup"><span data-stu-id="23e35-111">Component</span></span>|<span data-ttu-id="23e35-112">N\A</span><span class="sxs-lookup"><span data-stu-id="23e35-112">N\A</span></span>|  
|<span data-ttu-id="23e35-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="23e35-113">Symbolic Name</span></span>|<span data-ttu-id="23e35-114">SSO_WARN_BAD_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="23e35-114">SSO_WARN_BAD_APP_ADMIN_GROUP</span></span>|  
|<span data-ttu-id="23e35-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="23e35-115">Message Text</span></span>|<span data-ttu-id="23e35-116">此应用程序的应用程序管理员帐户无效。</span><span class="sxs-lookup"><span data-stu-id="23e35-116">The Application Administrators account for this application is not valid.</span></span> <span data-ttu-id="23e35-117">如果是本地帐户，请检查服务器上是否存在此帐户。</span><span class="sxs-lookup"><span data-stu-id="23e35-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="23e35-118">如果是域帐户，请与域管理员联系。</span><span class="sxs-lookup"><span data-stu-id="23e35-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="23e35-119">当帐户有效时，启用应用程序。</span><span class="sxs-lookup"><span data-stu-id="23e35-119">Enable the application when the account is valid.</span></span> <span data-ttu-id="23e35-120">如果您不打算在此计算机上使用此应用程序，则可以忽略此消息。</span><span class="sxs-lookup"><span data-stu-id="23e35-120">You can ignore this message if you are not going to use this application on this computer.%r</span></span><br /><br /> <span data-ttu-id="23e35-121">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="23e35-121">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="23e35-122">Application Administrators: %2 %r</span><span class="sxs-lookup"><span data-stu-id="23e35-122">Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="23e35-123">无效帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="23e35-123">Invalid accounts: %3%r</span></span><br /><br /> <span data-ttu-id="23e35-124">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="23e35-124">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="23e35-125">解释</span><span class="sxs-lookup"><span data-stu-id="23e35-125">Explanation</span></span>  
 <span data-ttu-id="23e35-126">此警告事件表示，某个应用程序管理员组帐户是无效的 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="23e35-126">This Warning event indicates that an Application Administrators group account is not a valid Windows account.</span></span> <span data-ttu-id="23e35-127">每个关联应用程序只有一个应用程序管理员帐户组。</span><span class="sxs-lookup"><span data-stu-id="23e35-127">There is one Application Administraotrs account group for each affiliate application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="23e35-128">用户操作</span><span class="sxs-lookup"><span data-stu-id="23e35-128">User Action</span></span>  
 <span data-ttu-id="23e35-129">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="23e35-129">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="23e35-130">验证指定的应用程序管理员帐户是否存在。</span><span class="sxs-lookup"><span data-stu-id="23e35-130">Verify the specified Application Administrators account exists.</span></span>  
  
-   <span data-ttu-id="23e35-131">使用 SSO 管理实用工具验证是否将指定的关联应用程序配置为使用正确的应用程序管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="23e35-131">Use the SSO Administration Utility to verify the specified affiliate application is configured to use the correct application administrators account.</span></span>  
  
 <span data-ttu-id="23e35-132">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="23e35-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="23e35-133">SSO 用户组</span><span class="sxs-lookup"><span data-stu-id="23e35-133">SSO User Groups</span></span>](../core/sso-user-groups.md)  
  
-   [<span data-ttu-id="23e35-134">SSO 关联应用程序</span><span class="sxs-lookup"><span data-stu-id="23e35-134">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)  
  
-   [<span data-ttu-id="23e35-135">如何更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="23e35-135">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)