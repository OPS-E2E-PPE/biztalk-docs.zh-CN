---
title: "测试结果： 内存关键绩效指标 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 224c40e5-08a7-4d30-b03a-4b6add5cde1f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4edf88023ee9e30e7fd0c808346b6231112f8ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="test-results-memory-key-performance-indicators"></a>测试结果： 内存关键绩效指标
本主题总结了内存关键绩效指标 (KPI) 的测试方案期间观察到。 这些测试计算由可用内存**\Memory\Available Mbytes**性能监视器计数器。  
  
## <a name="summary-of-memory-key-performance-indicators"></a>内存关键绩效指标的摘要  
 **比较内存关键绩效指标 –**的总内存供 SQL Server 和 BizTalk Server 测量**\Memory\Available Mbytes**所有性能监视器计数器是相当一致测试方案。 中可用的平均内存到物理 BizTalk Server 计算机以及可用于虚拟机上运行的 BizTalk Server 计算机的平均内存的区别是因为，两个物理 BizTalk Server 计算机用于测试时三个虚拟机上运行的 BizTalk Server 计算机已用于测试。  
  
 下图阐释了在不同的测试平台上的内存性能：  
  
 ![内存关键绩效指标](../technical-guides/media/memorykpi.gif "MemoryKPI")  
  
 下表说明了每个配置的收集 KPI 的相对性能。 每个结果集计算的基线配置 KPI 百分比  
  
|KPI|虚拟 BizTalk/物理 SQL|在单独的主机的虚拟 BizTalk/虚拟 SQL|合并环境上的虚拟 BizTalk/虚拟 SQL|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|SQL Server 可用内存 （mb 为单位） 每个服务器|100.1%|97.1%|103.2%|  
|总 BizTalk 可用内存 （mb 为单位）|88.3%|95.9%|96%|  
|平均每个服务器 / BizTalk 可用内存 （mb 为单位）|58.9%|63.9%|64%|  
  
 有关如何评估内存性能的详细信息，请参阅**度量内存性能**主题的部分[清单： HYPER-V 上的测量性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)。