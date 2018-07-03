---
title: 单一登录： 事件 10577 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4563567a-9ee3-4c32-a202-c2521fd95b6a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 769576430df7ac3ce7ec0ec31a3e7b3eea03968c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003054"
---
# <a name="single-sign-on-event-10577"></a><span data-ttu-id="ef26c-102">单一登录： 事件 10577</span><span class="sxs-lookup"><span data-stu-id="ef26c-102">Single Sign-On: Event 10577</span></span>
## <a name="details"></a><span data-ttu-id="ef26c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ef26c-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ef26c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ef26c-104">Product Name</span></span>   |                                                                                                             <span data-ttu-id="ef26c-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ef26c-105">Enterprise Single Sign-On</span></span>                                                                                                             |
| <span data-ttu-id="ef26c-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ef26c-106">Product Version</span></span> |                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    <span data-ttu-id="ef26c-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ef26c-107">Event ID</span></span>     |                                                                                                                       <span data-ttu-id="ef26c-108">10577</span><span class="sxs-lookup"><span data-stu-id="ef26c-108">10577</span></span>                                                                                                                       |
|  <span data-ttu-id="ef26c-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ef26c-109">Event Source</span></span>   |                                                                                                                      <span data-ttu-id="ef26c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ef26c-110">ENTSSO</span></span>                                                                                                                       |
|    <span data-ttu-id="ef26c-111">组件</span><span class="sxs-lookup"><span data-stu-id="ef26c-111">Component</span></span>    |                                                                                                                        <span data-ttu-id="ef26c-112">N/A</span><span class="sxs-lookup"><span data-stu-id="ef26c-112">N/A</span></span>                                                                                                                        |
|  <span data-ttu-id="ef26c-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ef26c-113">Symbolic Name</span></span>  |                                                                                                          <span data-ttu-id="ef26c-114">SSO_INFO_CHANGED_SSO_AFF_ADMIN</span><span class="sxs-lookup"><span data-stu-id="ef26c-114">SSO_INFO_CHANGED_SSO_AFF_ADMIN</span></span>                                                                                                           |
|  <span data-ttu-id="ef26c-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ef26c-115">Message Text</span></span>   | <span data-ttu-id="ef26c-116">已更新 SSO 关联管理员帐户。%r</span><span class="sxs-lookup"><span data-stu-id="ef26c-116">Updated SSO Affiliate Administrators account.%r</span></span><br /><br /> <span data-ttu-id="ef26c-117">新的 SSO 关联管理员: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ef26c-117">New SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="ef26c-118">旧 SSO 关联管理员: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ef26c-118">Old SSO Affiliate Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="ef26c-119">跟踪 ID: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ef26c-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="ef26c-120">客户端计算机: %4 %r</span><span class="sxs-lookup"><span data-stu-id="ef26c-120">Client Computer: %4%r</span></span><br /><br /> <span data-ttu-id="ef26c-121">客户端用户： %5</span><span class="sxs-lookup"><span data-stu-id="ef26c-121">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ef26c-122">解释</span><span class="sxs-lookup"><span data-stu-id="ef26c-122">Explanation</span></span>  
 <span data-ttu-id="ef26c-123">这是信息性消息，可以用于跟踪 SSO 系统中发生的与安全有关的重要事件。</span><span class="sxs-lookup"><span data-stu-id="ef26c-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="ef26c-124">此消息表明 SSO 关联应用程序帐户已更新。</span><span class="sxs-lookup"><span data-stu-id="ef26c-124">This message states that the SSO Affiliate Administrators account has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ef26c-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="ef26c-125">User Action</span></span>  
 <span data-ttu-id="ef26c-126">不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="ef26c-126">No user action is required.</span></span>