---
title: 单一登录： 事件 10539 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a67f5719-da7c-4ae0-a6fe-ff7b653a184d
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94ca34f40359b518e1a52b3326dae9917ca4910e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271453"
---
# <a name="single-sign-on-event-10539"></a><span data-ttu-id="2e69e-102">单一登录： 事件 10539</span><span class="sxs-lookup"><span data-stu-id="2e69e-102">Single Sign-On: Event 10539</span></span>
## <a name="details"></a><span data-ttu-id="2e69e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2e69e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2e69e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2e69e-104">Product Name</span></span>|<span data-ttu-id="2e69e-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="2e69e-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="2e69e-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="2e69e-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="2e69e-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2e69e-107">Event ID</span></span>|<span data-ttu-id="2e69e-108">10539</span><span class="sxs-lookup"><span data-stu-id="2e69e-108">10539</span></span>|  
|<span data-ttu-id="2e69e-109">事件源</span><span class="sxs-lookup"><span data-stu-id="2e69e-109">Event Source</span></span>|<span data-ttu-id="2e69e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2e69e-110">ENTSSO</span></span>|  
|<span data-ttu-id="2e69e-111">组件</span><span class="sxs-lookup"><span data-stu-id="2e69e-111">Component</span></span>|<span data-ttu-id="2e69e-112">CO</span><span class="sxs-lookup"><span data-stu-id="2e69e-112">CO</span></span>|  
|<span data-ttu-id="2e69e-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="2e69e-113">Symbolic Name</span></span>|<span data-ttu-id="2e69e-114">SSO_WARN_SSO_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="2e69e-114">SSO_WARN_SSO_TICKETS_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="2e69e-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="2e69e-115">Message Text</span></span>|<span data-ttu-id="2e69e-116">SSO 系统没有启用票证。</span><span class="sxs-lookup"><span data-stu-id="2e69e-116">Tickets are not enabled for the SSO system.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2e69e-117">解释</span><span class="sxs-lookup"><span data-stu-id="2e69e-117">Explanation</span></span>  
 <span data-ttu-id="2e69e-118">此警告事件表示 SSO 票证尚未启用。</span><span class="sxs-lookup"><span data-stu-id="2e69e-118">This Warning event indicates that the use of SSO tickets is not enabled.</span></span> <span data-ttu-id="2e69e-119">允许使用 SSO 票证是 SSO 系统的一个可选功能。</span><span class="sxs-lookup"><span data-stu-id="2e69e-119">Allowing the use of SSO tickets is an optional feature of the SSO system.</span></span> <span data-ttu-id="2e69e-120">您的 SSO 系统上尚未启用此功能。</span><span class="sxs-lookup"><span data-stu-id="2e69e-120">This feature has not been enabled on your SSO system.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2e69e-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="2e69e-121">User Action</span></span>  
 <span data-ttu-id="2e69e-122">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2e69e-122">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="2e69e-123">请与 SSO 管理员联系以启用 SSO 系统票证。</span><span class="sxs-lookup"><span data-stu-id="2e69e-123">Contact your SSO Administrator to enable tickets for the SSO system.</span></span> <span data-ttu-id="2e69e-124">可使用 SSO 管理工具（GUI 或命令行）完成此操作。</span><span class="sxs-lookup"><span data-stu-id="2e69e-124">This can be done using the SSO administration tools (GUI or command line).</span></span>  
  
 <span data-ttu-id="2e69e-125">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="2e69e-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="2e69e-126">如何配置 SSO 票证</span><span class="sxs-lookup"><span data-stu-id="2e69e-126">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)  
  
-   [<span data-ttu-id="2e69e-127">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="2e69e-127">Using SSO</span></span>](../core/using-sso.md)