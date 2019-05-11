---
title: 单一登录：Event 10610 | Microsoft Docs
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
ms.openlocfilehash: 451468316420c0653b967a25f233564303a6e1a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397726"
---
# <a name="single-sign-on-event-10610"></a><span data-ttu-id="ed4a5-102">单一登录：事件 10610</span><span class="sxs-lookup"><span data-stu-id="ed4a5-102">Single Sign-On: Event 10610</span></span>
## <a name="details"></a><span data-ttu-id="ed4a5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ed4a5-103">Details</span></span>  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ed4a5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ed4a5-104">Product Name</span></span>   |                                                       <span data-ttu-id="ed4a5-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ed4a5-105">Enterprise Single Sign-On</span></span>                                                       |
| <span data-ttu-id="ed4a5-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ed4a5-106">Product Version</span></span> |                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    <span data-ttu-id="ed4a5-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ed4a5-107">Event ID</span></span>     |                                                                 <span data-ttu-id="ed4a5-108">10610</span><span class="sxs-lookup"><span data-stu-id="ed4a5-108">10610</span></span>                                                                 |
|  <span data-ttu-id="ed4a5-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ed4a5-109">Event Source</span></span>   |                                                                <span data-ttu-id="ed4a5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ed4a5-110">ENTSSO</span></span>                                                                 |
|    <span data-ttu-id="ed4a5-111">组件</span><span class="sxs-lookup"><span data-stu-id="ed4a5-111">Component</span></span>    |                                                                  <span data-ttu-id="ed4a5-112">不可用</span><span class="sxs-lookup"><span data-stu-id="ed4a5-112">N/A</span></span>                                                                  |
|  <span data-ttu-id="ed4a5-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ed4a5-113">Symbolic Name</span></span>  |                                                      <span data-ttu-id="ed4a5-114">SSO_WARN_CRED_CACHE_FAILED</span><span class="sxs-lookup"><span data-stu-id="ed4a5-114">SSO_WARN_CRED_CACHE_FAILED</span></span>                                                       |
|  <span data-ttu-id="ed4a5-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ed4a5-115">Message Text</span></span>   | <span data-ttu-id="ed4a5-116">凭据缓存遇到意外的错误，已经关闭。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-116">The credential cache has encountered an unexpected error and has shut down.</span></span> <span data-ttu-id="ed4a5-117">这可能会影响 performance.%r</span><span class="sxs-lookup"><span data-stu-id="ed4a5-117">This may affect performance.%r</span></span><br /><br /> <span data-ttu-id="ed4a5-118">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="ed4a5-118">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ed4a5-119">解释</span><span class="sxs-lookup"><span data-stu-id="ed4a5-119">Explanation</span></span>  
 <span data-ttu-id="ed4a5-120">凭据缓存遇到意外的错误，已经关闭。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-120">The credential cache has encountered an unexpected error and has shut down.</span></span> <span data-ttu-id="ed4a5-121">虽然这可能会影响性能，它不会影响功能。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-121">While this may affect performance, it will not affect functionality.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ed4a5-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="ed4a5-122">User Action</span></span>  
 <span data-ttu-id="ed4a5-123">重新启动 SSO 服务在方便的时候。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-123">Restart the SSO service when convenient.</span></span>