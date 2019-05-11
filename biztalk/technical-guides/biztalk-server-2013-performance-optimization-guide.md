---
title: BizTalk Server 2013 性能优化指南 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5069b7f-a1f1-483e-9b37-1bfe853b5352
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72c498ee5d032666449b838bfd3e852b2619fca6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393558"
---
# <a name="biztalk-server-2013-performance-optimization-guide"></a><span data-ttu-id="ed384-102">BizTalk Server 2013 性能优化指南</span><span class="sxs-lookup"><span data-stu-id="ed384-102">BizTalk Server 2013 Performance Optimization Guide</span></span>
<span data-ttu-id="ed384-103">![BTS 白皮书](../technical-guides/media/btswhitepaper.jpg "BTSWhitepaper")</span><span class="sxs-lookup"><span data-stu-id="ed384-103">![BTS Whitepaper](../technical-guides/media/btswhitepaper.jpg "BTSWhitepaper")</span></span>  
  
## <a name="microsoft-biztalk-server-2013-performance-optimization-guide"></a><span data-ttu-id="ed384-104">Microsoft BizTalk Server 2013 性能优化指南</span><span class="sxs-lookup"><span data-stu-id="ed384-104">Microsoft BizTalk Server 2013 Performance Optimization Guide</span></span>  
 <span data-ttu-id="ed384-105">**摘要**</span><span class="sxs-lookup"><span data-stu-id="ed384-105">**Summary**</span></span>  
  
 <span data-ttu-id="ed384-106">BizTalk Server 2013 性能优化指南包含有关优化 BizTalk Server 性能，基于实践经验的 IT 专业人员已广泛使用 BizTalk Server 的规范性指南。</span><span class="sxs-lookup"><span data-stu-id="ed384-106">The BizTalk Server 2013 Performance Optimization Guide contains prescriptive guidance for optimizing BizTalk Server performance, based upon hands-on experience of IT professionals who have worked extensively with BizTalk Server.</span></span> <span data-ttu-id="ed384-107">本指南包含四个主要部分：查找并消除瓶颈、 优化性能，缩放生产 BizTalk Server 环境中和 BizTalk Server 性能测试方法。</span><span class="sxs-lookup"><span data-stu-id="ed384-107">This guide contains four main sections: Finding and Eliminating Bottlenecks, Optimizing Performance, Scaling a Production BizTalk Server Environment, and BizTalk Server Performance Testing Methodology.</span></span>  
  
 <span data-ttu-id="ed384-108">操作系统、 SQL Server 配置和其他性能设置也适用于 BizTalk Server 2013 R2。</span><span class="sxs-lookup"><span data-stu-id="ed384-108">The operating system, SQL Server configuration, and other performance settings also apply to BizTalk Server 2013 R2.</span></span>  
  
 <span data-ttu-id="ed384-109">若要查看该文档，请下载[Microsoft BizTalk Server 2013 性能优化指南](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/BizTalkServer2013-PerformanceGuide.docx)Word 文档。</span><span class="sxs-lookup"><span data-stu-id="ed384-109">To review the document, please download the [Microsoft BizTalk Server 2013 Performance Optimization Guide](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/BizTalkServer2013-PerformanceGuide.docx) Word document.</span></span>