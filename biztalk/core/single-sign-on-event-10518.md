---
title: 单一登录：Event 10518 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 274e29f9-1933-4e40-83c0-2e84c6708315
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e675204d73731502080f8ae168e5ca8458d50a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279758"
---
# <a name="single-sign-on-event-10518"></a><span data-ttu-id="fd0a1-102">单一登录：事件 10518</span><span class="sxs-lookup"><span data-stu-id="fd0a1-102">Single Sign-On: Event 10518</span></span>
## <a name="details"></a><span data-ttu-id="fd0a1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="fd0a1-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fd0a1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="fd0a1-104">Product Name</span></span>   |                                                                                                                                                                                                                                <span data-ttu-id="fd0a1-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="fd0a1-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="fd0a1-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="fd0a1-106">Product Version</span></span> |                                                                                                                                                                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                                                                |
|    <span data-ttu-id="fd0a1-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fd0a1-107">Event ID</span></span>     |                                                                                                                                                                                                                                          <span data-ttu-id="fd0a1-108">10518</span><span class="sxs-lookup"><span data-stu-id="fd0a1-108">10518</span></span>                                                                                                                                                                                                                                           |
|  <span data-ttu-id="fd0a1-109">事件源</span><span class="sxs-lookup"><span data-stu-id="fd0a1-109">Event Source</span></span>   |                                                                                                                                                                                                                                          <span data-ttu-id="fd0a1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fd0a1-110">ENTSSO</span></span>                                                                                                                                                                                                                                          |
|    <span data-ttu-id="fd0a1-111">组件</span><span class="sxs-lookup"><span data-stu-id="fd0a1-111">Component</span></span>    |                                                                                                                                                                                                                                           <span data-ttu-id="fd0a1-112">N\A</span><span class="sxs-lookup"><span data-stu-id="fd0a1-112">N\A</span></span>                                                                                                                                                                                                                                            |
|  <span data-ttu-id="fd0a1-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="fd0a1-113">Symbolic Name</span></span>  |                                                                                                                                                                                                                                 <span data-ttu-id="fd0a1-114">SSO_WARN_BAD_USER_GROUP</span><span class="sxs-lookup"><span data-stu-id="fd0a1-114">SSO_WARN_BAD_USER_GROUP</span></span>                                                                                                                                                                                                                                  |
|  <span data-ttu-id="fd0a1-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="fd0a1-115">Message Text</span></span>   | <span data-ttu-id="fd0a1-116">此应用程序的应用程序用户帐户不是有效的。</span><span class="sxs-lookup"><span data-stu-id="fd0a1-116">The Application Users account for this application is not valid.</span></span> <span data-ttu-id="fd0a1-117">如果它是本地帐户检查服务器上是否存在此帐户。</span><span class="sxs-lookup"><span data-stu-id="fd0a1-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="fd0a1-118">如果是域帐户与域管理员联系。</span><span class="sxs-lookup"><span data-stu-id="fd0a1-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="fd0a1-119">当帐户有效时，请启用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="fd0a1-119">Enable the application when the account is valid.</span></span> <span data-ttu-id="fd0a1-120">如果您不打算在此 computer.%r 上使用此应用程序，则可以忽略此消息</span><span class="sxs-lookup"><span data-stu-id="fd0a1-120">You can ignore this message if you are not going to use this application on this computer.%r</span></span><br /><br /> <span data-ttu-id="fd0a1-121">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="fd0a1-121">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="fd0a1-122">应用程序用户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="fd0a1-122">Application Users: %2%r</span></span><br /><br /> <span data-ttu-id="fd0a1-123">无效帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="fd0a1-123">Invalid accounts: %3%r</span></span><br /><br /> <span data-ttu-id="fd0a1-124">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="fd0a1-124">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="fd0a1-125">解释</span><span class="sxs-lookup"><span data-stu-id="fd0a1-125">Explanation</span></span>  
 <span data-ttu-id="fd0a1-126">此警告事件表示应用程序用户组帐户不是有效的 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="fd0a1-126">This Warning event indicates that an Application Users group account is not a valid Windows account.</span></span> <span data-ttu-id="fd0a1-127">没有为每个关联应用程序的一个应用程序用户帐户组。</span><span class="sxs-lookup"><span data-stu-id="fd0a1-127">There is one Application Users account group for each affiliate application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="fd0a1-128">用户操作</span><span class="sxs-lookup"><span data-stu-id="fd0a1-128">User Action</span></span>  
 <span data-ttu-id="fd0a1-129">若要解决此警告，请执行一个或多个以下操作：</span><span class="sxs-lookup"><span data-stu-id="fd0a1-129">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="fd0a1-130">验证指定的应用程序用户帐户存在。</span><span class="sxs-lookup"><span data-stu-id="fd0a1-130">Verify the specified Application Users account exists.</span></span>  

- <span data-ttu-id="fd0a1-131">使用 SSO 管理实用工具来验证指定的关联应用程序配置为使用正确的应用程序用户帐户。</span><span class="sxs-lookup"><span data-stu-id="fd0a1-131">Use the SSO Administration Utility to verify the specified affiliate application is configured to use the correct application users account.</span></span>  

  <span data-ttu-id="fd0a1-132">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="fd0a1-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="fd0a1-133">SSO 用户组</span><span class="sxs-lookup"><span data-stu-id="fd0a1-133">SSO User Groups</span></span>](../core/sso-user-groups.md)  

- [<span data-ttu-id="fd0a1-134">SSO 关联应用程序</span><span class="sxs-lookup"><span data-stu-id="fd0a1-134">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)  

- [<span data-ttu-id="fd0a1-135">如何更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="fd0a1-135">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
