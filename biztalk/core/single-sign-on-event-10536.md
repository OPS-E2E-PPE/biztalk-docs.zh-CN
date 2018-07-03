---
title: 单一登录： 事件 10536 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d493a45b-c4ed-40fc-8803-b3ca12f9795b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49687739fced504c9dccc06969c9eb3e10d9aae4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016127"
---
# <a name="single-sign-on-event-10536"></a><span data-ttu-id="fef76-102">单一登录： 事件 10536</span><span class="sxs-lookup"><span data-stu-id="fef76-102">Single Sign-On: Event 10536</span></span>
## <a name="details"></a><span data-ttu-id="fef76-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="fef76-103">Details</span></span>  

|                 |                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fef76-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="fef76-104">Product Name</span></span>   |                                                                                     <span data-ttu-id="fef76-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="fef76-105">Enterprise Single Sign-On</span></span>                                                                                      |
| <span data-ttu-id="fef76-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="fef76-106">Product Version</span></span> |                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    <span data-ttu-id="fef76-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fef76-107">Event ID</span></span>     |                                                                                               <span data-ttu-id="fef76-108">10536</span><span class="sxs-lookup"><span data-stu-id="fef76-108">10536</span></span>                                                                                                |
|  <span data-ttu-id="fef76-109">事件源</span><span class="sxs-lookup"><span data-stu-id="fef76-109">Event Source</span></span>   |                                                                                               <span data-ttu-id="fef76-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fef76-110">ENTSSO</span></span>                                                                                               |
|    <span data-ttu-id="fef76-111">组件</span><span class="sxs-lookup"><span data-stu-id="fef76-111">Component</span></span>    |                                                                                                 <span data-ttu-id="fef76-112">CO</span><span class="sxs-lookup"><span data-stu-id="fef76-112">CO</span></span>                                                                                                 |
|  <span data-ttu-id="fef76-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="fef76-113">Symbolic Name</span></span>  |                                                                                         <span data-ttu-id="fef76-114">SSO_WARN_API_AUDIT</span><span class="sxs-lookup"><span data-stu-id="fef76-114">SSO_WARN_API_AUDIT</span></span>                                                                                         |
|  <span data-ttu-id="fef76-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="fef76-115">Message Text</span></span>   | <span data-ttu-id="fef76-116">SSO 审核%r</span><span class="sxs-lookup"><span data-stu-id="fef76-116">SSO AUDIT%r</span></span><br /><br /> <span data-ttu-id="fef76-117">函数: %1 %r</span><span class="sxs-lookup"><span data-stu-id="fef76-117">Function: %1%r</span></span><br /><br /> <span data-ttu-id="fef76-118">跟踪 ID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="fef76-118">Tracking ID: %2%r</span></span><br /><br /> <span data-ttu-id="fef76-119">客户端计算机: %3 %r</span><span class="sxs-lookup"><span data-stu-id="fef76-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="fef76-120">客户端用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="fef76-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="fef76-121">应用程序名称: %5 %r</span><span class="sxs-lookup"><span data-stu-id="fef76-121">Application Name: %5%r</span></span><br /><br /> <span data-ttu-id="fef76-122">错误代码： %6</span><span class="sxs-lookup"><span data-stu-id="fef76-122">Error Code: %6</span></span> |

## <a name="explanation"></a><span data-ttu-id="fef76-123">解释</span><span class="sxs-lookup"><span data-stu-id="fef76-123">Explanation</span></span>  
 <span data-ttu-id="fef76-124">此警告审核事件表示，满足用户定义的审核级别的事件已经发生。</span><span class="sxs-lookup"><span data-stu-id="fef76-124">This Warning Audit event indicates that an event that meets the user defined audit level has occurred.</span></span> <span data-ttu-id="fef76-125">此事件消息包括：</span><span class="sxs-lookup"><span data-stu-id="fef76-125">This event message includes:</span></span>  

 <span data-ttu-id="fef76-126">**函数：** 正在执行的函数</span><span class="sxs-lookup"><span data-stu-id="fef76-126">**Function:** Function being performed</span></span>  

 <span data-ttu-id="fef76-127">**跟踪 ID:** 唯一 GUID 生成第一个 SSO API 时调用。</span><span class="sxs-lookup"><span data-stu-id="fef76-127">**Tracking ID:** Unique GUID generated when an SSO API is first called.</span></span>  

 <span data-ttu-id="fef76-128">**客户端计算机：** 生成函数的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="fef76-128">**Client Computer:** Client computer where the function originated.</span></span>  

 <span data-ttu-id="fef76-129">**客户端用户：** 调用该函数的用户帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="fef76-129">**Client User:** The name of the user account that invoked the function.</span></span>  

 <span data-ttu-id="fef76-130">**应用程序名称：** 名称的 SSO 关联应用程序与此函数相关联。</span><span class="sxs-lookup"><span data-stu-id="fef76-130">**Application Name:** Name of the SSO affiliate application associated with this function.</span></span>  

 <span data-ttu-id="fef76-131">**错误代码：** 唯一错误标识符。</span><span class="sxs-lookup"><span data-stu-id="fef76-131">**Error Code:** Unique error identifier.</span></span>  

 <span data-ttu-id="fef76-132">此类型事件用于诊断应用程序开发、疑难解答或运行过程中的问题。</span><span class="sxs-lookup"><span data-stu-id="fef76-132">This type of event is used for diagnosing problems during development, troubleshooting, or running of an application.</span></span> <span data-ttu-id="fef76-133">提供的信息可用于确定正在调用的 SSO API。</span><span class="sxs-lookup"><span data-stu-id="fef76-133">Information provided can be used to determine the SSO API call being made.</span></span>  

 <span data-ttu-id="fef76-134">审核级别可以设置为 0/1/2/3 – 0 意味着“无”、1 意味着“低”（只显示错误）、2 意味着“中”（显示错误和警告），以及 3 意味着“高”（显示所有的审核消息）。</span><span class="sxs-lookup"><span data-stu-id="fef76-134">The audit level can be set to 0/1/2/3 – 0 means “none”, 1 means “low” displays errors only, 2 means “medium” displays errors and warnings, and 3 means “high” displays all audit messages.</span></span>  

## <a name="user-action"></a><span data-ttu-id="fef76-135">用户操作</span><span class="sxs-lookup"><span data-stu-id="fef76-135">User Action</span></span>  

- <span data-ttu-id="fef76-136">检查相关事件消息的事件日志。</span><span class="sxs-lookup"><span data-stu-id="fef76-136">Check the event log for associated event messages.</span></span>  

  <span data-ttu-id="fef76-137">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="fef76-137">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="fef76-138">如何审核 SSO</span><span class="sxs-lookup"><span data-stu-id="fef76-138">How to Audit SSO</span></span>](../core/how-to-audit-sso.md)  

- [<span data-ttu-id="fef76-139">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="fef76-139">Using SSO</span></span>](../core/using-sso.md)
