---
title: "OrchestrationEventStream |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7c63610-6344-4b71-8d65-3add7883bc79
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc1fd0dc229c38b3a060c75a9c584259175d72fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="orchestrationeventstream"></a><span data-ttu-id="80fa6-102">OrchestrationEventStream</span><span class="sxs-lookup"><span data-stu-id="80fa6-102">OrchestrationEventStream</span></span>
<span data-ttu-id="80fa6-103">OrchestrationEventStream (OES) API 用于应用程序运行在安装有 BizTalk Server 的计算机上，且您正在跟踪属于 BizTalk 业务流程事务的项的情况下。</span><span class="sxs-lookup"><span data-stu-id="80fa6-103">You use the OrchestrationEventStream (OES) API when your application runs on a computer on which BizTalk Server is installed and you are tracking items that are part of BizTalk orchestration transactions.</span></span>  
  
 <span data-ttu-id="80fa6-104">OES API 最初将跟踪数据存储到 BizTalk MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="80fa6-104">The OES API stores tracking data first in the BizTalk MessageBox database.</span></span> <span data-ttu-id="80fa6-105">跟踪数据解码服务 (TDDS) 会定期处理这些数据，并将其持久化到 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="80fa6-105">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
 <span data-ttu-id="80fa6-106">OES API 位于 Microsoft.BizTalk.Bam.EventObservation 命名空间。</span><span class="sxs-lookup"><span data-stu-id="80fa6-106">The OES API is found in the Microsoft.BizTalk.Bam.EventObservation namespace.</span></span> <span data-ttu-id="80fa6-107">若要使用该 API，必须将 Microsoft.Biztalk.BAM.Xlangs.dll 添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="80fa6-107">To use the API you must add the Microsoft.Biztalk.BAM.Xlangs.dll to your project.</span></span>  
  
## <a name="oes-members"></a><span data-ttu-id="80fa6-108">OES 成员</span><span class="sxs-lookup"><span data-stu-id="80fa6-108">OES Members</span></span>  
 <span data-ttu-id="80fa6-109">OES API 派生自 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) 类。</span><span class="sxs-lookup"><span data-stu-id="80fa6-109">The OES API is derived from the [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) class.</span></span>  
  
 <span data-ttu-id="80fa6-110">OES 实现了 EventStream 类中的所有方法，但有以下例外情况：</span><span class="sxs-lookup"><span data-stu-id="80fa6-110">OES implements all of the methods within the EventStream class, but has the  following exception in behaviors:</span></span>  
  
 <span data-ttu-id="80fa6-111">**公共的静态 void clear （);**</span><span class="sxs-lookup"><span data-stu-id="80fa6-111">**public static void Clear();**</span></span>  
  
 <span data-ttu-id="80fa6-112">无操作。</span><span class="sxs-lookup"><span data-stu-id="80fa6-112">No operation.</span></span>  
  
 <span data-ttu-id="80fa6-113">**公共的静态 void flush （);**</span><span class="sxs-lookup"><span data-stu-id="80fa6-113">**public static void Flush();**</span></span>  
  
 <span data-ttu-id="80fa6-114">无操作。</span><span class="sxs-lookup"><span data-stu-id="80fa6-114">No operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80fa6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80fa6-115">See Also</span></span>  
 [<span data-ttu-id="80fa6-116">EventStream 类</span><span class="sxs-lookup"><span data-stu-id="80fa6-116">EventStream Classes</span></span>](../core/eventstream-classes.md)