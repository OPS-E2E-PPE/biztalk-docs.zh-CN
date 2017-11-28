---
title: "单一登录： 事件 10590 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd8c3804-5c84-403f-881b-e4b101c2323a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 542e597c56f1049133670c91f233d82f5f431b78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10590"></a><span data-ttu-id="0989d-102">单一登录： 事件 10590</span><span class="sxs-lookup"><span data-stu-id="0989d-102">Single Sign-On: Event 10590</span></span>
## <a name="details"></a><span data-ttu-id="0989d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0989d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0989d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0989d-104">Product Name</span></span>|<span data-ttu-id="0989d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0989d-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0989d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0989d-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0989d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0989d-107">Event ID</span></span>|<span data-ttu-id="0989d-108">10590</span><span class="sxs-lookup"><span data-stu-id="0989d-108">10590</span></span>|  
|<span data-ttu-id="0989d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0989d-109">Event Source</span></span>|<span data-ttu-id="0989d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0989d-110">ENTSSO</span></span>|  
|<span data-ttu-id="0989d-111">组件</span><span class="sxs-lookup"><span data-stu-id="0989d-111">Component</span></span>|<span data-ttu-id="0989d-112">N/A</span><span class="sxs-lookup"><span data-stu-id="0989d-112">N/A</span></span>|  
|<span data-ttu-id="0989d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0989d-113">Symbolic Name</span></span>|<span data-ttu-id="0989d-114">SSO_ERROR_OUT_OF_SERVICE</span><span class="sxs-lookup"><span data-stu-id="0989d-114">SSO_ERROR_OUT_OF_SERVICE</span></span>|  
|<span data-ttu-id="0989d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0989d-115">Message Text</span></span>|<span data-ttu-id="0989d-116">企业单一登录正在进入脱机状态。</span><span class="sxs-lookup"><span data-stu-id="0989d-116">Enterprise Single Sign-On is going offline.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0989d-117">解释</span><span class="sxs-lookup"><span data-stu-id="0989d-117">Explanation</span></span>  
 <span data-ttu-id="0989d-118">通常，ENTSSO 系统每隔 30 秒检查一次 ENTSSO 数据库中的更新。</span><span class="sxs-lookup"><span data-stu-id="0989d-118">The ENTSSO system usually checks for updates on the ENTSSO database every 30 seconds.</span></span> <span data-ttu-id="0989d-119">如果数据库在指定的时间内（通常是五分钟）不可用，则系统本身进入脱机状态。</span><span class="sxs-lookup"><span data-stu-id="0989d-119">If the database is unavailable for a specified time (usually five minutes), the system itself goes offline.</span></span> <span data-ttu-id="0989d-120">在此状态下，系统将不会响应凭据请求。</span><span class="sxs-lookup"><span data-stu-id="0989d-120">In this state the system will not respond to requests for credentials.</span></span> <span data-ttu-id="0989d-121">但仍然可以响应某些脱机和管理活动。</span><span class="sxs-lookup"><span data-stu-id="0989d-121">Some offline and administrative activities are still possible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0989d-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="0989d-122">User Action</span></span>  
 <span data-ttu-id="0989d-123">此错误表示 ENTSSO 数据库处于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="0989d-123">This error indicates that the ENTSSO database is offline.</span></span> <span data-ttu-id="0989d-124">您应该立即调查。</span><span class="sxs-lookup"><span data-stu-id="0989d-124">You should investigate immediately.</span></span>