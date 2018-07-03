---
title: 单一登录： 事件 10543 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46b1ffda-a6c1-408c-acb4-074183d697bc
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf5c026384bf463f6ee0a33045dd1e7b1fca4188
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998439"
---
# <a name="single-sign-on-event-10543"></a><span data-ttu-id="92c73-102">单一登录： 事件 10543</span><span class="sxs-lookup"><span data-stu-id="92c73-102">Single Sign-On: Event 10543</span></span>
## <a name="details"></a><span data-ttu-id="92c73-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="92c73-103">Details</span></span>  

|                 |                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="92c73-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="92c73-104">Product Name</span></span>   |                                                               <span data-ttu-id="92c73-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="92c73-105">Enterprise Single Sign-On</span></span>                                                                |
| <span data-ttu-id="92c73-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="92c73-106">Product Version</span></span> |                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                               |
|    <span data-ttu-id="92c73-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="92c73-107">Event ID</span></span>     |                                                                         <span data-ttu-id="92c73-108">10543</span><span class="sxs-lookup"><span data-stu-id="92c73-108">10543</span></span>                                                                          |
|  <span data-ttu-id="92c73-109">事件源</span><span class="sxs-lookup"><span data-stu-id="92c73-109">Event Source</span></span>   |                                                                         <span data-ttu-id="92c73-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="92c73-110">ENTSSO</span></span>                                                                         |
|    <span data-ttu-id="92c73-111">组件</span><span class="sxs-lookup"><span data-stu-id="92c73-111">Component</span></span>    |                                                                           <span data-ttu-id="92c73-112">CO</span><span class="sxs-lookup"><span data-stu-id="92c73-112">CO</span></span>                                                                           |
|  <span data-ttu-id="92c73-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="92c73-113">Symbolic Name</span></span>  |                                                           <span data-ttu-id="92c73-114">SSO_WARN_ORIGINAL_TICKET_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="92c73-114">SSO_WARN_ORIGINAL_TICKET_VALIDATED</span></span>                                                           |
|  <span data-ttu-id="92c73-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="92c73-115">Message Text</span></span>   | <span data-ttu-id="92c73-116">需要验证之后发出票证。</span><span class="sxs-lookup"><span data-stu-id="92c73-116">The ticket was issued with validation required.</span></span> <span data-ttu-id="92c73-117">此应用程序在不经过验证的情况下无法兑换票证。%r</span><span class="sxs-lookup"><span data-stu-id="92c73-117">It cannot be redeemed for this application without being validated.%r</span></span><br /><br /> <span data-ttu-id="92c73-118">应用程序名称： %1</span><span class="sxs-lookup"><span data-stu-id="92c73-118">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="92c73-119">解释</span><span class="sxs-lookup"><span data-stu-id="92c73-119">Explanation</span></span>  
 <span data-ttu-id="92c73-120">此警告事件表明应用程序票证需要经过验证之后才能发出。</span><span class="sxs-lookup"><span data-stu-id="92c73-120">This Warning event indicates that an application ticket was issued with validation required.</span></span> <span data-ttu-id="92c73-121">票证未经验证不能兑换。</span><span class="sxs-lookup"><span data-stu-id="92c73-121">Tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="92c73-122">票证的验证基于每个关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="92c73-122">Validation of the ticket is on a per affiliate application basis.</span></span>  

## <a name="user-action"></a><span data-ttu-id="92c73-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="92c73-123">User Action</span></span>  
 <span data-ttu-id="92c73-124">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="92c73-124">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="92c73-125">如果您使用的是企业单一登录，请确保您的消息只通过受信任主机传输。</span><span class="sxs-lookup"><span data-stu-id="92c73-125">If you are using Enterprise Single Sign-On, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="92c73-126">这将降低在消息中篡改数据的风险。</span><span class="sxs-lookup"><span data-stu-id="92c73-126">This will reduce the risk of tampering with the data in the message.</span></span>  

- <span data-ttu-id="92c73-127">如果情况允许，请针对此应用程序关闭验证。</span><span class="sxs-lookup"><span data-stu-id="92c73-127">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="92c73-128">验证是一个管理选项，可以针对整个系统、或只针对此特定的应用程序关闭该选项。</span><span class="sxs-lookup"><span data-stu-id="92c73-128">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  

  <span data-ttu-id="92c73-129">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="92c73-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="92c73-130">SSO 票证</span><span class="sxs-lookup"><span data-stu-id="92c73-130">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="92c73-131">如何列出关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="92c73-131">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="92c73-132">如何更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="92c73-132">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
