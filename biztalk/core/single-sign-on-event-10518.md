---
title: 单一登录： 事件 10518 |Microsoft Docs
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
ms.openlocfilehash: 76b267950d734f6a0935ed22e27782e8a6bcd1f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011406"
---
# <a name="single-sign-on-event-10518"></a><span data-ttu-id="e9ef0-102">单一登录： 事件 10518</span><span class="sxs-lookup"><span data-stu-id="e9ef0-102">Single Sign-On: Event 10518</span></span>
## <a name="details"></a><span data-ttu-id="e9ef0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e9ef0-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e9ef0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e9ef0-104">Product Name</span></span>   |                                                                                                                                                                                                                                <span data-ttu-id="e9ef0-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e9ef0-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="e9ef0-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e9ef0-106">Product Version</span></span> |                                                                                                                                                                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                                                                |
|    <span data-ttu-id="e9ef0-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e9ef0-107">Event ID</span></span>     |                                                                                                                                                                                                                                          <span data-ttu-id="e9ef0-108">10518</span><span class="sxs-lookup"><span data-stu-id="e9ef0-108">10518</span></span>                                                                                                                                                                                                                                           |
|  <span data-ttu-id="e9ef0-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e9ef0-109">Event Source</span></span>   |                                                                                                                                                                                                                                          <span data-ttu-id="e9ef0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e9ef0-110">ENTSSO</span></span>                                                                                                                                                                                                                                          |
|    <span data-ttu-id="e9ef0-111">组件</span><span class="sxs-lookup"><span data-stu-id="e9ef0-111">Component</span></span>    |                                                                                                                                                                                                                                           <span data-ttu-id="e9ef0-112">N\A</span><span class="sxs-lookup"><span data-stu-id="e9ef0-112">N\A</span></span>                                                                                                                                                                                                                                            |
|  <span data-ttu-id="e9ef0-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e9ef0-113">Symbolic Name</span></span>  |                                                                                                                                                                                                                                 <span data-ttu-id="e9ef0-114">SSO_WARN_BAD_USER_GROUP</span><span class="sxs-lookup"><span data-stu-id="e9ef0-114">SSO_WARN_BAD_USER_GROUP</span></span>                                                                                                                                                                                                                                  |
|  <span data-ttu-id="e9ef0-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e9ef0-115">Message Text</span></span>   | <span data-ttu-id="e9ef0-116">用于此应用程序的应用程序用户帐户无效。</span><span class="sxs-lookup"><span data-stu-id="e9ef0-116">The Application Users account for this application is not valid.</span></span> <span data-ttu-id="e9ef0-117">如果是本地帐户，请检查服务器上是否存在此帐户。</span><span class="sxs-lookup"><span data-stu-id="e9ef0-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="e9ef0-118">如果是域帐户，请与域管理员联系。</span><span class="sxs-lookup"><span data-stu-id="e9ef0-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="e9ef0-119">当帐户有效时，启用应用程序。</span><span class="sxs-lookup"><span data-stu-id="e9ef0-119">Enable the application when the account is valid.</span></span> <span data-ttu-id="e9ef0-120">如果您不打算在此计算机上使用此应用程序，则可以忽略此消息。</span><span class="sxs-lookup"><span data-stu-id="e9ef0-120">You can ignore this message if you are not going to use this application on this computer.%r</span></span><br /><br /> <span data-ttu-id="e9ef0-121">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e9ef0-121">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="e9ef0-122">应用程序用户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="e9ef0-122">Application Users: %2%r</span></span><br /><br /> <span data-ttu-id="e9ef0-123">无效帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="e9ef0-123">Invalid accounts: %3%r</span></span><br /><br /> <span data-ttu-id="e9ef0-124">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="e9ef0-124">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="e9ef0-125">解释</span><span class="sxs-lookup"><span data-stu-id="e9ef0-125">Explanation</span></span>  
 <span data-ttu-id="e9ef0-126">此警告事件表示应用程序用户组帐户不是有效的 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="e9ef0-126">This Warning event indicates that an Application Users group account is not a valid Windows account.</span></span> <span data-ttu-id="e9ef0-127">每个关联应用程序都有一个对应的应用程序用户帐户组。</span><span class="sxs-lookup"><span data-stu-id="e9ef0-127">There is one Application Users account group for each affiliate application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="e9ef0-128">用户操作</span><span class="sxs-lookup"><span data-stu-id="e9ef0-128">User Action</span></span>  
 <span data-ttu-id="e9ef0-129">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="e9ef0-129">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="e9ef0-130">验证指定的应用程序用户帐户是否存在。</span><span class="sxs-lookup"><span data-stu-id="e9ef0-130">Verify the specified Application Users account exists.</span></span>  

- <span data-ttu-id="e9ef0-131">使用 SSO 管理实用工具来验证指定的关联应用程序是否配置为使用正确的应用程序用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e9ef0-131">Use the SSO Administration Utility to verify the specified affiliate application is configured to use the correct application users account.</span></span>  

  <span data-ttu-id="e9ef0-132">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="e9ef0-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="e9ef0-133">SSO 用户组</span><span class="sxs-lookup"><span data-stu-id="e9ef0-133">SSO User Groups</span></span>](../core/sso-user-groups.md)  

- [<span data-ttu-id="e9ef0-134">SSO 关联应用程序</span><span class="sxs-lookup"><span data-stu-id="e9ef0-134">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)  

- [<span data-ttu-id="e9ef0-135">如何更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="e9ef0-135">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
