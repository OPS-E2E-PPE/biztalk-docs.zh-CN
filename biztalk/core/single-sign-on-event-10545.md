---
title: 单一登录：Event 10545 | Microsoft Docs
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
ms.openlocfilehash: 6695a46f2116045e5aec58514ac110c6a2948f66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243487"
---
# <a name="single-sign-on-event-10545"></a><span data-ttu-id="215d9-102">单一登录：事件 10545</span><span class="sxs-lookup"><span data-stu-id="215d9-102">Single Sign-On: Event 10545</span></span>
## <a name="details"></a><span data-ttu-id="215d9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="215d9-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="215d9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="215d9-104">Product Name</span></span>   |                 <span data-ttu-id="215d9-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="215d9-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="215d9-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="215d9-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="215d9-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="215d9-107">Event ID</span></span>     |                           <span data-ttu-id="215d9-108">10545</span><span class="sxs-lookup"><span data-stu-id="215d9-108">10545</span></span>                            |
|  <span data-ttu-id="215d9-109">事件源</span><span class="sxs-lookup"><span data-stu-id="215d9-109">Event Source</span></span>   |                           <span data-ttu-id="215d9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="215d9-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="215d9-111">组件</span><span class="sxs-lookup"><span data-stu-id="215d9-111">Component</span></span>    |                             <span data-ttu-id="215d9-112">CO</span><span class="sxs-lookup"><span data-stu-id="215d9-112">CO</span></span>                             |
|  <span data-ttu-id="215d9-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="215d9-113">Symbolic Name</span></span>  |             <span data-ttu-id="215d9-114">SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="215d9-114">SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED</span></span>             |
|  <span data-ttu-id="215d9-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="215d9-115">Message Text</span></span>   |        <span data-ttu-id="215d9-116">SSO 系统未启用票证。</span><span class="sxs-lookup"><span data-stu-id="215d9-116">Tickets are not enabled for the SSO system.</span></span>         |

## <a name="explanation"></a><span data-ttu-id="215d9-117">解释</span><span class="sxs-lookup"><span data-stu-id="215d9-117">Explanation</span></span>  
 <span data-ttu-id="215d9-118">此警告事件表示 SSO 系统未启用票证。</span><span class="sxs-lookup"><span data-stu-id="215d9-118">This Warning event indicates that tickets are not enabled for the SSO System.</span></span> <span data-ttu-id="215d9-119">如果在系统级别上禁用了票证，票证不能在关联应用程序级别使用或者。</span><span class="sxs-lookup"><span data-stu-id="215d9-119">If ticketing is disabled at the system level, ticketing cannot be used at the Affiliate Application level either.</span></span> <span data-ttu-id="215d9-120">就可以启用在系统级别票证和关联应用程序级别禁用它。</span><span class="sxs-lookup"><span data-stu-id="215d9-120">It is possible to enable tickets at the system level and disable it at the Affiliate Application level.</span></span>  

## <a name="user-action"></a><span data-ttu-id="215d9-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="215d9-121">User Action</span></span>  
 <span data-ttu-id="215d9-122">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="215d9-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="215d9-123">启用 SSO 系统级别票证。</span><span class="sxs-lookup"><span data-stu-id="215d9-123">Enable tickets at the SSO System level.</span></span>  

  <span data-ttu-id="215d9-124">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="215d9-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="215d9-125">SSO 票证</span><span class="sxs-lookup"><span data-stu-id="215d9-125">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="215d9-126">如何配置 SSO 票证</span><span class="sxs-lookup"><span data-stu-id="215d9-126">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)
