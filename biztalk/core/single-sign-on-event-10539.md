---
title: 单一登录：Event 10539 | Microsoft Docs
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
ms.openlocfilehash: cbae36ca6e261fab1b7ae4e691f64da2bf9ba718
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392922"
---
# <a name="single-sign-on-event-10539"></a><span data-ttu-id="fc241-102">单一登录：事件 10539</span><span class="sxs-lookup"><span data-stu-id="fc241-102">Single Sign-On: Event 10539</span></span>
## <a name="details"></a><span data-ttu-id="fc241-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="fc241-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="fc241-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="fc241-104">Product Name</span></span>   |                 <span data-ttu-id="fc241-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="fc241-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="fc241-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="fc241-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="fc241-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fc241-107">Event ID</span></span>     |                           <span data-ttu-id="fc241-108">10539</span><span class="sxs-lookup"><span data-stu-id="fc241-108">10539</span></span>                            |
|  <span data-ttu-id="fc241-109">事件源</span><span class="sxs-lookup"><span data-stu-id="fc241-109">Event Source</span></span>   |                           <span data-ttu-id="fc241-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fc241-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="fc241-111">组件</span><span class="sxs-lookup"><span data-stu-id="fc241-111">Component</span></span>    |                             <span data-ttu-id="fc241-112">CO</span><span class="sxs-lookup"><span data-stu-id="fc241-112">CO</span></span>                             |
|  <span data-ttu-id="fc241-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="fc241-113">Symbolic Name</span></span>  |              <span data-ttu-id="fc241-114">SSO_WARN_SSO_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="fc241-114">SSO_WARN_SSO_TICKETS_NOT_ALLOWED</span></span>              |
|  <span data-ttu-id="fc241-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="fc241-115">Message Text</span></span>   |        <span data-ttu-id="fc241-116">SSO 系统未启用票证。</span><span class="sxs-lookup"><span data-stu-id="fc241-116">Tickets are not enabled for the SSO system.</span></span>         |

## <a name="explanation"></a><span data-ttu-id="fc241-117">解释</span><span class="sxs-lookup"><span data-stu-id="fc241-117">Explanation</span></span>  
 <span data-ttu-id="fc241-118">此警告事件表明未启用使用 SSO 票证。</span><span class="sxs-lookup"><span data-stu-id="fc241-118">This Warning event indicates that the use of SSO tickets is not enabled.</span></span> <span data-ttu-id="fc241-119">允许使用 SSO 票证是 SSO 系统的一项可选功能。</span><span class="sxs-lookup"><span data-stu-id="fc241-119">Allowing the use of SSO tickets is an optional feature of the SSO system.</span></span> <span data-ttu-id="fc241-120">尚未在 SSO 系统上启用此功能。</span><span class="sxs-lookup"><span data-stu-id="fc241-120">This feature has not been enabled on your SSO system.</span></span>  

## <a name="user-action"></a><span data-ttu-id="fc241-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="fc241-121">User Action</span></span>  
 <span data-ttu-id="fc241-122">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fc241-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="fc241-123">与 SSO 管理员联系以启用 SSO 系统票证。</span><span class="sxs-lookup"><span data-stu-id="fc241-123">Contact your SSO Administrator to enable tickets for the SSO system.</span></span> <span data-ttu-id="fc241-124">这可以使用 SSO 管理工具 （GUI 或命令行）。</span><span class="sxs-lookup"><span data-stu-id="fc241-124">This can be done using the SSO administration tools (GUI or command line).</span></span>  

  <span data-ttu-id="fc241-125">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="fc241-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="fc241-126">如何配置 SSO 票证</span><span class="sxs-lookup"><span data-stu-id="fc241-126">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)  

- [<span data-ttu-id="fc241-127">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="fc241-127">Using SSO</span></span>](../core/using-sso.md)
