---
title: 单一登录：Event 10612 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9d9e6f5-06b8-4989-a0dc-6e2e5980443b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b73a601e883f651b5333224c557a1344d32943c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397714"
---
# <a name="single-sign-on-event-10612"></a><span data-ttu-id="14529-102">单一登录：事件 10612</span><span class="sxs-lookup"><span data-stu-id="14529-102">Single Sign-On: Event 10612</span></span>
## <a name="details"></a><span data-ttu-id="14529-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="14529-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="14529-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="14529-104">Product Name</span></span>   |                                                                                                                            <span data-ttu-id="14529-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="14529-105">Enterprise Single Sign-On</span></span>                                                                                                                            |
| <span data-ttu-id="14529-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="14529-106">Product Version</span></span> |                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                            |
|    <span data-ttu-id="14529-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="14529-107">Event ID</span></span>     |                                                                                                                                      <span data-ttu-id="14529-108">10612</span><span class="sxs-lookup"><span data-stu-id="14529-108">10612</span></span>                                                                                                                                      |
|  <span data-ttu-id="14529-109">事件源</span><span class="sxs-lookup"><span data-stu-id="14529-109">Event Source</span></span>   |                                                                                                                                     <span data-ttu-id="14529-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="14529-110">ENTSSO</span></span>                                                                                                                                      |
|    <span data-ttu-id="14529-111">组件</span><span class="sxs-lookup"><span data-stu-id="14529-111">Component</span></span>    |                                                                                                                                       <span data-ttu-id="14529-112">不可用</span><span class="sxs-lookup"><span data-stu-id="14529-112">N/A</span></span>                                                                                                                                       |
|  <span data-ttu-id="14529-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="14529-113">Symbolic Name</span></span>  |                                                                                                                          <span data-ttu-id="14529-114">SSO_WARN_TRANSACTION_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="14529-114">SSO_WARN_TRANSACTION_TIMEOUT</span></span>                                                                                                                           |
|  <span data-ttu-id="14529-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="14529-115">Message Text</span></span>   | <span data-ttu-id="14529-116">事务超时时间超出了此操作的建议最大值。</span><span class="sxs-lookup"><span data-stu-id="14529-116">The transaction time-out exceeds the recommended maximum for this operation.</span></span> <span data-ttu-id="14529-117">请参阅 details.%r 文档</span><span class="sxs-lookup"><span data-stu-id="14529-117">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="14529-118">事务 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="14529-118">Transaction ID: %1%r</span></span><br /><br /> <span data-ttu-id="14529-119">事务超时： %2 分钟 （零表示无限超时） %r</span><span class="sxs-lookup"><span data-stu-id="14529-119">Transaction time-out: %2 minutes (zero indicates an infinite time-out)%r</span></span><br /><br /> <span data-ttu-id="14529-120">建议最大值： %3 分钟</span><span class="sxs-lookup"><span data-stu-id="14529-120">Recommended maximum: %3 minutes</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="14529-121">解释</span><span class="sxs-lookup"><span data-stu-id="14529-121">Explanation</span></span>  
 <span data-ttu-id="14529-122">事务已进入系统具有过大超时值。</span><span class="sxs-lookup"><span data-stu-id="14529-122">A transaction has entered the system with an exceedingly large timeout value.</span></span> <span data-ttu-id="14529-123">如果 ENTSSO 系统轮询 SSO 数据库时锁定由长时间运行事务时，系统最终会处于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="14529-123">If the ENTSSO system polls the SSO database while it’s locked by a long-running transaction, the system will eventually go offline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14529-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="14529-124">User Action</span></span>  
 <span data-ttu-id="14529-125">不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="14529-125">No user action is required.</span></span>