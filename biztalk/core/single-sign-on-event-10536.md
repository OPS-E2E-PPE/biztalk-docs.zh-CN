---
title: 单一登录：Event 10536 | Microsoft Docs
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
ms.openlocfilehash: 9b66b9a37a92614b10849ac39bd8385d9e850efb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262244"
---
# <a name="single-sign-on-event-10536"></a><span data-ttu-id="cbb5a-102">单一登录：事件 10536</span><span class="sxs-lookup"><span data-stu-id="cbb5a-102">Single Sign-On: Event 10536</span></span>
## <a name="details"></a><span data-ttu-id="cbb5a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="cbb5a-103">Details</span></span>  

|                 |                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cbb5a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="cbb5a-104">Product Name</span></span>   |                                                                                     <span data-ttu-id="cbb5a-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="cbb5a-105">Enterprise Single Sign-On</span></span>                                                                                      |
| <span data-ttu-id="cbb5a-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="cbb5a-106">Product Version</span></span> |                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    <span data-ttu-id="cbb5a-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cbb5a-107">Event ID</span></span>     |                                                                                               <span data-ttu-id="cbb5a-108">10536</span><span class="sxs-lookup"><span data-stu-id="cbb5a-108">10536</span></span>                                                                                                |
|  <span data-ttu-id="cbb5a-109">事件源</span><span class="sxs-lookup"><span data-stu-id="cbb5a-109">Event Source</span></span>   |                                                                                               <span data-ttu-id="cbb5a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cbb5a-110">ENTSSO</span></span>                                                                                               |
|    <span data-ttu-id="cbb5a-111">组件</span><span class="sxs-lookup"><span data-stu-id="cbb5a-111">Component</span></span>    |                                                                                                 <span data-ttu-id="cbb5a-112">CO</span><span class="sxs-lookup"><span data-stu-id="cbb5a-112">CO</span></span>                                                                                                 |
|  <span data-ttu-id="cbb5a-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="cbb5a-113">Symbolic Name</span></span>  |                                                                                         <span data-ttu-id="cbb5a-114">SSO_WARN_API_AUDIT</span><span class="sxs-lookup"><span data-stu-id="cbb5a-114">SSO_WARN_API_AUDIT</span></span>                                                                                         |
|  <span data-ttu-id="cbb5a-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="cbb5a-115">Message Text</span></span>   | <span data-ttu-id="cbb5a-116">SSO AUDIT %r</span><span class="sxs-lookup"><span data-stu-id="cbb5a-116">SSO AUDIT%r</span></span><br /><br /> <span data-ttu-id="cbb5a-117">函数: %1 %r</span><span class="sxs-lookup"><span data-stu-id="cbb5a-117">Function: %1%r</span></span><br /><br /> <span data-ttu-id="cbb5a-118">跟踪 ID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="cbb5a-118">Tracking ID: %2%r</span></span><br /><br /> <span data-ttu-id="cbb5a-119">客户端计算机: %3 %r</span><span class="sxs-lookup"><span data-stu-id="cbb5a-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="cbb5a-120">客户端用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="cbb5a-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="cbb5a-121">应用程序名称: %5 %r</span><span class="sxs-lookup"><span data-stu-id="cbb5a-121">Application Name: %5%r</span></span><br /><br /> <span data-ttu-id="cbb5a-122">错误代码： %6</span><span class="sxs-lookup"><span data-stu-id="cbb5a-122">Error Code: %6</span></span> |

## <a name="explanation"></a><span data-ttu-id="cbb5a-123">解释</span><span class="sxs-lookup"><span data-stu-id="cbb5a-123">Explanation</span></span>  
 <span data-ttu-id="cbb5a-124">此警告审核事件指示发生满足用户定义的审核级别的事件。</span><span class="sxs-lookup"><span data-stu-id="cbb5a-124">This Warning Audit event indicates that an event that meets the user defined audit level has occurred.</span></span> <span data-ttu-id="cbb5a-125">此事件消息包括：</span><span class="sxs-lookup"><span data-stu-id="cbb5a-125">This event message includes:</span></span>  

 <span data-ttu-id="cbb5a-126">**函数：** 正在执行的函数</span><span class="sxs-lookup"><span data-stu-id="cbb5a-126">**Function:** Function being performed</span></span>  

 <span data-ttu-id="cbb5a-127">**跟踪 ID:** 当首次调用 SSO API 时，生成的唯一 GUID。</span><span class="sxs-lookup"><span data-stu-id="cbb5a-127">**Tracking ID:** Unique GUID generated when an SSO API is first called.</span></span>  

 <span data-ttu-id="cbb5a-128">**客户端计算机：** 生成函数的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="cbb5a-128">**Client Computer:** Client computer where the function originated.</span></span>  

 <span data-ttu-id="cbb5a-129">**客户端用户：** 调用该函数的用户帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="cbb5a-129">**Client User:** The name of the user account that invoked the function.</span></span>  

 <span data-ttu-id="cbb5a-130">**应用程序名称：** 名称的 SSO 关联应用程序与此函数相关联。</span><span class="sxs-lookup"><span data-stu-id="cbb5a-130">**Application Name:** Name of the SSO affiliate application associated with this function.</span></span>  

 <span data-ttu-id="cbb5a-131">**错误代码：** 唯一的错误标识符。</span><span class="sxs-lookup"><span data-stu-id="cbb5a-131">**Error Code:** Unique error identifier.</span></span>  

 <span data-ttu-id="cbb5a-132">此类型的事件用于在开发期间诊断问题、 故障排除，或正在运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cbb5a-132">This type of event is used for diagnosing problems during development, troubleshooting, or running of an application.</span></span> <span data-ttu-id="cbb5a-133">提供的信息可以用于确定正在进行的 SSO API 调用。</span><span class="sxs-lookup"><span data-stu-id="cbb5a-133">Information provided can be used to determine the SSO API call being made.</span></span>  

 <span data-ttu-id="cbb5a-134">可以将审核级别设置为 0/1/2/3 – 0 意味着"无"、 1 意味着"低"显示仅限错误、 2 意味着"medium"显示错误和警告，和 3 意味着"高"显示所有审核消息。</span><span class="sxs-lookup"><span data-stu-id="cbb5a-134">The audit level can be set to 0/1/2/3 – 0 means “none”, 1 means “low” displays errors only, 2 means “medium” displays errors and warnings, and 3 means “high” displays all audit messages.</span></span>  

## <a name="user-action"></a><span data-ttu-id="cbb5a-135">用户操作</span><span class="sxs-lookup"><span data-stu-id="cbb5a-135">User Action</span></span>  

- <span data-ttu-id="cbb5a-136">检查关联的事件消息的事件日志。</span><span class="sxs-lookup"><span data-stu-id="cbb5a-136">Check the event log for associated event messages.</span></span>  

  <span data-ttu-id="cbb5a-137">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="cbb5a-137">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="cbb5a-138">如何审核 SSO</span><span class="sxs-lookup"><span data-stu-id="cbb5a-138">How to Audit SSO</span></span>](../core/how-to-audit-sso.md)  

- [<span data-ttu-id="cbb5a-139">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="cbb5a-139">Using SSO</span></span>](../core/using-sso.md)
