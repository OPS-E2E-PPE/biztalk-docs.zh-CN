---
title: 单一登录：Event 10762 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 516e120d-e72b-4f40-9a81-9131ea247dd0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b26f196e2431f0229ac28b9d8f2718b551a58b1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396653"
---
# <a name="single-sign-on-event-10762"></a><span data-ttu-id="3af5b-102">单一登录：事件 10762</span><span class="sxs-lookup"><span data-stu-id="3af5b-102">Single Sign-On: Event 10762</span></span>
## <a name="details"></a><span data-ttu-id="3af5b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3af5b-103">Details</span></span>  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3af5b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3af5b-104">Product Name</span></span>   |                                                   <span data-ttu-id="3af5b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="3af5b-105">Enterprise Single Sign-On</span></span>                                                    |
| <span data-ttu-id="3af5b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="3af5b-106">Product Version</span></span> |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    <span data-ttu-id="3af5b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3af5b-107">Event ID</span></span>     |                                                             <span data-ttu-id="3af5b-108">10762</span><span class="sxs-lookup"><span data-stu-id="3af5b-108">10762</span></span>                                                              |
|  <span data-ttu-id="3af5b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="3af5b-109">Event Source</span></span>   |                                                             <span data-ttu-id="3af5b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3af5b-110">ENTSSO</span></span>                                                             |
|    <span data-ttu-id="3af5b-111">组件</span><span class="sxs-lookup"><span data-stu-id="3af5b-111">Component</span></span>    |                                                              <span data-ttu-id="3af5b-112">不可用</span><span class="sxs-lookup"><span data-stu-id="3af5b-112">N/A</span></span>                                                               |
|  <span data-ttu-id="3af5b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="3af5b-113">Symbolic Name</span></span>  |                                                     <span data-ttu-id="3af5b-114">ENTSSO_E_WRONG_THREAD</span><span class="sxs-lookup"><span data-stu-id="3af5b-114">ENTSSO_E_WRONG_THREAD</span></span>                                                      |
|  <span data-ttu-id="3af5b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="3af5b-115">Message Text</span></span>   | <span data-ttu-id="3af5b-116">已对错误的线程调用 SSO 客户端组件。</span><span class="sxs-lookup"><span data-stu-id="3af5b-116">The SSO client component has been called on the wrong thread.</span></span> <span data-ttu-id="3af5b-117">它当前已锁定到一个线程，因为它具有一个事务。</span><span class="sxs-lookup"><span data-stu-id="3af5b-117">It is currently locked to a thread because it has a transaction.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3af5b-118">解释</span><span class="sxs-lookup"><span data-stu-id="3af5b-118">Explanation</span></span>  
 <span data-ttu-id="3af5b-119">当它们不具有事务组件只能是多线程。</span><span class="sxs-lookup"><span data-stu-id="3af5b-119">Components can only be multi-threaded when they do not have a transaction.</span></span> <span data-ttu-id="3af5b-120">此组件有一个事务，因此它锁定到一个线程。</span><span class="sxs-lookup"><span data-stu-id="3af5b-120">This component has a transaction so it is locked to a thread.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3af5b-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="3af5b-121">User Action</span></span>  
 <span data-ttu-id="3af5b-122">配置你的应用程序，以便它将不会调用 SSO 客户端组件在多个线程上使用事务时。</span><span class="sxs-lookup"><span data-stu-id="3af5b-122">Configure your application so that it will not call SSO client components on multiple threads when using transactions.</span></span>