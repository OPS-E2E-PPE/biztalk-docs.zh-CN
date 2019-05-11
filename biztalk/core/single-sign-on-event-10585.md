---
title: 单一登录：Event 10585 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c55ada-1ee3-4626-b044-9c537d11f0d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfca6095e57936df056558e84ec0ed8ecdb8b002
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530944"
---
# <a name="single-sign-on-event-10585"></a><span data-ttu-id="d7f2d-102">单一登录：事件 10585</span><span class="sxs-lookup"><span data-stu-id="d7f2d-102">Single Sign-On: Event 10585</span></span>
## <a name="details"></a><span data-ttu-id="d7f2d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d7f2d-103">Details</span></span>  
  
|                 |                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d7f2d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d7f2d-104">Product Name</span></span>   |                                                                                 <span data-ttu-id="d7f2d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="d7f2d-105">Enterprise Single Sign-On</span></span>                                                                                 |
| <span data-ttu-id="d7f2d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="d7f2d-106">Product Version</span></span> |                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                 |
|    <span data-ttu-id="d7f2d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d7f2d-107">Event ID</span></span>     |                                                                                           <span data-ttu-id="d7f2d-108">10585</span><span class="sxs-lookup"><span data-stu-id="d7f2d-108">10585</span></span>                                                                                           |
|  <span data-ttu-id="d7f2d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="d7f2d-109">Event Source</span></span>   |                                                                                          <span data-ttu-id="d7f2d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d7f2d-110">ENTSSO</span></span>                                                                                           |
|    <span data-ttu-id="d7f2d-111">组件</span><span class="sxs-lookup"><span data-stu-id="d7f2d-111">Component</span></span>    |                                                                                            <span data-ttu-id="d7f2d-112">不可用</span><span class="sxs-lookup"><span data-stu-id="d7f2d-112">N/A</span></span>                                                                                            |
|  <span data-ttu-id="d7f2d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="d7f2d-113">Symbolic Name</span></span>  |                                                                             <span data-ttu-id="d7f2d-114">SSO_WARN_EXPIRED_TICKET_REDEEMED</span><span class="sxs-lookup"><span data-stu-id="d7f2d-114">SSO_WARN_EXPIRED_TICKET_REDEEMED</span></span>                                                                              |
|  <span data-ttu-id="d7f2d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="d7f2d-115">Message Text</span></span>   | <span data-ttu-id="d7f2d-116">票证将兑换票证超时期限已过。</span><span class="sxs-lookup"><span data-stu-id="d7f2d-116">A ticket is being redeemed after the ticket time-out period has expired.</span></span> <span data-ttu-id="d7f2d-117">这允许，因为 application.%r 禁用票证超时值</span><span class="sxs-lookup"><span data-stu-id="d7f2d-117">This is allowed because the ticket time-out is disabled for this application.%r</span></span><br /><br /> <span data-ttu-id="d7f2d-118">应用程序名称： %1</span><span class="sxs-lookup"><span data-stu-id="d7f2d-118">Application Name: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d7f2d-119">解释</span><span class="sxs-lookup"><span data-stu-id="d7f2d-119">Explanation</span></span>  
 <span data-ttu-id="d7f2d-120">可以启用或禁用票证超时值。</span><span class="sxs-lookup"><span data-stu-id="d7f2d-120">Ticket time-out can be enabled or disabled.</span></span> <span data-ttu-id="d7f2d-121">在这种情况下将兑换票证即使其超时期限已过，因为已禁用超时。</span><span class="sxs-lookup"><span data-stu-id="d7f2d-121">In this case a ticket is being redeemed even though its time-out period has expired, because the time-out is disabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d7f2d-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="d7f2d-122">User Action</span></span>  
 <span data-ttu-id="d7f2d-123">如果应禁用超时，不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="d7f2d-123">If the time-out was supposed to be disabled, no user action is required.</span></span> <span data-ttu-id="d7f2d-124">但是，如果您没有意识到此特定应用程序已禁用其超时，则应检查应用程序立即以确保你想要允许它。</span><span class="sxs-lookup"><span data-stu-id="d7f2d-124">However, if you were not aware that this particular application had its time-out disabled, check the application immediately to be sure you want to allow it.</span></span>