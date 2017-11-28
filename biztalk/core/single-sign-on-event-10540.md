---
title: "单一登录： 事件 10540 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce91ff30-3d68-4c5f-a955-5c426e94d917
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec48afebfa36411594c28908a233409311e32df9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10540"></a><span data-ttu-id="716ee-102">单一登录： 事件 10540</span><span class="sxs-lookup"><span data-stu-id="716ee-102">Single Sign-On: Event 10540</span></span>
## <a name="details"></a><span data-ttu-id="716ee-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="716ee-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="716ee-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="716ee-104">Product Name</span></span>|<span data-ttu-id="716ee-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="716ee-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="716ee-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="716ee-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="716ee-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="716ee-107">Event ID</span></span>|<span data-ttu-id="716ee-108">10540</span><span class="sxs-lookup"><span data-stu-id="716ee-108">10540</span></span>|  
|<span data-ttu-id="716ee-109">事件源</span><span class="sxs-lookup"><span data-stu-id="716ee-109">Event Source</span></span>|<span data-ttu-id="716ee-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="716ee-110">ENTSSO</span></span>|  
|<span data-ttu-id="716ee-111">组件</span><span class="sxs-lookup"><span data-stu-id="716ee-111">Component</span></span>|<span data-ttu-id="716ee-112">CO</span><span class="sxs-lookup"><span data-stu-id="716ee-112">CO</span></span>|  
|<span data-ttu-id="716ee-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="716ee-113">Symbolic Name</span></span>|<span data-ttu-id="716ee-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="716ee-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="716ee-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="716ee-115">Message Text</span></span>|<span data-ttu-id="716ee-116">此应用程序未启用票证。%r</span><span class="sxs-lookup"><span data-stu-id="716ee-116">Tickets are not enabled for this application.%r</span></span><br /><br /> <span data-ttu-id="716ee-117">应用程序名称： %1</span><span class="sxs-lookup"><span data-stu-id="716ee-117">Application Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="716ee-118">解释</span><span class="sxs-lookup"><span data-stu-id="716ee-118">Explanation</span></span>  
 <span data-ttu-id="716ee-119">此警告事件表示，此应用程序未启用票证功能。</span><span class="sxs-lookup"><span data-stu-id="716ee-119">This Warning event indicates that the tickets feature has not been enabled for this application.</span></span> <span data-ttu-id="716ee-120">使用 SSO 票证是每个 SSO 应用程序的可选功能。</span><span class="sxs-lookup"><span data-stu-id="716ee-120">The use of SSO tickets is an optional feature for each SSO application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="716ee-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="716ee-121">User Action</span></span>  
 <span data-ttu-id="716ee-122">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="716ee-122">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="716ee-123">与应用程序管理员联系，为此 SSO 应用程序启用票证。</span><span class="sxs-lookup"><span data-stu-id="716ee-123">Contact your Application Administrator to enable tickets for this SSO application.</span></span> <span data-ttu-id="716ee-124">可使用 SSO 管理工具（GUI 或命令行）完成此操作。</span><span class="sxs-lookup"><span data-stu-id="716ee-124">This can be done using the SSO administration tools (GUI or command line).</span></span>  
  
 <span data-ttu-id="716ee-125">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="716ee-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="716ee-126">SSO 票证</span><span class="sxs-lookup"><span data-stu-id="716ee-126">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="716ee-127">如何列出关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="716ee-127">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [<span data-ttu-id="716ee-128">如何更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="716ee-128">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)