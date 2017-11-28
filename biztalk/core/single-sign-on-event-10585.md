---
title: "单一登录： 事件 10585 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51c55ada-1ee3-4626-b044-9c537d11f0d9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b4781628121edad8904130e546038698de03161
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10585"></a><span data-ttu-id="e1fa1-102">单一登录： 事件 10585</span><span class="sxs-lookup"><span data-stu-id="e1fa1-102">Single Sign-On: Event 10585</span></span>
## <a name="details"></a><span data-ttu-id="e1fa1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e1fa1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e1fa1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e1fa1-104">Product Name</span></span>|<span data-ttu-id="e1fa1-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e1fa1-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="e1fa1-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e1fa1-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="e1fa1-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e1fa1-107">Event ID</span></span>|<span data-ttu-id="e1fa1-108">10585</span><span class="sxs-lookup"><span data-stu-id="e1fa1-108">10585</span></span>|  
|<span data-ttu-id="e1fa1-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e1fa1-109">Event Source</span></span>|<span data-ttu-id="e1fa1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e1fa1-110">ENTSSO</span></span>|  
|<span data-ttu-id="e1fa1-111">组件</span><span class="sxs-lookup"><span data-stu-id="e1fa1-111">Component</span></span>|<span data-ttu-id="e1fa1-112">N/A</span><span class="sxs-lookup"><span data-stu-id="e1fa1-112">N/A</span></span>|  
|<span data-ttu-id="e1fa1-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e1fa1-113">Symbolic Name</span></span>|<span data-ttu-id="e1fa1-114">SSO_WARN_EXPIRED_TICKET_REDEEMED</span><span class="sxs-lookup"><span data-stu-id="e1fa1-114">SSO_WARN_EXPIRED_TICKET_REDEEMED</span></span>|  
|<span data-ttu-id="e1fa1-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e1fa1-115">Message Text</span></span>|<span data-ttu-id="e1fa1-116">票证超时期限过后将兑换票证。</span><span class="sxs-lookup"><span data-stu-id="e1fa1-116">A ticket is being redeemed after the ticket time-out period has expired.</span></span> <span data-ttu-id="e1fa1-117">允许此操作是因为已禁用了此应用程序的票证超时。%r</span><span class="sxs-lookup"><span data-stu-id="e1fa1-117">This is allowed because the ticket time-out is disabled for this application.%r</span></span><br /><br /> <span data-ttu-id="e1fa1-118">应用程序名称： %1</span><span class="sxs-lookup"><span data-stu-id="e1fa1-118">Application Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e1fa1-119">解释</span><span class="sxs-lookup"><span data-stu-id="e1fa1-119">Explanation</span></span>  
 <span data-ttu-id="e1fa1-120">可以启用也可以禁用票证超时。</span><span class="sxs-lookup"><span data-stu-id="e1fa1-120">Ticket time-out can be enabled or disabled.</span></span> <span data-ttu-id="e1fa1-121">在这种情况下将兑换票证（尽管票证超时期限已过），因为已禁用超时。</span><span class="sxs-lookup"><span data-stu-id="e1fa1-121">In this case a ticket is being redeemed even though its time-out period has expired, because the time-out is disabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e1fa1-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="e1fa1-122">User Action</span></span>  
 <span data-ttu-id="e1fa1-123">如果应禁用超时，则不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="e1fa1-123">If the time-out was supposed to be disabled, no user action is required.</span></span> <span data-ttu-id="e1fa1-124">但是，如果您不知道此特定应用程序已禁用了超时，请立即检查应用程序以确保您希望允许超时。</span><span class="sxs-lookup"><span data-stu-id="e1fa1-124">However, if you were not aware that this particular application had its time-out disabled, check the application immediately to be sure you want to allow it.</span></span>