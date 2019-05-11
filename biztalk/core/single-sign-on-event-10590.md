---
title: 单一登录：Event 10590 | Microsoft Docs
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
ms.openlocfilehash: 21e9ed1ffdee369ccb357cb7b7f20424cb61b474
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271034"
---
# <a name="single-sign-on-event-10590"></a><span data-ttu-id="4c2da-102">单一登录：事件 10590</span><span class="sxs-lookup"><span data-stu-id="4c2da-102">Single Sign-On: Event 10590</span></span>
## <a name="details"></a><span data-ttu-id="4c2da-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="4c2da-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="4c2da-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="4c2da-104">Product Name</span></span>   |                 <span data-ttu-id="4c2da-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="4c2da-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="4c2da-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="4c2da-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="4c2da-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4c2da-107">Event ID</span></span>     |                           <span data-ttu-id="4c2da-108">10590</span><span class="sxs-lookup"><span data-stu-id="4c2da-108">10590</span></span>                            |
|  <span data-ttu-id="4c2da-109">事件源</span><span class="sxs-lookup"><span data-stu-id="4c2da-109">Event Source</span></span>   |                           <span data-ttu-id="4c2da-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4c2da-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="4c2da-111">组件</span><span class="sxs-lookup"><span data-stu-id="4c2da-111">Component</span></span>    |                            <span data-ttu-id="4c2da-112">不可用</span><span class="sxs-lookup"><span data-stu-id="4c2da-112">N/A</span></span>                             |
|  <span data-ttu-id="4c2da-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="4c2da-113">Symbolic Name</span></span>  |                  <span data-ttu-id="4c2da-114">SSO_ERROR_OUT_OF_SERVICE</span><span class="sxs-lookup"><span data-stu-id="4c2da-114">SSO_ERROR_OUT_OF_SERVICE</span></span>                  |
|  <span data-ttu-id="4c2da-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="4c2da-115">Message Text</span></span>   |        <span data-ttu-id="4c2da-116">企业单一登录正在进入脱机状态。</span><span class="sxs-lookup"><span data-stu-id="4c2da-116">Enterprise Single Sign-On is going offline.</span></span>         |
  
## <a name="explanation"></a><span data-ttu-id="4c2da-117">解释</span><span class="sxs-lookup"><span data-stu-id="4c2da-117">Explanation</span></span>  
 <span data-ttu-id="4c2da-118">ENTSSO 系统通常会会每隔 30 秒检查 ENTSSO 数据库上的更新。</span><span class="sxs-lookup"><span data-stu-id="4c2da-118">The ENTSSO system usually checks for updates on the ENTSSO database every 30 seconds.</span></span> <span data-ttu-id="4c2da-119">如果指定的时间 （通常为 5 分钟），数据库将不可用，则系统本身进入脱机。</span><span class="sxs-lookup"><span data-stu-id="4c2da-119">If the database is unavailable for a specified time (usually five minutes), the system itself goes offline.</span></span> <span data-ttu-id="4c2da-120">在此状态下，系统将不响应凭据请求。</span><span class="sxs-lookup"><span data-stu-id="4c2da-120">In this state the system will not respond to requests for credentials.</span></span> <span data-ttu-id="4c2da-121">仍有可能某些脱机和管理活动。</span><span class="sxs-lookup"><span data-stu-id="4c2da-121">Some offline and administrative activities are still possible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4c2da-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="4c2da-122">User Action</span></span>  
 <span data-ttu-id="4c2da-123">此错误表示 ENTSSO 数据库处于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="4c2da-123">This error indicates that the ENTSSO database is offline.</span></span> <span data-ttu-id="4c2da-124">应立即调查。</span><span class="sxs-lookup"><span data-stu-id="4c2da-124">You should investigate immediately.</span></span>