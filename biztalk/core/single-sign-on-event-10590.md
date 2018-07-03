---
title: 单一登录： 事件 10590 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd8c3804-5c84-403f-881b-e4b101c2323a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc2ac48ecf1279c1a8347e8f1ab3bcd1367854ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006766"
---
# <a name="single-sign-on-event-10590"></a><span data-ttu-id="e183b-102">单一登录： 事件 10590</span><span class="sxs-lookup"><span data-stu-id="e183b-102">Single Sign-On: Event 10590</span></span>
## <a name="details"></a><span data-ttu-id="e183b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e183b-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="e183b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e183b-104">Product Name</span></span>   |                 <span data-ttu-id="e183b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e183b-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="e183b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e183b-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="e183b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e183b-107">Event ID</span></span>     |                           <span data-ttu-id="e183b-108">10590</span><span class="sxs-lookup"><span data-stu-id="e183b-108">10590</span></span>                            |
|  <span data-ttu-id="e183b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e183b-109">Event Source</span></span>   |                           <span data-ttu-id="e183b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e183b-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="e183b-111">组件</span><span class="sxs-lookup"><span data-stu-id="e183b-111">Component</span></span>    |                            <span data-ttu-id="e183b-112">N/A</span><span class="sxs-lookup"><span data-stu-id="e183b-112">N/A</span></span>                             |
|  <span data-ttu-id="e183b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e183b-113">Symbolic Name</span></span>  |                  <span data-ttu-id="e183b-114">SSO_ERROR_OUT_OF_SERVICE</span><span class="sxs-lookup"><span data-stu-id="e183b-114">SSO_ERROR_OUT_OF_SERVICE</span></span>                  |
|  <span data-ttu-id="e183b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e183b-115">Message Text</span></span>   |        <span data-ttu-id="e183b-116">企业单一登录正在进入脱机状态。</span><span class="sxs-lookup"><span data-stu-id="e183b-116">Enterprise Single Sign-On is going offline.</span></span>         |
  
## <a name="explanation"></a><span data-ttu-id="e183b-117">解释</span><span class="sxs-lookup"><span data-stu-id="e183b-117">Explanation</span></span>  
 <span data-ttu-id="e183b-118">通常，ENTSSO 系统每隔 30 秒检查一次 ENTSSO 数据库中的更新。</span><span class="sxs-lookup"><span data-stu-id="e183b-118">The ENTSSO system usually checks for updates on the ENTSSO database every 30 seconds.</span></span> <span data-ttu-id="e183b-119">如果数据库在指定的时间内（通常是五分钟）不可用，则系统本身进入脱机状态。</span><span class="sxs-lookup"><span data-stu-id="e183b-119">If the database is unavailable for a specified time (usually five minutes), the system itself goes offline.</span></span> <span data-ttu-id="e183b-120">在此状态下，系统将不会响应凭据请求。</span><span class="sxs-lookup"><span data-stu-id="e183b-120">In this state the system will not respond to requests for credentials.</span></span> <span data-ttu-id="e183b-121">但仍然可以响应某些脱机和管理活动。</span><span class="sxs-lookup"><span data-stu-id="e183b-121">Some offline and administrative activities are still possible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e183b-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="e183b-122">User Action</span></span>  
 <span data-ttu-id="e183b-123">此错误表示 ENTSSO 数据库处于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="e183b-123">This error indicates that the ENTSSO database is offline.</span></span> <span data-ttu-id="e183b-124">您应该立即调查。</span><span class="sxs-lookup"><span data-stu-id="e183b-124">You should investigate immediately.</span></span>