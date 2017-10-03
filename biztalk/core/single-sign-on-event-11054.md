---
title: "单一登录： 事件 11054 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59dc801d-fc78-4561-8a26-9d815c86d842
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c4d71bc77f36231ddec939faf5e904e45017614
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11054"></a><span data-ttu-id="5a954-102">单一登录： 事件 11054</span><span class="sxs-lookup"><span data-stu-id="5a954-102">Single Sign-On: Event 11054</span></span>
## <a name="details"></a><span data-ttu-id="5a954-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5a954-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5a954-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5a954-104">Product Name</span></span>|<span data-ttu-id="5a954-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5a954-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="5a954-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="5a954-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="5a954-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5a954-107">Event ID</span></span>|<span data-ttu-id="5a954-108">11054</span><span class="sxs-lookup"><span data-stu-id="5a954-108">11054</span></span>|  
|<span data-ttu-id="5a954-109">事件源</span><span class="sxs-lookup"><span data-stu-id="5a954-109">Event Source</span></span>|<span data-ttu-id="5a954-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5a954-110">ENTSSO</span></span>|  
|<span data-ttu-id="5a954-111">组件</span><span class="sxs-lookup"><span data-stu-id="5a954-111">Component</span></span>|<span data-ttu-id="5a954-112">N/A</span><span class="sxs-lookup"><span data-stu-id="5a954-112">N/A</span></span>|  
|<span data-ttu-id="5a954-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="5a954-113">Symbolic Name</span></span>|<span data-ttu-id="5a954-114">SSO_WARN_APP_USERS_NOT_GROUP</span><span class="sxs-lookup"><span data-stu-id="5a954-114">SSO_WARN_APP_USERS_NOT_GROUP</span></span>|  
|<span data-ttu-id="5a954-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="5a954-115">Message Text</span></span>|<span data-ttu-id="5a954-116">应用程序用户帐户包含一个或多个个人（不是组）帐户。</span><span class="sxs-lookup"><span data-stu-id="5a954-116">The Application Users account contains one or more individual (not group) accounts.</span></span> <span data-ttu-id="5a954-117">如果已经从 Active Directory 或本地计算机删除这些个人帐户，则必须立即从 SSO 系统中删除这些帐户，否则它们会成为安全隐患。%r</span><span class="sxs-lookup"><span data-stu-id="5a954-117">If these individual accounts are deleted from Active Directory or the local computer they must be promptly removed from the SSO system or they could become a security risk.%r</span></span><br /><br /> <span data-ttu-id="5a954-118">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5a954-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="5a954-119">Application Users: %2 %r</span><span class="sxs-lookup"><span data-stu-id="5a954-119">Application Users: %2%r</span></span><br /><br /> <span data-ttu-id="5a954-120">个人帐户： %3</span><span class="sxs-lookup"><span data-stu-id="5a954-120">Individual accounts: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5a954-121">解释</span><span class="sxs-lookup"><span data-stu-id="5a954-121">Explanation</span></span>  
 <span data-ttu-id="5a954-122">从 Active Directory 或本地计算机上删除个人帐户并不会自动从 SSO 系统删除该帐户。</span><span class="sxs-lookup"><span data-stu-id="5a954-122">Deleting an individual account from the Active Directory or local computer does not automatically delete that account from the SSO System.</span></span> <span data-ttu-id="5a954-123">这意味着如果从本地计算机删除帐户 USER1，然后另一个不同用户（例如新的员工）使用相同的名称加入到系统，则 SSO 系统会将原来 USER1 所具有的安全权限都授予新的 USER1。</span><span class="sxs-lookup"><span data-stu-id="5a954-123">This means that if the account USER1 was deleted locally, and then a different user (for instance, a new employee) joined the system using that same name, the SSO System would grant the new USER1 all security rights possessed by the original USER1.</span></span> <span data-ttu-id="5a954-124">这会形成安全隐患。</span><span class="sxs-lookup"><span data-stu-id="5a954-124">This poses a security risk.</span></span>  
  
 <span data-ttu-id="5a954-125">作为最佳实践，建议 SSO 管理员帐户使用 Active Directory 组帐户，而非个人帐户。</span><span class="sxs-lookup"><span data-stu-id="5a954-125">As a best practice, it is recommended that SSO Administration accounts use Active Directory group (not individual) accounts.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5a954-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="5a954-126">User Action</span></span>  
 <span data-ttu-id="5a954-127">在从 Active Directory 或本地计算机中删除个人帐户之前，无需进行操作。</span><span class="sxs-lookup"><span data-stu-id="5a954-127">No action is necessary until an individual account is deleted from Active Directory or the local computer.</span></span> <span data-ttu-id="5a954-128">如果发生上述删除操作，则必须尽快从 SSO 系统删除该个人帐户。</span><span class="sxs-lookup"><span data-stu-id="5a954-128">At that point, you must delete the individual account from the SSO System as soon as possible.</span></span>