---
title: 测试结果：网络关键绩效指标 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9bdbc2df-9d19-4ae8-b540-ec1b9a7cdbe9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdf346b1a13838ca8e3ba3cbd8ec208e33670f6c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400651"
---
# <a name="test-results-networking-key-performance-indicators"></a>测试结果：网络关键性能指标
本主题概述了网络关键性能指标 (KPI) 的测试方案期间观察到。 这些测试评估网络性能，因为通过测量**\Network 接口 (\*) \Bytes Total/sec**性能监视计数器和通过测量**SQL Network Interface\Bytes Total/sec （平均值）** 返回的 VSTS 2008 负载测试控制器。  
  
## <a name="summary-of-network-key-performance-indicators"></a>网络关键性能指标的摘要  
 **网络关键绩效指标 – 比较**BizTalk Server 的 HYPER-V 虚拟机上运行的网络吞吐量已观察到范围从大约 70%到 96%的物理 BizTalk 服务器上实现的网络吞吐量具体取决于特定的测试环境。 HYPER-V 虚拟机上运行的 SQL Server 的网络吞吐量已观察到范围从大约 68%到 81%的实现在物理 SQL 服务器上，再次根据特定的测试环境的网络吞吐量。 可以将观测到的网络吞吐量增量归为 HYPER-V 虚拟机监控程序的资源要求。  
  
 按照中的步骤[网络优化](../technical-guides/network-optimizations.md)若要最大化网络吞吐量上的 HYPER-V 虚拟机由度量**\Network 接口 (\*) \Bytes 总数/秒**  
  
 下图说明了各种测试平台上的网络性能：  
  
 ![网络关键性能指标](../technical-guides/media/networkkpi.gif "NetworkKPI")  
  
 下表说明了每个配置的收集 KPI 的相对性能。 每个结果集计算的基线配置 KPI 百分比  
  
|KPI|虚拟 BizTalk/物理 SQL|在单独的主机的虚拟 BizTalk/虚拟 SQL|合并环境上的虚拟 BizTalk/虚拟 SQL|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|\Network Interface(*)\Bytes Total/sec (Total Avg Across all BizTalk Servers)|96%|82.1%|70.2%|  
|SQL Network Interface\Bytes Total/sec (Avg )|95.5%|81.2%|68.4%|  
  
 有关如何评估网络性能的详细信息，请参阅**测量网络性能**主题的部分[核对清单：Hyper V 上测量性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)。