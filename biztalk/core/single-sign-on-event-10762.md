---
title: "单一登录： 事件 10762 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 516e120d-e72b-4f40-9a81-9131ea247dd0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 487fbeb0f077950605432861a9118eacd93f2c89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10762"></a><span data-ttu-id="eb0cd-102">单一登录： 事件 10762</span><span class="sxs-lookup"><span data-stu-id="eb0cd-102">Single Sign-On: Event 10762</span></span>
## <a name="details"></a><span data-ttu-id="eb0cd-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="eb0cd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eb0cd-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="eb0cd-104">Product Name</span></span>|<span data-ttu-id="eb0cd-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="eb0cd-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="eb0cd-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="eb0cd-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="eb0cd-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="eb0cd-107">Event ID</span></span>|<span data-ttu-id="eb0cd-108">10762</span><span class="sxs-lookup"><span data-stu-id="eb0cd-108">10762</span></span>|  
|<span data-ttu-id="eb0cd-109">事件源</span><span class="sxs-lookup"><span data-stu-id="eb0cd-109">Event Source</span></span>|<span data-ttu-id="eb0cd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="eb0cd-110">ENTSSO</span></span>|  
|<span data-ttu-id="eb0cd-111">组件</span><span class="sxs-lookup"><span data-stu-id="eb0cd-111">Component</span></span>|<span data-ttu-id="eb0cd-112">N/A</span><span class="sxs-lookup"><span data-stu-id="eb0cd-112">N/A</span></span>|  
|<span data-ttu-id="eb0cd-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="eb0cd-113">Symbolic Name</span></span>|<span data-ttu-id="eb0cd-114">ENTSSO_E_WRONG_THREAD</span><span class="sxs-lookup"><span data-stu-id="eb0cd-114">ENTSSO_E_WRONG_THREAD</span></span>|  
|<span data-ttu-id="eb0cd-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="eb0cd-115">Message Text</span></span>|<span data-ttu-id="eb0cd-116">已在错误的线程上调用了 SSO 客户端组件。</span><span class="sxs-lookup"><span data-stu-id="eb0cd-116">The SSO client component has been called on the wrong thread.</span></span> <span data-ttu-id="eb0cd-117">由于此组件具有一个事务，因此当前被锁定到一个线程。</span><span class="sxs-lookup"><span data-stu-id="eb0cd-117">It is currently locked to a thread because it has a transaction.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eb0cd-118">解释</span><span class="sxs-lookup"><span data-stu-id="eb0cd-118">Explanation</span></span>  
 <span data-ttu-id="eb0cd-119">如果组件不具有事务，则只能为多线程。</span><span class="sxs-lookup"><span data-stu-id="eb0cd-119">Components can only be multi-threaded when they do not have a transaction.</span></span> <span data-ttu-id="eb0cd-120">此组件具有一个事务，因此被锁定到一个线程。</span><span class="sxs-lookup"><span data-stu-id="eb0cd-120">This component has a transaction so it is locked to a thread.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eb0cd-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="eb0cd-121">User Action</span></span>  
 <span data-ttu-id="eb0cd-122">配置您的应用程序以便使用事务时将不调用多个线程上的 SSO 客户端组件。</span><span class="sxs-lookup"><span data-stu-id="eb0cd-122">Configure your application so that it will not call SSO client components on multiple threads when using transactions.</span></span>