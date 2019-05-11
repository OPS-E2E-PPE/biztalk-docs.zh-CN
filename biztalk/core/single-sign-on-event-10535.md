---
title: 单一登录：Event 10535 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b570b0b-5c45-4be3-80c9-a2c50601b677
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4c6fc30ad5b0953ddecaad3266dec787e210429
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262347"
---
# <a name="single-sign-on-event-10535"></a><span data-ttu-id="77e76-102">单一登录：事件 10535</span><span class="sxs-lookup"><span data-stu-id="77e76-102">Single Sign-On: Event 10535</span></span>
## <a name="details"></a><span data-ttu-id="77e76-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="77e76-103">Details</span></span>  

|                 |                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="77e76-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="77e76-104">Product Name</span></span>   |                                                                       <span data-ttu-id="77e76-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="77e76-105">Enterprise Single Sign-On</span></span>                                                                       |
| <span data-ttu-id="77e76-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="77e76-106">Product Version</span></span> |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    <span data-ttu-id="77e76-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="77e76-107">Event ID</span></span>     |                                                                                 <span data-ttu-id="77e76-108">10535</span><span class="sxs-lookup"><span data-stu-id="77e76-108">10535</span></span>                                                                                 |
|  <span data-ttu-id="77e76-109">事件源</span><span class="sxs-lookup"><span data-stu-id="77e76-109">Event Source</span></span>   |                                                                                <span data-ttu-id="77e76-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="77e76-110">ENTSSO</span></span>                                                                                 |
|    <span data-ttu-id="77e76-111">组件</span><span class="sxs-lookup"><span data-stu-id="77e76-111">Component</span></span>    |                                                                                  <span data-ttu-id="77e76-112">CO</span><span class="sxs-lookup"><span data-stu-id="77e76-112">CO</span></span>                                                                                   |
|  <span data-ttu-id="77e76-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="77e76-113">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="77e76-114">SSO_INFO_API_AUDIT</span><span class="sxs-lookup"><span data-stu-id="77e76-114">SSO_INFO_API_AUDIT</span></span>                                                                           |
|  <span data-ttu-id="77e76-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="77e76-115">Message Text</span></span>   | <span data-ttu-id="77e76-116">SSO AUDIT %r</span><span class="sxs-lookup"><span data-stu-id="77e76-116">SSO AUDIT%r</span></span><br /><br /> <span data-ttu-id="77e76-117">函数: %1 %r</span><span class="sxs-lookup"><span data-stu-id="77e76-117">Function: %1%r</span></span><br /><br /> <span data-ttu-id="77e76-118">跟踪 ID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="77e76-118">Tracking ID: %2%r</span></span><br /><br /> <span data-ttu-id="77e76-119">客户端计算机: %3 %r</span><span class="sxs-lookup"><span data-stu-id="77e76-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="77e76-120">客户端用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="77e76-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="77e76-121">应用程序名称： %5</span><span class="sxs-lookup"><span data-stu-id="77e76-121">Application Name: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="77e76-122">解释</span><span class="sxs-lookup"><span data-stu-id="77e76-122">Explanation</span></span>  
 <span data-ttu-id="77e76-123">此信息审核事件指示发生满足用户定义的审核级别的事件。</span><span class="sxs-lookup"><span data-stu-id="77e76-123">This Information Audit event indicates that an event that meets the user defined audit level has occurred.</span></span> <span data-ttu-id="77e76-124">此事件消息包括：</span><span class="sxs-lookup"><span data-stu-id="77e76-124">This event message includes:</span></span>  

 <span data-ttu-id="77e76-125">**函数：** 正在执行的函数</span><span class="sxs-lookup"><span data-stu-id="77e76-125">**Function:** Function being performed</span></span>  

 <span data-ttu-id="77e76-126">**跟踪 ID:** 当首次调用 SSO API 时，生成的唯一 GUID。</span><span class="sxs-lookup"><span data-stu-id="77e76-126">**Tracking ID:** Unique GUID generated when an SSO API is first called.</span></span>  

 <span data-ttu-id="77e76-127">**客户端计算机：** 生成函数的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="77e76-127">**Client Computer:** Client computer where the function originated.</span></span>  

 <span data-ttu-id="77e76-128">**客户端用户：** 调用该函数的用户帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="77e76-128">**Client User:** The name of the user account that invoked the function.</span></span>  

 <span data-ttu-id="77e76-129">**应用程序名称：** 名称的 SSO 关联应用程序与此函数相关联。</span><span class="sxs-lookup"><span data-stu-id="77e76-129">**Application Name:** Name of the SSO affiliate application associated with this function.</span></span>  

 <span data-ttu-id="77e76-130">此类型的事件用于在开发期间诊断问题、 故障排除，或正在运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="77e76-130">This type of event is used for diagnosing problems during development, troubleshooting, or running of an application.</span></span> <span data-ttu-id="77e76-131">提供的信息可以用于确定正在进行的 SSO API 调用。</span><span class="sxs-lookup"><span data-stu-id="77e76-131">Information provided can be used to determine the SSO API call being made.</span></span>  

 <span data-ttu-id="77e76-132">可以将审核级别设置为 0/1/2/3 – 0 意味着"无"、 1 意味着"低"显示仅限错误、 2 意味着"medium"显示错误和警告，和 3 意味着"高"显示所有审核消息。</span><span class="sxs-lookup"><span data-stu-id="77e76-132">The audit level can be set to 0/1/2/3 – 0 means “none”, 1 means “low” displays errors only, 2 means “medium” displays errors and warnings, and 3 means “high” displays all audit messages.</span></span>  

## <a name="user-action"></a><span data-ttu-id="77e76-133">用户操作</span><span class="sxs-lookup"><span data-stu-id="77e76-133">User Action</span></span>  

- <span data-ttu-id="77e76-134">检查关联的事件消息的事件日志。</span><span class="sxs-lookup"><span data-stu-id="77e76-134">Check the event log for associated event messages.</span></span>  

  <span data-ttu-id="77e76-135">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="77e76-135">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="77e76-136">如何审核 SSO</span><span class="sxs-lookup"><span data-stu-id="77e76-136">How to Audit SSO</span></span>](../core/how-to-audit-sso.md)  

- [<span data-ttu-id="77e76-137">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="77e76-137">Using SSO</span></span>](../core/using-sso.md)
