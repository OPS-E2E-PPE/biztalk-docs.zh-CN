---
title: 单一登录： 事件 10539 |Microsoft Docs
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
ms.openlocfilehash: f7934b3011af2656f413270b4d249ca4f7f96bae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006270"
---
# <a name="single-sign-on-event-10539"></a><span data-ttu-id="478e6-102">单一登录： 事件 10539</span><span class="sxs-lookup"><span data-stu-id="478e6-102">Single Sign-On: Event 10539</span></span>
## <a name="details"></a><span data-ttu-id="478e6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="478e6-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="478e6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="478e6-104">Product Name</span></span>   |                 <span data-ttu-id="478e6-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="478e6-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="478e6-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="478e6-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="478e6-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="478e6-107">Event ID</span></span>     |                           <span data-ttu-id="478e6-108">10539</span><span class="sxs-lookup"><span data-stu-id="478e6-108">10539</span></span>                            |
|  <span data-ttu-id="478e6-109">事件源</span><span class="sxs-lookup"><span data-stu-id="478e6-109">Event Source</span></span>   |                           <span data-ttu-id="478e6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="478e6-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="478e6-111">组件</span><span class="sxs-lookup"><span data-stu-id="478e6-111">Component</span></span>    |                             <span data-ttu-id="478e6-112">CO</span><span class="sxs-lookup"><span data-stu-id="478e6-112">CO</span></span>                             |
|  <span data-ttu-id="478e6-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="478e6-113">Symbolic Name</span></span>  |              <span data-ttu-id="478e6-114">SSO_WARN_SSO_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="478e6-114">SSO_WARN_SSO_TICKETS_NOT_ALLOWED</span></span>              |
|  <span data-ttu-id="478e6-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="478e6-115">Message Text</span></span>   |        <span data-ttu-id="478e6-116">SSO 系统没有启用票证。</span><span class="sxs-lookup"><span data-stu-id="478e6-116">Tickets are not enabled for the SSO system.</span></span>         |

## <a name="explanation"></a><span data-ttu-id="478e6-117">解释</span><span class="sxs-lookup"><span data-stu-id="478e6-117">Explanation</span></span>  
 <span data-ttu-id="478e6-118">此警告事件表示 SSO 票证尚未启用。</span><span class="sxs-lookup"><span data-stu-id="478e6-118">This Warning event indicates that the use of SSO tickets is not enabled.</span></span> <span data-ttu-id="478e6-119">允许使用 SSO 票证是 SSO 系统的一个可选功能。</span><span class="sxs-lookup"><span data-stu-id="478e6-119">Allowing the use of SSO tickets is an optional feature of the SSO system.</span></span> <span data-ttu-id="478e6-120">您的 SSO 系统上尚未启用此功能。</span><span class="sxs-lookup"><span data-stu-id="478e6-120">This feature has not been enabled on your SSO system.</span></span>  

## <a name="user-action"></a><span data-ttu-id="478e6-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="478e6-121">User Action</span></span>  
 <span data-ttu-id="478e6-122">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="478e6-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="478e6-123">请与 SSO 管理员联系以启用 SSO 系统票证。</span><span class="sxs-lookup"><span data-stu-id="478e6-123">Contact your SSO Administrator to enable tickets for the SSO system.</span></span> <span data-ttu-id="478e6-124">可使用 SSO 管理工具（GUI 或命令行）完成此操作。</span><span class="sxs-lookup"><span data-stu-id="478e6-124">This can be done using the SSO administration tools (GUI or command line).</span></span>  

  <span data-ttu-id="478e6-125">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="478e6-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="478e6-126">如何配置 SSO 票证</span><span class="sxs-lookup"><span data-stu-id="478e6-126">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)  

- [<span data-ttu-id="478e6-127">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="478e6-127">Using SSO</span></span>](../core/using-sso.md)
