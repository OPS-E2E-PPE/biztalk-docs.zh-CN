---
title: 同步业务事件跟踪 |Microsoft 文档
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
ms.openlocfilehash: 84223714e2e04cec6c079862693a09786cb19a7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277933"
---
# <a name="synchronous-business-event-tracking"></a><span data-ttu-id="b3a74-102">同步业务事件跟踪</span><span class="sxs-lookup"><span data-stu-id="b3a74-102">Synchronous Business Event Tracking</span></span>
<span data-ttu-id="b3a74-103">向 BAM 发送事件数据的最简单方法是使用 DirectEventStream 类的实例。</span><span class="sxs-lookup"><span data-stu-id="b3a74-103">The simplest way to send event data to BAM is to use an instance of the class DirectEventStream.</span></span> <span data-ttu-id="b3a74-104">此类在应用程序的当前事务（如果有）的上下文中将事件数据直接保存到 BAM 主导入数据库中。</span><span class="sxs-lookup"><span data-stu-id="b3a74-104">This class saves the event data directly into the BAM Primary Import Database in the context of the current transaction of the application (if present).</span></span>  
  
 <span data-ttu-id="b3a74-105">如果在此操作期间发生错误，方法调用将在调用应用程序中引发异常。</span><span class="sxs-lookup"><span data-stu-id="b3a74-105">If any error happens during this operation, the method call will throw an exception back in the calling application.</span></span> <span data-ttu-id="b3a74-106">例如，如果传入 UpdateActivity 的项的名称与 BAM 活动定义不匹配，或者您还未部署 BAM 定义，将会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="b3a74-106">This will happen for example if the name of an item passed in UpdateActivity mismatches the BAM Activity Definition, or you did not deploy the BAM Definition yet.</span></span> <span data-ttu-id="b3a74-107">这样，在保存 BAM 数据时调用应用程序能够捕获所有错误并从这些错误中恢复，这使以后的管理工作变得更简单。</span><span class="sxs-lookup"><span data-stu-id="b3a74-107">This allows the calling application to catch and recover from any errors when saving the BAM data, which results in much easier management later.</span></span>  
  
 <span data-ttu-id="b3a74-108">同步保存数据可能会影响性能，这是因为调用应用程序必须等待 BAM 执行完所有存储过程和触发器。</span><span class="sxs-lookup"><span data-stu-id="b3a74-108">Saving the data synchronously might have a performance impact, because the calling application has to wait until BAM executes all stored procedures and triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3a74-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3a74-109">See Also</span></span>  
 [<span data-ttu-id="b3a74-110">异步业务事件跟踪</span><span class="sxs-lookup"><span data-stu-id="b3a74-110">Asynchronous Business Event Tracking</span></span>](../core/asynchronous-business-event-tracking.md)