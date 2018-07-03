---
title: 单一登录： 事件 10544 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c79e2186-1c75-4e7b-8bf5-f582e5c2aac7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f476e664d50d05a57f42006ec08aa03d901e9f1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983926"
---
# <a name="single-sign-on-event-10544"></a><span data-ttu-id="80279-102">单一登录： 事件 10544</span><span class="sxs-lookup"><span data-stu-id="80279-102">Single Sign-On: Event 10544</span></span>
## <a name="details"></a><span data-ttu-id="80279-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="80279-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="80279-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="80279-104">Product Name</span></span>   |                 <span data-ttu-id="80279-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="80279-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="80279-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="80279-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="80279-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="80279-107">Event ID</span></span>     |                           <span data-ttu-id="80279-108">10544</span><span class="sxs-lookup"><span data-stu-id="80279-108">10544</span></span>                            |
|  <span data-ttu-id="80279-109">事件源</span><span class="sxs-lookup"><span data-stu-id="80279-109">Event Source</span></span>   |                           <span data-ttu-id="80279-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="80279-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="80279-111">组件</span><span class="sxs-lookup"><span data-stu-id="80279-111">Component</span></span>    |                             <span data-ttu-id="80279-112">CO</span><span class="sxs-lookup"><span data-stu-id="80279-112">CO</span></span>                             |
|  <span data-ttu-id="80279-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="80279-113">Symbolic Name</span></span>  |                  <span data-ttu-id="80279-114">SSO_WARN_TICKET_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="80279-114">SSO_WARN_TICKET_EXPIRED</span></span>                   |
|  <span data-ttu-id="80279-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="80279-115">Message Text</span></span>   | <span data-ttu-id="80279-116">票证已过期。%r</span><span class="sxs-lookup"><span data-stu-id="80279-116">The ticket has expired.%r</span></span><br /><br /> <span data-ttu-id="80279-117">应用程序名称： %1</span><span class="sxs-lookup"><span data-stu-id="80279-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="80279-118">解释</span><span class="sxs-lookup"><span data-stu-id="80279-118">Explanation</span></span>  
 <span data-ttu-id="80279-119">此警告事件表示应用程序票证超时已过期。</span><span class="sxs-lookup"><span data-stu-id="80279-119">This Warning event indicates that an application ticket timeout has expired.</span></span> <span data-ttu-id="80279-120">票证超时可以在系统级别和应用程序级别上指定。</span><span class="sxs-lookup"><span data-stu-id="80279-120">Ticket timeout can be specified at both the system level and the application level.</span></span> <span data-ttu-id="80279-121">如果在系统级别和应用程序级别上都已指定超时，则将由应用程序级别的超时决定过期时间。</span><span class="sxs-lookup"><span data-stu-id="80279-121">If both system level and the application level timeout are specified, the application level timeout is used to determine the expiry time.</span></span>  

## <a name="user-action"></a><span data-ttu-id="80279-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="80279-122">User Action</span></span>  
 <span data-ttu-id="80279-123">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="80279-123">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="80279-124">确定票证在验证之前就过期的原因。</span><span class="sxs-lookup"><span data-stu-id="80279-124">Determine why the ticket expired before being validated.</span></span>  

- <span data-ttu-id="80279-125">确保票证超时值足够长，以便可以从颁发票证之时延续到兑换票证之时。</span><span class="sxs-lookup"><span data-stu-id="80279-125">Ensure that the Ticket timeout value is long enough to last between the time when the ticket is issued to the time that it is redeemed.</span></span>  

  <span data-ttu-id="80279-126">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="80279-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="80279-127">SSO 票证</span><span class="sxs-lookup"><span data-stu-id="80279-127">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="80279-128">如何配置 SSO 票证</span><span class="sxs-lookup"><span data-stu-id="80279-128">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)
