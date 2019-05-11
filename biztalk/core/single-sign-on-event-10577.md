---
title: 单一登录：Event 10577 | Microsoft Docs
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
ms.openlocfilehash: 10d381ccbeb1809fbd3a668bd8d1e38264a3a5fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303389"
---
# <a name="single-sign-on-event-10577"></a><span data-ttu-id="f6cdf-102">单一登录：事件 10577</span><span class="sxs-lookup"><span data-stu-id="f6cdf-102">Single Sign-On: Event 10577</span></span>
## <a name="details"></a><span data-ttu-id="f6cdf-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f6cdf-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f6cdf-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f6cdf-104">Product Name</span></span>   |                                                                                                             <span data-ttu-id="f6cdf-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f6cdf-105">Enterprise Single Sign-On</span></span>                                                                                                             |
| <span data-ttu-id="f6cdf-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f6cdf-106">Product Version</span></span> |                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    <span data-ttu-id="f6cdf-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f6cdf-107">Event ID</span></span>     |                                                                                                                       <span data-ttu-id="f6cdf-108">10577</span><span class="sxs-lookup"><span data-stu-id="f6cdf-108">10577</span></span>                                                                                                                       |
|  <span data-ttu-id="f6cdf-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f6cdf-109">Event Source</span></span>   |                                                                                                                      <span data-ttu-id="f6cdf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f6cdf-110">ENTSSO</span></span>                                                                                                                       |
|    <span data-ttu-id="f6cdf-111">组件</span><span class="sxs-lookup"><span data-stu-id="f6cdf-111">Component</span></span>    |                                                                                                                        <span data-ttu-id="f6cdf-112">不可用</span><span class="sxs-lookup"><span data-stu-id="f6cdf-112">N/A</span></span>                                                                                                                        |
|  <span data-ttu-id="f6cdf-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f6cdf-113">Symbolic Name</span></span>  |                                                                                                          <span data-ttu-id="f6cdf-114">SSO_INFO_CHANGED_SSO_AFF_ADMIN</span><span class="sxs-lookup"><span data-stu-id="f6cdf-114">SSO_INFO_CHANGED_SSO_AFF_ADMIN</span></span>                                                                                                           |
|  <span data-ttu-id="f6cdf-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f6cdf-115">Message Text</span></span>   | <span data-ttu-id="f6cdf-116">已更新的 SSO Affiliate Administrators account.%r</span><span class="sxs-lookup"><span data-stu-id="f6cdf-116">Updated SSO Affiliate Administrators account.%r</span></span><br /><br /> <span data-ttu-id="f6cdf-117">新的 SSO 关联管理员: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f6cdf-117">New SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="f6cdf-118">旧 SSO 关联管理员: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f6cdf-118">Old SSO Affiliate Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="f6cdf-119">跟踪 ID: %3 %r</span><span class="sxs-lookup"><span data-stu-id="f6cdf-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="f6cdf-120">客户端计算机: %4 %r</span><span class="sxs-lookup"><span data-stu-id="f6cdf-120">Client Computer: %4%r</span></span><br /><br /> <span data-ttu-id="f6cdf-121">客户端用户： %5</span><span class="sxs-lookup"><span data-stu-id="f6cdf-121">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f6cdf-122">解释</span><span class="sxs-lookup"><span data-stu-id="f6cdf-122">Explanation</span></span>  
 <span data-ttu-id="f6cdf-123">这是一条信息性消息，也可用于跟踪 SSO 系统中的发生的与安全相关的重要事件。</span><span class="sxs-lookup"><span data-stu-id="f6cdf-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="f6cdf-124">此消息表明已更新 SSO 关联管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="f6cdf-124">This message states that the SSO Affiliate Administrators account has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f6cdf-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="f6cdf-125">User Action</span></span>  
 <span data-ttu-id="f6cdf-126">不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="f6cdf-126">No user action is required.</span></span>