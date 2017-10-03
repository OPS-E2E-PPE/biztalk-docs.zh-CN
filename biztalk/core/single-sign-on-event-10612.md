---
title: "单一登录： 事件 10612 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9d9e6f5-06b8-4989-a0dc-6e2e5980443b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a85361bf9946efc283683d41ed0d08187e4d8754
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10612"></a><span data-ttu-id="3560b-102">单一登录： 事件 10612</span><span class="sxs-lookup"><span data-stu-id="3560b-102">Single Sign-On: Event 10612</span></span>
## <a name="details"></a><span data-ttu-id="3560b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3560b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3560b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3560b-104">Product Name</span></span>|<span data-ttu-id="3560b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="3560b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="3560b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="3560b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="3560b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3560b-107">Event ID</span></span>|<span data-ttu-id="3560b-108">10612</span><span class="sxs-lookup"><span data-stu-id="3560b-108">10612</span></span>|  
|<span data-ttu-id="3560b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="3560b-109">Event Source</span></span>|<span data-ttu-id="3560b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3560b-110">ENTSSO</span></span>|  
|<span data-ttu-id="3560b-111">组件</span><span class="sxs-lookup"><span data-stu-id="3560b-111">Component</span></span>|<span data-ttu-id="3560b-112">N/A</span><span class="sxs-lookup"><span data-stu-id="3560b-112">N/A</span></span>|  
|<span data-ttu-id="3560b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="3560b-113">Symbolic Name</span></span>|<span data-ttu-id="3560b-114">SSO_WARN_TRANSACTION_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3560b-114">SSO_WARN_TRANSACTION_TIMEOUT</span></span>|  
|<span data-ttu-id="3560b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="3560b-115">Message Text</span></span>|<span data-ttu-id="3560b-116">事务超时值超过此操作建议的最大值。</span><span class="sxs-lookup"><span data-stu-id="3560b-116">The transaction time-out exceeds the recommended maximum for this operation.</span></span> <span data-ttu-id="3560b-117">有关详细信息，请参阅文档。%r</span><span class="sxs-lookup"><span data-stu-id="3560b-117">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="3560b-118">事务 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3560b-118">Transaction ID: %1%r</span></span><br /><br /> <span data-ttu-id="3560b-119">事务超时： %2 分钟 （零表示无限期超时） %r</span><span class="sxs-lookup"><span data-stu-id="3560b-119">Transaction time-out: %2 minutes (zero indicates an infinite time-out)%r</span></span><br /><br /> <span data-ttu-id="3560b-120">建议最大值： %3 分钟</span><span class="sxs-lookup"><span data-stu-id="3560b-120">Recommended maximum: %3 minutes</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3560b-121">解释</span><span class="sxs-lookup"><span data-stu-id="3560b-121">Explanation</span></span>  
 <span data-ttu-id="3560b-122">一个具有过大超时值的事务已进入系统。</span><span class="sxs-lookup"><span data-stu-id="3560b-122">A transaction has entered the system with an exceedingly large timeout value.</span></span> <span data-ttu-id="3560b-123">如果 ENTSSO 系统轮询 SSO 数据库，但该数据库被某个长时间运行的事务将其锁定，则系统最终会处于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="3560b-123">If the ENTSSO system polls the SSO database while it’s locked by a long-running transaction, the system will eventually go offline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3560b-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="3560b-124">User Action</span></span>  
 <span data-ttu-id="3560b-125">不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="3560b-125">No user action is required.</span></span>