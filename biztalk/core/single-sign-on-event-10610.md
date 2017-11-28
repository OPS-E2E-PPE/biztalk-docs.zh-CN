---
title: "单一登录： 事件 10610 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6a400eb-7cf2-49df-befb-caf76e845fdf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3e4edc579c18147ad34234fbf268ec8d867c60f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10610"></a><span data-ttu-id="ebdec-102">单一登录： 事件 10610</span><span class="sxs-lookup"><span data-stu-id="ebdec-102">Single Sign-On: Event 10610</span></span>
## <a name="details"></a><span data-ttu-id="ebdec-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ebdec-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ebdec-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ebdec-104">Product Name</span></span>|<span data-ttu-id="ebdec-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ebdec-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ebdec-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ebdec-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ebdec-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ebdec-107">Event ID</span></span>|<span data-ttu-id="ebdec-108">10610</span><span class="sxs-lookup"><span data-stu-id="ebdec-108">10610</span></span>|  
|<span data-ttu-id="ebdec-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ebdec-109">Event Source</span></span>|<span data-ttu-id="ebdec-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ebdec-110">ENTSSO</span></span>|  
|<span data-ttu-id="ebdec-111">组件</span><span class="sxs-lookup"><span data-stu-id="ebdec-111">Component</span></span>|<span data-ttu-id="ebdec-112">N/A</span><span class="sxs-lookup"><span data-stu-id="ebdec-112">N/A</span></span>|  
|<span data-ttu-id="ebdec-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ebdec-113">Symbolic Name</span></span>|<span data-ttu-id="ebdec-114">SSO_WARN_CRED_CACHE_FAILED</span><span class="sxs-lookup"><span data-stu-id="ebdec-114">SSO_WARN_CRED_CACHE_FAILED</span></span>|  
|<span data-ttu-id="ebdec-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ebdec-115">Message Text</span></span>|<span data-ttu-id="ebdec-116">凭据缓存遇到意外错误并已关闭。</span><span class="sxs-lookup"><span data-stu-id="ebdec-116">The credential cache has encountered an unexpected error and has shut down.</span></span> <span data-ttu-id="ebdec-117">这可能会影响 performance.%r</span><span class="sxs-lookup"><span data-stu-id="ebdec-117">This may affect performance.%r</span></span><br /><br /> <span data-ttu-id="ebdec-118">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="ebdec-118">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ebdec-119">解释</span><span class="sxs-lookup"><span data-stu-id="ebdec-119">Explanation</span></span>  
 <span data-ttu-id="ebdec-120">凭据缓存遇到意外错误并已关闭。</span><span class="sxs-lookup"><span data-stu-id="ebdec-120">The credential cache has encountered an unexpected error and has shut down.</span></span> <span data-ttu-id="ebdec-121">尽管这可能会影响性能，但对功能运转没有影响。</span><span class="sxs-lookup"><span data-stu-id="ebdec-121">While this may affect performance, it will not affect functionality.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ebdec-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="ebdec-122">User Action</span></span>  
 <span data-ttu-id="ebdec-123">在方便的时候重新启动 SSO 服务。</span><span class="sxs-lookup"><span data-stu-id="ebdec-123">Restart the SSO service when convenient.</span></span>