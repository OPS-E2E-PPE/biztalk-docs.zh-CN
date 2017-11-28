---
title: "单一登录： 事件 11042 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1927bb5-a400-4e3a-8f80-95ef5693216c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da20346fbf2f73ac2ab64db3c9137394aa5bd366
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11042"></a><span data-ttu-id="df8f5-102">单一登录： 事件 11042</span><span class="sxs-lookup"><span data-stu-id="df8f5-102">Single Sign-On: Event 11042</span></span>
## <a name="details"></a><span data-ttu-id="df8f5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="df8f5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="df8f5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="df8f5-104">Product Name</span></span>|<span data-ttu-id="df8f5-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="df8f5-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="df8f5-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="df8f5-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="df8f5-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="df8f5-107">Event ID</span></span>|<span data-ttu-id="df8f5-108">11042</span><span class="sxs-lookup"><span data-stu-id="df8f5-108">11042</span></span>|  
|<span data-ttu-id="df8f5-109">事件源</span><span class="sxs-lookup"><span data-stu-id="df8f5-109">Event Source</span></span>|<span data-ttu-id="df8f5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="df8f5-110">ENTSSO</span></span>|  
|<span data-ttu-id="df8f5-111">组件</span><span class="sxs-lookup"><span data-stu-id="df8f5-111">Component</span></span>|<span data-ttu-id="df8f5-112">N/A</span><span class="sxs-lookup"><span data-stu-id="df8f5-112">N/A</span></span>|  
|<span data-ttu-id="df8f5-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="df8f5-113">Symbolic Name</span></span>|<span data-ttu-id="df8f5-114">SSO_WARN_ACCESS_DENIED_ACCOUNTS</span><span class="sxs-lookup"><span data-stu-id="df8f5-114">SSO_WARN_ACCESS_DENIED_ACCOUNTS</span></span>|  
|<span data-ttu-id="df8f5-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="df8f5-115">Message Text</span></span>|<span data-ttu-id="df8f5-116">访问被拒绝。</span><span class="sxs-lookup"><span data-stu-id="df8f5-116">Access denied.</span></span><br /><br /> <span data-ttu-id="df8f5-117">若要执行此功能，客户端用户必须是以下某一帐户中的成员。%r</span><span class="sxs-lookup"><span data-stu-id="df8f5-117">The client user must be a member of one of the following accounts to perform this function.%r</span></span><br /><br /> <span data-ttu-id="df8f5-118">SSO Administrators: %1 %r</span><span class="sxs-lookup"><span data-stu-id="df8f5-118">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="df8f5-119">SSO 关联管理员: %2 %r</span><span class="sxs-lookup"><span data-stu-id="df8f5-119">SSO Affiliate Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="df8f5-120">Application Administrators: %3 %r</span><span class="sxs-lookup"><span data-stu-id="df8f5-120">Application Administrators: %3%r</span></span><br /><br /> <span data-ttu-id="df8f5-121">Application Users: %4 %r</span><span class="sxs-lookup"><span data-stu-id="df8f5-121">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="df8f5-122">其他数据： %5</span><span class="sxs-lookup"><span data-stu-id="df8f5-122">Additional Data: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="df8f5-123">解释</span><span class="sxs-lookup"><span data-stu-id="df8f5-123">Explanation</span></span>  
 <span data-ttu-id="df8f5-124">若要执行此功能，客户端用户必须是警告中列出的其中一个帐户中的成员。</span><span class="sxs-lookup"><span data-stu-id="df8f5-124">The client user must be a member of one of the accounts listed in the warning to perform this function.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="df8f5-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="df8f5-125">User Action</span></span>  
 <span data-ttu-id="df8f5-126">若要执行此功能，您必须加入到其中一个帐户。</span><span class="sxs-lookup"><span data-stu-id="df8f5-126">You must join one of the accounts to perform this function.</span></span>