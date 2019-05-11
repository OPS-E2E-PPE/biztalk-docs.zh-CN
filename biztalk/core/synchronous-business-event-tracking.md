---
title: 同步业务事件跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 302c7918-bc62-46f1-a949-fbf94a7073e3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a97cfac1eb2b4fa13e0f3d94867d2a4993c6ba5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321821"
---
# <a name="synchronous-business-event-tracking"></a><span data-ttu-id="f7be8-102">同步业务事件跟踪</span><span class="sxs-lookup"><span data-stu-id="f7be8-102">Synchronous Business Event Tracking</span></span>
<span data-ttu-id="f7be8-103">若要向 BAM 发送事件数据的最简单方法是使用 DirectEventStream 类的实例。</span><span class="sxs-lookup"><span data-stu-id="f7be8-103">The simplest way to send event data to BAM is to use an instance of the class DirectEventStream.</span></span> <span data-ttu-id="f7be8-104">此类将事件数据保存到 BAM 主导入数据库中的应用程序 （如果存在） 的当前事务上下文直接。</span><span class="sxs-lookup"><span data-stu-id="f7be8-104">This class saves the event data directly into the BAM Primary Import Database in the context of the current transaction of the application (if present).</span></span>  
  
 <span data-ttu-id="f7be8-105">如果在执行此操作，会发生任何错误，方法调用将返回在调用应用程序中引发异常。</span><span class="sxs-lookup"><span data-stu-id="f7be8-105">If any error happens during this operation, the method call will throw an exception back in the calling application.</span></span> <span data-ttu-id="f7be8-106">这将会发生例如如果传入 UpdateActivity 的项的名称不匹配的 BAM 活动定义，或未尚未部署 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="f7be8-106">This will happen for example if the name of an item passed in UpdateActivity mismatches the BAM Activity Definition, or you did not deploy the BAM Definition yet.</span></span> <span data-ttu-id="f7be8-107">这样调用应用程序以捕获并保存 BAM 数据，这会导致多更轻松地管理更高版本时从任何错误中恢复。</span><span class="sxs-lookup"><span data-stu-id="f7be8-107">This allows the calling application to catch and recover from any errors when saving the BAM data, which results in much easier management later.</span></span>  
  
 <span data-ttu-id="f7be8-108">同步保存数据可能影响性能，因为调用应用程序必须等待，直到 BAM 执行所有存储的过程和触发器。</span><span class="sxs-lookup"><span data-stu-id="f7be8-108">Saving the data synchronously might have a performance impact, because the calling application has to wait until BAM executes all stored procedures and triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7be8-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7be8-109">See Also</span></span>  
 [<span data-ttu-id="f7be8-110">异步业务事件跟踪</span><span class="sxs-lookup"><span data-stu-id="f7be8-110">Asynchronous Business Event Tracking</span></span>](../core/asynchronous-business-event-tracking.md)