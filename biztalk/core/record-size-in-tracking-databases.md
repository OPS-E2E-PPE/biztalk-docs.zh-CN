---
title: 在跟踪数据库中记录大小 |Microsoft 文档
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
ms.openlocfilehash: d1f4d09d1af92ce4777f5036885d81ea7bf3e648
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268309"
---
# <a name="record-size-in-tracking-databases"></a><span data-ttu-id="4d320-102">跟踪数据库中的记录大小</span><span class="sxs-lookup"><span data-stu-id="4d320-102">Record Size in Tracking Databases</span></span>
<span data-ttu-id="4d320-103">为了帮助您计划 BizTalk 的硬件要求，下表显示了跟踪数据库中不同事件记录的预期记录大小：</span><span class="sxs-lookup"><span data-stu-id="4d320-103">To help you plan your hardware requirements for BizTalk, the following table shows the expected record size for various event records in the Tracking database.</span></span>  
  
|<span data-ttu-id="4d320-104">操作类型</span><span class="sxs-lookup"><span data-stu-id="4d320-104">Action Type</span></span>|<span data-ttu-id="4d320-105">Size</span><span class="sxs-lookup"><span data-stu-id="4d320-105">Size</span></span>|<span data-ttu-id="4d320-106">说明</span><span class="sxs-lookup"><span data-stu-id="4d320-106">Notes</span></span>|  
|-----------------|----------|-----------|  
|<span data-ttu-id="4d320-107">部署服务</span><span class="sxs-lookup"><span data-stu-id="4d320-107">Deploying a Service</span></span>|<span data-ttu-id="4d320-108">1864 + 符号化信息大小</span><span class="sxs-lookup"><span data-stu-id="4d320-108">1864 + Symbolic Information Size</span></span>|<span data-ttu-id="4d320-109">符号化信息取决于业务流程的大小。</span><span class="sxs-lookup"><span data-stu-id="4d320-109">Symbolic Information depends on the size of the orchestration.</span></span> <span data-ttu-id="4d320-110">例如，接收一个消息并发送出一个包含 2 个形状的消息的业务流程占据大约 4000 字节。</span><span class="sxs-lookup"><span data-stu-id="4d320-110">For example, an orchestration that receives one message and sends one message out with 2 shapes in it takes approximately 4000 bytes.</span></span>|  
|<span data-ttu-id="4d320-111">已启动并已成功完成的服务实例</span><span class="sxs-lookup"><span data-stu-id="4d320-111">Started and Successfully Completed Service Instance</span></span>|<span data-ttu-id="4d320-112">通常为 252 字节。</span><span class="sxs-lookup"><span data-stu-id="4d320-112">Normally 252 bytes.</span></span><br /><br /> <span data-ttu-id="4d320-113">在极端情况下，可能达到 735 字节。</span><span class="sxs-lookup"><span data-stu-id="4d320-113">Extreme cases, can reach 735 bytes.</span></span>||  
|<span data-ttu-id="4d320-114">已启动但失败/遇到异常的服务实例</span><span class="sxs-lookup"><span data-stu-id="4d320-114">Started and Failed/Exception Met Service Instance</span></span>|<span data-ttu-id="4d320-115">通常为 252 字节 + 错误信息。</span><span class="sxs-lookup"><span data-stu-id="4d320-115">Normally 252 bytes + error information.</span></span><br /><br /> <span data-ttu-id="4d320-116">在极端情况下，可能达到 735 字节 + 错误信息。</span><span class="sxs-lookup"><span data-stu-id="4d320-116">Extreme cases can reach 735 bytes + error information.</span></span>|<span data-ttu-id="4d320-117">错误信息是 BizTalk 或用户组件返回的文本数据。</span><span class="sxs-lookup"><span data-stu-id="4d320-117">Error information is the text data returned by a BizTalk or user component.</span></span> <span data-ttu-id="4d320-118">大小从 100 字节到 2 KB 不等。</span><span class="sxs-lookup"><span data-stu-id="4d320-118">Ranges from 100 bytes to 2 KB.</span></span>|  
|<span data-ttu-id="4d320-119">业务流程中形状的开始/结束</span><span class="sxs-lookup"><span data-stu-id="4d320-119">Start/End of a Shape In an Orchestration</span></span>|<span data-ttu-id="4d320-120">每个 120 字节。</span><span class="sxs-lookup"><span data-stu-id="4d320-120">120 bytes each.</span></span>||  
|<span data-ttu-id="4d320-121">消息输入/输出事件</span><span class="sxs-lookup"><span data-stu-id="4d320-121">Message In/Out Events</span></span>|<span data-ttu-id="4d320-122">最小 162 字节。</span><span class="sxs-lookup"><span data-stu-id="4d320-122">Minimum 162 bytes.</span></span><br /><br /> <span data-ttu-id="4d320-123">首次查看消息时，此记录大小为 202 字节 + 消息属性（如果跟踪）</span><span class="sxs-lookup"><span data-stu-id="4d320-123">First time message is seen it is 202 bytes + Message Property (if tracked)</span></span><br /><br /> <span data-ttu-id="4d320-124">在极端情况下，可能达到 2930 字节。</span><span class="sxs-lookup"><span data-stu-id="4d320-124">Extreme cases can reach 2930 bytes.</span></span>|<span data-ttu-id="4d320-125">如果不存在任何消息属性跟踪，则可以安全地假定平均大小为 182 字节。</span><span class="sxs-lookup"><span data-stu-id="4d320-125">You can safely assume that the average is 182 bytes if there is no message property tracking.</span></span>|  
|<span data-ttu-id="4d320-126">消息属性大小</span><span class="sxs-lookup"><span data-stu-id="4d320-126">Message Property Size</span></span>|<span data-ttu-id="4d320-127">如果 DTA 识别此跟踪属性的 40 到 288 个字节。</span><span class="sxs-lookup"><span data-stu-id="4d320-127">40 to 288 bytes if DTA recognizes this tracking property.</span></span><br /><br /> <span data-ttu-id="4d320-128">对于首次跟踪属性，则此记录大小总计为 268 字节。</span><span class="sxs-lookup"><span data-stu-id="4d320-128">Add up to 268 bytes for tracking the property the first time.</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="4d320-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d320-129">See Also</span></span>  
 <span data-ttu-id="4d320-130">[什么是邮件跟踪？](../core/what-is-message-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="4d320-130">[What is Message Tracking?](../core/what-is-message-tracking.md) </span></span>  
 [<span data-ttu-id="4d320-131">管理和跟踪体系结构</span><span class="sxs-lookup"><span data-stu-id="4d320-131">Management and Tracking Architecture</span></span>](../core/management-and-tracking-architecture.md)