---
title: "单一登录： 事件 10516 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d20df92f-c995-4cbc-a8f9-21cea30b82c9
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0b74ca4a47bc62d28b25564bd5843729c56362
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10516"></a><span data-ttu-id="becd7-102">单一登录： 事件 10516</span><span class="sxs-lookup"><span data-stu-id="becd7-102">Single Sign-On: Event 10516</span></span>
## <a name="details"></a><span data-ttu-id="becd7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="becd7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="becd7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="becd7-104">Product Name</span></span>|<span data-ttu-id="becd7-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="becd7-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="becd7-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="becd7-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="becd7-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="becd7-107">Event ID</span></span>|<span data-ttu-id="becd7-108">10516</span><span class="sxs-lookup"><span data-stu-id="becd7-108">10516</span></span>|  
|<span data-ttu-id="becd7-109">事件源</span><span class="sxs-lookup"><span data-stu-id="becd7-109">Event Source</span></span>|<span data-ttu-id="becd7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="becd7-110">ENTSSO</span></span>|  
|<span data-ttu-id="becd7-111">组件</span><span class="sxs-lookup"><span data-stu-id="becd7-111">Component</span></span>|<span data-ttu-id="becd7-112">N\A</span><span class="sxs-lookup"><span data-stu-id="becd7-112">N\A</span></span>|  
|<span data-ttu-id="becd7-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="becd7-113">Symbolic Name</span></span>|<span data-ttu-id="becd7-114">SSO_ERROR_BAD_SSO_APP_ADMIN</span><span class="sxs-lookup"><span data-stu-id="becd7-114">SSO_ERROR_BAD_SSO_APP_ADMIN</span></span>|  
|<span data-ttu-id="becd7-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="becd7-115">Message Text</span></span>|<span data-ttu-id="becd7-116">SSO 关联管理员帐户无效。</span><span class="sxs-lookup"><span data-stu-id="becd7-116">The SSO Affiliate Administrators account is not valid.</span></span> <span data-ttu-id="becd7-117">如果是本地帐户，请检查服务器上是否存在此帐户。</span><span class="sxs-lookup"><span data-stu-id="becd7-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="becd7-118">如果是域帐户，请与域管理员联系。</span><span class="sxs-lookup"><span data-stu-id="becd7-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="becd7-119">当帐户有效时，启用 SSO。%r</span><span class="sxs-lookup"><span data-stu-id="becd7-119">Enable SSO when the account is valid.%r</span></span><br /><br /> <span data-ttu-id="becd7-120">SSO 关联管理员: %1 %r</span><span class="sxs-lookup"><span data-stu-id="becd7-120">SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="becd7-121">无效帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="becd7-121">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="becd7-122">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="becd7-122">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="becd7-123">解释</span><span class="sxs-lookup"><span data-stu-id="becd7-123">Explanation</span></span>  
 <span data-ttu-id="becd7-124">此错误事件表示，企业单一登录创建的 SSO 关联管理员帐户或组不是有效的 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="becd7-124">This Error event indicates that the SSO Affiliate Administrator account or group created by Enterprise Sing Sign-on is not a valid Windows account.</span></span> <span data-ttu-id="becd7-125">SSO 关联管理员帐户可以是 Windows 组帐户或个人帐户。</span><span class="sxs-lookup"><span data-stu-id="becd7-125">The SSO Affiliate Administrators account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="becd7-126">SSO 关联管理员帐户也可以是域或本地组帐户。</span><span class="sxs-lookup"><span data-stu-id="becd7-126">The SSO Affiliate Administrator account can also be either a domain or local group account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="becd7-127">用户操作</span><span class="sxs-lookup"><span data-stu-id="becd7-127">User Action</span></span>  
 <span data-ttu-id="becd7-128">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="becd7-128">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="becd7-129">验证 SSO 关联管理员帐户是否存在。</span><span class="sxs-lookup"><span data-stu-id="becd7-129">Verify the SSO Affiliate Administrator account exists.</span></span>  
  
 <span data-ttu-id="becd7-130">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="becd7-130">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="becd7-131">SSO 用户组</span><span class="sxs-lookup"><span data-stu-id="becd7-131">SSO User Groups</span></span>](../core/sso-user-groups.md)  
  
-   [<span data-ttu-id="becd7-132">如何更新 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="becd7-132">How to Update the SSO Database</span></span>](../core/how-to-update-the-sso-database.md)