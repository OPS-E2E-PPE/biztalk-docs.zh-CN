---
title: 单一登录：Event 10614 | Microsoft Docs
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
ms.openlocfilehash: a5fc2758327087d0b312de16b6f7c8ebc6b5bb6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397697"
---
# <a name="single-sign-on-event-10614"></a><span data-ttu-id="6a9b1-102">单一登录：事件 10614</span><span class="sxs-lookup"><span data-stu-id="6a9b1-102">Single Sign-On: Event 10614</span></span>
## <a name="details"></a><span data-ttu-id="6a9b1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="6a9b1-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6a9b1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="6a9b1-104">Product Name</span></span>   |                                                                                                        <span data-ttu-id="6a9b1-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="6a9b1-105">Enterprise Single Sign-On</span></span>                                                                                                        |
| <span data-ttu-id="6a9b1-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="6a9b1-106">Product Version</span></span> |                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                        |
|    <span data-ttu-id="6a9b1-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6a9b1-107">Event ID</span></span>     |                                                                                                                  <span data-ttu-id="6a9b1-108">10614</span><span class="sxs-lookup"><span data-stu-id="6a9b1-108">10614</span></span>                                                                                                                  |
|  <span data-ttu-id="6a9b1-109">事件源</span><span class="sxs-lookup"><span data-stu-id="6a9b1-109">Event Source</span></span>   |                                                                                                                 <span data-ttu-id="6a9b1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6a9b1-110">ENTSSO</span></span>                                                                                                                  |
|    <span data-ttu-id="6a9b1-111">组件</span><span class="sxs-lookup"><span data-stu-id="6a9b1-111">Component</span></span>    |                                                                                                                   <span data-ttu-id="6a9b1-112">不可用</span><span class="sxs-lookup"><span data-stu-id="6a9b1-112">N/A</span></span>                                                                                                                   |
|  <span data-ttu-id="6a9b1-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="6a9b1-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="6a9b1-114">SSO_WARN_INVALID_TICKET_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6a9b1-114">SSO_WARN_INVALID_TICKET_TIMEOUT</span></span>                                                                                                     |
|  <span data-ttu-id="6a9b1-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="6a9b1-115">Message Text</span></span>   | <span data-ttu-id="6a9b1-116">票证超时值不能用于全局信息 update.%r</span><span class="sxs-lookup"><span data-stu-id="6a9b1-116">The ticket time-out value is not valid for global info update.%r</span></span><br /><br /> <span data-ttu-id="6a9b1-117">票证超时： %1 分钟 %r</span><span class="sxs-lookup"><span data-stu-id="6a9b1-117">Ticket time-out: %1 minutes%r</span></span><br /><br /> <span data-ttu-id="6a9b1-118">最小票证超时：1 分钟 %r</span><span class="sxs-lookup"><span data-stu-id="6a9b1-118">Minimum ticket time-out: 1 minute%r</span></span><br /><br /> <span data-ttu-id="6a9b1-119">最大票证超时： %2 分钟 %r</span><span class="sxs-lookup"><span data-stu-id="6a9b1-119">Maximum ticket time-out: %2 minutes%r</span></span><br /><br /> <span data-ttu-id="6a9b1-120">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="6a9b1-120">Error Code: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="6a9b1-121">解释</span><span class="sxs-lookup"><span data-stu-id="6a9b1-121">Explanation</span></span>  
 <span data-ttu-id="6a9b1-122">指定的票证超时值无效。</span><span class="sxs-lookup"><span data-stu-id="6a9b1-122">The ticket time-out value specified is not valid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6a9b1-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="6a9b1-123">User Action</span></span>  
 <span data-ttu-id="6a9b1-124">使用警告消息中提供的信息修正此值。</span><span class="sxs-lookup"><span data-stu-id="6a9b1-124">Use the information supplied in the warning message to fix the value.</span></span>