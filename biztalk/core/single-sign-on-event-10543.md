---
title: 单一登录：Event 10543 | Microsoft Docs
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
ms.openlocfilehash: 4f8a3b284910ea5555085a5617a2d2922d0231f3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243386"
---
# <a name="single-sign-on-event-10543"></a><span data-ttu-id="45634-102">单一登录：事件 10543</span><span class="sxs-lookup"><span data-stu-id="45634-102">Single Sign-On: Event 10543</span></span>
## <a name="details"></a><span data-ttu-id="45634-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="45634-103">Details</span></span>  

|                 |                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="45634-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="45634-104">Product Name</span></span>   |                                                               <span data-ttu-id="45634-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="45634-105">Enterprise Single Sign-On</span></span>                                                                |
| <span data-ttu-id="45634-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="45634-106">Product Version</span></span> |                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                               |
|    <span data-ttu-id="45634-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="45634-107">Event ID</span></span>     |                                                                         <span data-ttu-id="45634-108">10543</span><span class="sxs-lookup"><span data-stu-id="45634-108">10543</span></span>                                                                          |
|  <span data-ttu-id="45634-109">事件源</span><span class="sxs-lookup"><span data-stu-id="45634-109">Event Source</span></span>   |                                                                         <span data-ttu-id="45634-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="45634-110">ENTSSO</span></span>                                                                         |
|    <span data-ttu-id="45634-111">组件</span><span class="sxs-lookup"><span data-stu-id="45634-111">Component</span></span>    |                                                                           <span data-ttu-id="45634-112">CO</span><span class="sxs-lookup"><span data-stu-id="45634-112">CO</span></span>                                                                           |
|  <span data-ttu-id="45634-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="45634-113">Symbolic Name</span></span>  |                                                           <span data-ttu-id="45634-114">SSO_WARN_ORIGINAL_TICKET_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="45634-114">SSO_WARN_ORIGINAL_TICKET_VALIDATED</span></span>                                                           |
|  <span data-ttu-id="45634-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="45634-115">Message Text</span></span>   | <span data-ttu-id="45634-116">需要验证所颁发票证。</span><span class="sxs-lookup"><span data-stu-id="45634-116">The ticket was issued with validation required.</span></span> <span data-ttu-id="45634-117">它无法兑换此应用程序未经 validated.%r</span><span class="sxs-lookup"><span data-stu-id="45634-117">It cannot be redeemed for this application without being validated.%r</span></span><br /><br /> <span data-ttu-id="45634-118">应用程序名称： %1</span><span class="sxs-lookup"><span data-stu-id="45634-118">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="45634-119">解释</span><span class="sxs-lookup"><span data-stu-id="45634-119">Explanation</span></span>  
 <span data-ttu-id="45634-120">此警告事件指示需要验证发布应用程序票证。</span><span class="sxs-lookup"><span data-stu-id="45634-120">This Warning event indicates that an application ticket was issued with validation required.</span></span> <span data-ttu-id="45634-121">未经验证，不能兑换票证。</span><span class="sxs-lookup"><span data-stu-id="45634-121">Tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="45634-122">票证验证是在每个关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="45634-122">Validation of the ticket is on a per affiliate application basis.</span></span>  

## <a name="user-action"></a><span data-ttu-id="45634-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="45634-123">User Action</span></span>  
 <span data-ttu-id="45634-124">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="45634-124">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="45634-125">如果使用企业单一登录，请确保您的消息只通过受信任的主机流动。</span><span class="sxs-lookup"><span data-stu-id="45634-125">If you are using Enterprise Single Sign-On, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="45634-126">这将减少与消息中的数据被篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="45634-126">This will reduce the risk of tampering with the data in the message.</span></span>  

- <span data-ttu-id="45634-127">如果你的方案允许，将关闭此应用程序的验证。</span><span class="sxs-lookup"><span data-stu-id="45634-127">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="45634-128">验证是一个管理选项，可以关闭状态的系统或只需为此特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="45634-128">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  

  <span data-ttu-id="45634-129">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="45634-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="45634-130">SSO 票证</span><span class="sxs-lookup"><span data-stu-id="45634-130">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="45634-131">如何列出关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="45634-131">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="45634-132">如何更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="45634-132">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
