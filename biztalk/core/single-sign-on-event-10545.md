---
title: "单一登录： 事件 10545 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 268cb7be-b191-4335-a4cc-7c15d879507c
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64cb10ceef5827f9c0b0aab5d9810db061af8a71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10545"></a><span data-ttu-id="07109-102">单一登录： 事件 10545</span><span class="sxs-lookup"><span data-stu-id="07109-102">Single Sign-On: Event 10545</span></span>
## <a name="details"></a><span data-ttu-id="07109-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="07109-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07109-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="07109-104">Product Name</span></span>|<span data-ttu-id="07109-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="07109-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="07109-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="07109-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="07109-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="07109-107">Event ID</span></span>|<span data-ttu-id="07109-108">10545</span><span class="sxs-lookup"><span data-stu-id="07109-108">10545</span></span>|  
|<span data-ttu-id="07109-109">事件源</span><span class="sxs-lookup"><span data-stu-id="07109-109">Event Source</span></span>|<span data-ttu-id="07109-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="07109-110">ENTSSO</span></span>|  
|<span data-ttu-id="07109-111">组件</span><span class="sxs-lookup"><span data-stu-id="07109-111">Component</span></span>|<span data-ttu-id="07109-112">CO</span><span class="sxs-lookup"><span data-stu-id="07109-112">CO</span></span>|  
|<span data-ttu-id="07109-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="07109-113">Symbolic Name</span></span>|<span data-ttu-id="07109-114">SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="07109-114">SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="07109-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="07109-115">Message Text</span></span>|<span data-ttu-id="07109-116">SSO 系统没有启用票证。</span><span class="sxs-lookup"><span data-stu-id="07109-116">Tickets are not enabled for the SSO system.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="07109-117">解释</span><span class="sxs-lookup"><span data-stu-id="07109-117">Explanation</span></span>  
 <span data-ttu-id="07109-118">此警告事件表示没有为 SSO 系统启动票证。</span><span class="sxs-lookup"><span data-stu-id="07109-118">This Warning event indicates that tickets are not enabled for the SSO System.</span></span> <span data-ttu-id="07109-119">如果在系统级别上禁用了票证功能，则也不能在关联应用程序级别上使用此功能。</span><span class="sxs-lookup"><span data-stu-id="07109-119">If ticketing is disabled at the system level, ticketing cannot be used at the Affiliate Application level either.</span></span> <span data-ttu-id="07109-120">它可启用在系统级别的票证和 Affiliate 应用程序级别禁用它。</span><span class="sxs-lookup"><span data-stu-id="07109-120">It is possible to enable tickets at the system level and disable it at the Affiliate Application level.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="07109-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="07109-121">User Action</span></span>  
 <span data-ttu-id="07109-122">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="07109-122">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="07109-123">启用 SSO 系统级别的票证。</span><span class="sxs-lookup"><span data-stu-id="07109-123">Enable tickets at the SSO System level.</span></span>  
  
 <span data-ttu-id="07109-124">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="07109-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="07109-125">SSO 票证</span><span class="sxs-lookup"><span data-stu-id="07109-125">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="07109-126">如何配置 SSO 票证</span><span class="sxs-lookup"><span data-stu-id="07109-126">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)