---
title: 单一登录： 事件 10610 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f6a400eb-7cf2-49df-befb-caf76e845fdf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c90855c1f136dc8204afe718ea4456c834ab667
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024403"
---
# <a name="single-sign-on-event-10610"></a><span data-ttu-id="29239-102">单一登录： 事件 10610</span><span class="sxs-lookup"><span data-stu-id="29239-102">Single Sign-On: Event 10610</span></span>
## <a name="details"></a><span data-ttu-id="29239-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="29239-103">Details</span></span>  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="29239-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="29239-104">Product Name</span></span>   |                                                       <span data-ttu-id="29239-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="29239-105">Enterprise Single Sign-On</span></span>                                                       |
| <span data-ttu-id="29239-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="29239-106">Product Version</span></span> |                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    <span data-ttu-id="29239-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="29239-107">Event ID</span></span>     |                                                                 <span data-ttu-id="29239-108">10610</span><span class="sxs-lookup"><span data-stu-id="29239-108">10610</span></span>                                                                 |
|  <span data-ttu-id="29239-109">事件源</span><span class="sxs-lookup"><span data-stu-id="29239-109">Event Source</span></span>   |                                                                <span data-ttu-id="29239-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="29239-110">ENTSSO</span></span>                                                                 |
|    <span data-ttu-id="29239-111">组件</span><span class="sxs-lookup"><span data-stu-id="29239-111">Component</span></span>    |                                                                  <span data-ttu-id="29239-112">N/A</span><span class="sxs-lookup"><span data-stu-id="29239-112">N/A</span></span>                                                                  |
|  <span data-ttu-id="29239-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="29239-113">Symbolic Name</span></span>  |                                                      <span data-ttu-id="29239-114">SSO_WARN_CRED_CACHE_FAILED</span><span class="sxs-lookup"><span data-stu-id="29239-114">SSO_WARN_CRED_CACHE_FAILED</span></span>                                                       |
|  <span data-ttu-id="29239-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="29239-115">Message Text</span></span>   | <span data-ttu-id="29239-116">凭据缓存遇到意外错误并已关闭。</span><span class="sxs-lookup"><span data-stu-id="29239-116">The credential cache has encountered an unexpected error and has shut down.</span></span> <span data-ttu-id="29239-117">这可能会影响 performance.%r</span><span class="sxs-lookup"><span data-stu-id="29239-117">This may affect performance.%r</span></span><br /><br /> <span data-ttu-id="29239-118">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="29239-118">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="29239-119">解释</span><span class="sxs-lookup"><span data-stu-id="29239-119">Explanation</span></span>  
 <span data-ttu-id="29239-120">凭据缓存遇到意外错误并已关闭。</span><span class="sxs-lookup"><span data-stu-id="29239-120">The credential cache has encountered an unexpected error and has shut down.</span></span> <span data-ttu-id="29239-121">尽管这可能会影响性能，但对功能运转没有影响。</span><span class="sxs-lookup"><span data-stu-id="29239-121">While this may affect performance, it will not affect functionality.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="29239-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="29239-122">User Action</span></span>  
 <span data-ttu-id="29239-123">在方便的时候重新启动 SSO 服务。</span><span class="sxs-lookup"><span data-stu-id="29239-123">Restart the SSO service when convenient.</span></span>