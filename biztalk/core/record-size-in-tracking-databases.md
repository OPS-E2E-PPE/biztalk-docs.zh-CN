---
title: 跟踪数据库中记录大小 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: be7a891b-2674-49a3-a8e0-6aa11a918bf2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1e19e5861a061294806c428d300d475ac2e21c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398047"
---
# <a name="record-size-in-tracking-databases"></a><span data-ttu-id="19628-102">跟踪数据库中的记录大小</span><span class="sxs-lookup"><span data-stu-id="19628-102">Record Size in Tracking Databases</span></span>
<span data-ttu-id="19628-103">为了帮助你规划 BizTalk 的硬件要求下, 表显示在跟踪数据库中的各种事件记录的预期的记录大小。</span><span class="sxs-lookup"><span data-stu-id="19628-103">To help you plan your hardware requirements for BizTalk, the following table shows the expected record size for various event records in the Tracking database.</span></span>  
  
|<span data-ttu-id="19628-104">操作类型</span><span class="sxs-lookup"><span data-stu-id="19628-104">Action Type</span></span>|<span data-ttu-id="19628-105">大小</span><span class="sxs-lookup"><span data-stu-id="19628-105">Size</span></span>|<span data-ttu-id="19628-106">说明</span><span class="sxs-lookup"><span data-stu-id="19628-106">Notes</span></span>|  
|-----------------|----------|-----------|  
|<span data-ttu-id="19628-107">部署服务</span><span class="sxs-lookup"><span data-stu-id="19628-107">Deploying a Service</span></span>|<span data-ttu-id="19628-108">1864 + 符号化信息大小</span><span class="sxs-lookup"><span data-stu-id="19628-108">1864 + Symbolic Information Size</span></span>|<span data-ttu-id="19628-109">符号化信息取决于业务流程的大小。</span><span class="sxs-lookup"><span data-stu-id="19628-109">Symbolic Information depends on the size of the orchestration.</span></span> <span data-ttu-id="19628-110">例如，接收一条消息，并使用 2 个形状发出一条消息的业务流程占据大约 4000 字节。</span><span class="sxs-lookup"><span data-stu-id="19628-110">For example, an orchestration that receives one message and sends one message out with 2 shapes in it takes approximately 4000 bytes.</span></span>|  
|<span data-ttu-id="19628-111">已启动并已成功完成服务实例</span><span class="sxs-lookup"><span data-stu-id="19628-111">Started and Successfully Completed Service Instance</span></span>|<span data-ttu-id="19628-112">通常为 252 字节。</span><span class="sxs-lookup"><span data-stu-id="19628-112">Normally 252 bytes.</span></span><br /><br /> <span data-ttu-id="19628-113">在极端情况下，可能达到 735 字节。</span><span class="sxs-lookup"><span data-stu-id="19628-113">Extreme cases, can reach 735 bytes.</span></span>||  
|<span data-ttu-id="19628-114">启动并失败/遇到异常的服务实例</span><span class="sxs-lookup"><span data-stu-id="19628-114">Started and Failed/Exception Met Service Instance</span></span>|<span data-ttu-id="19628-115">通常为 252 字节 + 错误信息。</span><span class="sxs-lookup"><span data-stu-id="19628-115">Normally 252 bytes + error information.</span></span><br /><br /> <span data-ttu-id="19628-116">在极端情况下可能达到 735 字节 + 错误信息。</span><span class="sxs-lookup"><span data-stu-id="19628-116">Extreme cases can reach 735 bytes + error information.</span></span>|<span data-ttu-id="19628-117">错误信息是 BizTalk 或用户组件返回的文本数据。</span><span class="sxs-lookup"><span data-stu-id="19628-117">Error information is the text data returned by a BizTalk or user component.</span></span> <span data-ttu-id="19628-118">范围的范围是从 100 个字节到 2 KB。</span><span class="sxs-lookup"><span data-stu-id="19628-118">Ranges from 100 bytes to 2 KB.</span></span>|  
|<span data-ttu-id="19628-119">在业务流程中形状的开始/结束</span><span class="sxs-lookup"><span data-stu-id="19628-119">Start/End of a Shape In an Orchestration</span></span>|<span data-ttu-id="19628-120">每个 120 字节。</span><span class="sxs-lookup"><span data-stu-id="19628-120">120 bytes each.</span></span>||  
|<span data-ttu-id="19628-121">消息输入/输出事件</span><span class="sxs-lookup"><span data-stu-id="19628-121">Message In/Out Events</span></span>|<span data-ttu-id="19628-122">最小 162 字节。</span><span class="sxs-lookup"><span data-stu-id="19628-122">Minimum 162 bytes.</span></span><br /><br /> <span data-ttu-id="19628-123">第一次查看消息时它为 202 字节 + 消息属性 （如果跟踪）</span><span class="sxs-lookup"><span data-stu-id="19628-123">First time message is seen it is 202 bytes + Message Property (if tracked)</span></span><br /><br /> <span data-ttu-id="19628-124">在极端情况下可能达到 2930 字节。</span><span class="sxs-lookup"><span data-stu-id="19628-124">Extreme cases can reach 2930 bytes.</span></span>|<span data-ttu-id="19628-125">您可以放心平均值为 182 字节，如果没有任何消息属性跟踪。</span><span class="sxs-lookup"><span data-stu-id="19628-125">You can safely assume that the average is 182 bytes if there is no message property tracking.</span></span>|  
|<span data-ttu-id="19628-126">消息属性大小</span><span class="sxs-lookup"><span data-stu-id="19628-126">Message Property Size</span></span>|<span data-ttu-id="19628-127">如果 DTA 识别此跟踪属性的 40 到 288 字节。</span><span class="sxs-lookup"><span data-stu-id="19628-127">40 to 288 bytes if DTA recognizes this tracking property.</span></span><br /><br /> <span data-ttu-id="19628-128">添加总计为 268 字节用于跟踪该属性第一次。</span><span class="sxs-lookup"><span data-stu-id="19628-128">Add up to 268 bytes for tracking the property the first time.</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="19628-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="19628-129">See Also</span></span>  
 <span data-ttu-id="19628-130">[什么是消息跟踪？](../core/what-is-message-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="19628-130">[What is Message Tracking?](../core/what-is-message-tracking.md) </span></span>  
 [<span data-ttu-id="19628-131">管理和跟踪体系结构</span><span class="sxs-lookup"><span data-stu-id="19628-131">Management and Tracking Architecture</span></span>](../core/management-and-tracking-architecture.md)