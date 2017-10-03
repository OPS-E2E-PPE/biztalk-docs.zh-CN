---
title: "单一登录： 事件 11052 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c797ed19-7613-4e0f-8867-9258ec3776a4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aa45afc85535cd0107d43e795b6e3f97fcc5f9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11052"></a><span data-ttu-id="bdf9d-102">单一登录： 事件 11052</span><span class="sxs-lookup"><span data-stu-id="bdf9d-102">Single Sign-On: Event 11052</span></span>
## <a name="details"></a><span data-ttu-id="bdf9d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="bdf9d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bdf9d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="bdf9d-104">Product Name</span></span>|<span data-ttu-id="bdf9d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="bdf9d-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="bdf9d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="bdf9d-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="bdf9d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="bdf9d-107">Event ID</span></span>|<span data-ttu-id="bdf9d-108">11052</span><span class="sxs-lookup"><span data-stu-id="bdf9d-108">11052</span></span>|  
|<span data-ttu-id="bdf9d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="bdf9d-109">Event Source</span></span>|<span data-ttu-id="bdf9d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bdf9d-110">ENTSSO</span></span>|  
|<span data-ttu-id="bdf9d-111">组件</span><span class="sxs-lookup"><span data-stu-id="bdf9d-111">Component</span></span>|<span data-ttu-id="bdf9d-112">N/A</span><span class="sxs-lookup"><span data-stu-id="bdf9d-112">N/A</span></span>|  
|<span data-ttu-id="bdf9d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="bdf9d-113">Symbolic Name</span></span>|<span data-ttu-id="bdf9d-114">SSO_WARN_SSO_AFF_ADMIN_NOT_GROUP</span><span class="sxs-lookup"><span data-stu-id="bdf9d-114">SSO_WARN_SSO_AFF_ADMIN_NOT_GROUP</span></span>|  
|<span data-ttu-id="bdf9d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="bdf9d-115">Message Text</span></span>|<span data-ttu-id="bdf9d-116">SSO Affiliate Administrators 帐户包含一个或多个个人 （非组） 帐户。</span><span class="sxs-lookup"><span data-stu-id="bdf9d-116">The SSO Affiliate Administrators account contains one or more individual (not group) accounts.</span></span> <span data-ttu-id="bdf9d-117">如果已经从 Active Directory 或本地计算机删除这些个人帐户，则必须立即从 SSO 系统中删除这些帐户，否则它们会成为安全隐患。%r</span><span class="sxs-lookup"><span data-stu-id="bdf9d-117">If these individual accounts are deleted from Active Directory or the local computer they must be promptly removed from the SSO system or they could become a security risk.%r</span></span><br /><br /> <span data-ttu-id="bdf9d-118">SSO 关联管理员: %1 %r</span><span class="sxs-lookup"><span data-stu-id="bdf9d-118">SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="bdf9d-119">个人帐户： %2</span><span class="sxs-lookup"><span data-stu-id="bdf9d-119">Individual accounts: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bdf9d-120">解释</span><span class="sxs-lookup"><span data-stu-id="bdf9d-120">Explanation</span></span>  
 <span data-ttu-id="bdf9d-121">从 Active Directory 或本地计算机上删除个人帐户并不会自动从 SSO 系统删除该帐户。</span><span class="sxs-lookup"><span data-stu-id="bdf9d-121">Deleting an individual account from the Active Directory or local computer does not automatically delete that account from the SSO System.</span></span> <span data-ttu-id="bdf9d-122">这意味着如果从本地计算机删除帐户 USER1，然后另一个不同用户（例如新的员工）使用相同的名称加入到系统，则 SSO 系统会将原来 USER1 所具有的安全权限都授予新的 USER1。</span><span class="sxs-lookup"><span data-stu-id="bdf9d-122">This means that if the account USER1 was deleted locally, and then a different user (for instance, a new employee) joined the system using that same name, the SSO System would grant the new USER1 all security rights possessed by the original USER1.</span></span> <span data-ttu-id="bdf9d-123">这会形成安全隐患。</span><span class="sxs-lookup"><span data-stu-id="bdf9d-123">This poses a security risk.</span></span>  
  
 <span data-ttu-id="bdf9d-124">作为最佳实践，建议 SSO 管理员帐户使用 Active Directory 组帐户，而非个人帐户。</span><span class="sxs-lookup"><span data-stu-id="bdf9d-124">As a best practice, it is recommended that SSO Administration accounts use Active Directory group (not individual) accounts.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bdf9d-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="bdf9d-125">User Action</span></span>  
 <span data-ttu-id="bdf9d-126">在从 Active Directory 或本地计算机中删除个人帐户之前，无需进行操作。</span><span class="sxs-lookup"><span data-stu-id="bdf9d-126">No action is necessary until an individual account is deleted from Active Directory or the local computer.</span></span> <span data-ttu-id="bdf9d-127">如果发生上述删除操作，则必须尽快从 SSO 系统删除该个人帐户。</span><span class="sxs-lookup"><span data-stu-id="bdf9d-127">At that point, you must delete the individual account from the SSO System as soon as possible.</span></span>