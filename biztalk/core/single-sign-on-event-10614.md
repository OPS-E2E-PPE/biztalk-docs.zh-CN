---
title: 单一登录： 事件 10614 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1f9cd21-3f4b-446f-a4c7-15266973adf1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba6cae7c64b5eeff339499f279aa85917211cbba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968166"
---
# <a name="single-sign-on-event-10614"></a><span data-ttu-id="e5a83-102">单一登录： 事件 10614</span><span class="sxs-lookup"><span data-stu-id="e5a83-102">Single Sign-On: Event 10614</span></span>
## <a name="details"></a><span data-ttu-id="e5a83-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e5a83-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e5a83-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e5a83-104">Product Name</span></span>   |                                                                                                        <span data-ttu-id="e5a83-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e5a83-105">Enterprise Single Sign-On</span></span>                                                                                                        |
| <span data-ttu-id="e5a83-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e5a83-106">Product Version</span></span> |                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                        |
|    <span data-ttu-id="e5a83-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e5a83-107">Event ID</span></span>     |                                                                                                                  <span data-ttu-id="e5a83-108">10614</span><span class="sxs-lookup"><span data-stu-id="e5a83-108">10614</span></span>                                                                                                                  |
|  <span data-ttu-id="e5a83-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e5a83-109">Event Source</span></span>   |                                                                                                                 <span data-ttu-id="e5a83-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e5a83-110">ENTSSO</span></span>                                                                                                                  |
|    <span data-ttu-id="e5a83-111">组件</span><span class="sxs-lookup"><span data-stu-id="e5a83-111">Component</span></span>    |                                                                                                                   <span data-ttu-id="e5a83-112">N/A</span><span class="sxs-lookup"><span data-stu-id="e5a83-112">N/A</span></span>                                                                                                                   |
|  <span data-ttu-id="e5a83-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e5a83-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="e5a83-114">SSO_WARN_INVALID_TICKET_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e5a83-114">SSO_WARN_INVALID_TICKET_TIMEOUT</span></span>                                                                                                     |
|  <span data-ttu-id="e5a83-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e5a83-115">Message Text</span></span>   | <span data-ttu-id="e5a83-116">票证超时值对全局信息更新无效。%r</span><span class="sxs-lookup"><span data-stu-id="e5a83-116">The ticket time-out value is not valid for global info update.%r</span></span><br /><br /> <span data-ttu-id="e5a83-117">票证超时： %1 分钟 %r</span><span class="sxs-lookup"><span data-stu-id="e5a83-117">Ticket time-out: %1 minutes%r</span></span><br /><br /> <span data-ttu-id="e5a83-118">最小票证超时： 1 分钟 %r</span><span class="sxs-lookup"><span data-stu-id="e5a83-118">Minimum ticket time-out: 1 minute%r</span></span><br /><br /> <span data-ttu-id="e5a83-119">最大票证超时： %2 分钟 %r</span><span class="sxs-lookup"><span data-stu-id="e5a83-119">Maximum ticket time-out: %2 minutes%r</span></span><br /><br /> <span data-ttu-id="e5a83-120">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="e5a83-120">Error Code: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e5a83-121">解释</span><span class="sxs-lookup"><span data-stu-id="e5a83-121">Explanation</span></span>  
 <span data-ttu-id="e5a83-122">指定的票证超时值无效。</span><span class="sxs-lookup"><span data-stu-id="e5a83-122">The ticket time-out value specified is not valid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e5a83-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="e5a83-123">User Action</span></span>  
 <span data-ttu-id="e5a83-124">使用警告消息中提供的信息修正此值。</span><span class="sxs-lookup"><span data-stu-id="e5a83-124">Use the information supplied in the warning message to fix the value.</span></span>