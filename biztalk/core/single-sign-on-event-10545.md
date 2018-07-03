---
title: 单一登录： 事件 10545 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 268cb7be-b191-4335-a4cc-7c15d879507c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a21543359b9a0d59aba3071874b6b01210118a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969126"
---
# <a name="single-sign-on-event-10545"></a><span data-ttu-id="1ccab-102">单一登录： 事件 10545</span><span class="sxs-lookup"><span data-stu-id="1ccab-102">Single Sign-On: Event 10545</span></span>
## <a name="details"></a><span data-ttu-id="1ccab-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1ccab-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="1ccab-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1ccab-104">Product Name</span></span>   |                 <span data-ttu-id="1ccab-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="1ccab-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="1ccab-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="1ccab-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="1ccab-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1ccab-107">Event ID</span></span>     |                           <span data-ttu-id="1ccab-108">10545</span><span class="sxs-lookup"><span data-stu-id="1ccab-108">10545</span></span>                            |
|  <span data-ttu-id="1ccab-109">事件源</span><span class="sxs-lookup"><span data-stu-id="1ccab-109">Event Source</span></span>   |                           <span data-ttu-id="1ccab-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1ccab-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="1ccab-111">组件</span><span class="sxs-lookup"><span data-stu-id="1ccab-111">Component</span></span>    |                             <span data-ttu-id="1ccab-112">CO</span><span class="sxs-lookup"><span data-stu-id="1ccab-112">CO</span></span>                             |
|  <span data-ttu-id="1ccab-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="1ccab-113">Symbolic Name</span></span>  |             <span data-ttu-id="1ccab-114">SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="1ccab-114">SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED</span></span>             |
|  <span data-ttu-id="1ccab-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="1ccab-115">Message Text</span></span>   |        <span data-ttu-id="1ccab-116">SSO 系统没有启用票证。</span><span class="sxs-lookup"><span data-stu-id="1ccab-116">Tickets are not enabled for the SSO system.</span></span>         |

## <a name="explanation"></a><span data-ttu-id="1ccab-117">解释</span><span class="sxs-lookup"><span data-stu-id="1ccab-117">Explanation</span></span>  
 <span data-ttu-id="1ccab-118">此警告事件表示没有为 SSO 系统启动票证。</span><span class="sxs-lookup"><span data-stu-id="1ccab-118">This Warning event indicates that tickets are not enabled for the SSO System.</span></span> <span data-ttu-id="1ccab-119">如果在系统级别上禁用了票证功能，则也不能在关联应用程序级别上使用此功能。</span><span class="sxs-lookup"><span data-stu-id="1ccab-119">If ticketing is disabled at the system level, ticketing cannot be used at the Affiliate Application level either.</span></span> <span data-ttu-id="1ccab-120">就可以启用在系统级别票证和关联应用程序级别禁用它。</span><span class="sxs-lookup"><span data-stu-id="1ccab-120">It is possible to enable tickets at the system level and disable it at the Affiliate Application level.</span></span>  

## <a name="user-action"></a><span data-ttu-id="1ccab-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="1ccab-121">User Action</span></span>  
 <span data-ttu-id="1ccab-122">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1ccab-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="1ccab-123">启用 SSO 系统级别的票证。</span><span class="sxs-lookup"><span data-stu-id="1ccab-123">Enable tickets at the SSO System level.</span></span>  

  <span data-ttu-id="1ccab-124">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="1ccab-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="1ccab-125">SSO 票证</span><span class="sxs-lookup"><span data-stu-id="1ccab-125">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="1ccab-126">如何配置 SSO 票证</span><span class="sxs-lookup"><span data-stu-id="1ccab-126">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)
