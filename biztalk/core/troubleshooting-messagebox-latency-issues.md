---
title: MessageBox 延迟问题疑难解答 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9eb5789-80bd-40d4-8c27-7ae117fd9232
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e37fc970230bf218bcfd820611fb6b87322e535
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279869"
---
# <a name="troubleshooting-messagebox-latency-issues"></a>MessageBox 延迟问题疑难解答
理想情况下，在将消息发布到 MessageBox 数据库后，所有消息都将被处理和传送，并且 MessageBox 数据库永远不会变得过大。 MessageBox 中所有不再被引用的消息将立即由定期清理 MessageBox 数据库表的 SQL 代理作业删除。  
  
 但是在实际情况下，通常不是以可预测的线性方式来接收消息，并且 SQL 代理作业需要时间来清理 MessageBox 数据库表。  
  
 因此在某些情况下，MessageBox 可能会迅速变得相当大。  
  
 以下各项原因可能会导致 MessageBox 变得过大并因此影响整体性能：  
  
-   **"允许主机跟踪"选项设置了 Biztalk 主机实例停止**。 这是负责将跟踪数据从 MessageBox 数据库移至 Biztalk 跟踪数据库 (BizTalkDTADb) 的主机。  
  
-   **SQL Server 代理未运行**可能的原因是未运行负责将数据从 MessageBox 数据库移到 [随后清除已移动的数据在 MessageBox] BizTalkDTADb 数据库的 SQL 作业。 SQL 代理服务必须始终运行以避免出现此问题。  
  
-   **SQL Server 作业被禁用**即使 SQL Server 代理正在运行，则务必无默认 SQL Server 作业被禁用。  
  
-   **BizTalkDTADb 数据库增长过**可能的原因是 BizTalkDTADb 数据库增长过大，导致插入到 BizTalkDTADb 数据库需要更长时间。 发生这种情况时，通过跟踪数据传送服务 (TDDS) 移动数据的速度会减慢，从而导致在 MessageBox 数据库中产生积压。 要避免出现这种问题，SQL Server 必须定期对 BizTalkDTADb 数据库执行存档和清除作业。  
  
-   **过多的磁盘 I/O 延迟**如果到 MessageBox 数据库的数据的传入速率速度快于系统可以处理并将数据移到 BizTalkDTADb 数据库积压工作可以建立 MessageBox 数据库中。 如果积压的数据持续增加，则这将是一个很严重的问题，并且系统性能将随着时间推移而下降。 一种缓解此问题的方法是安装速度较快的磁盘和/或升级硬件，以帮助确保系统能够消除随着时间的推移而产生的任何消息积压现象。  
  
## <a name="plan-for-the-future"></a>未来规划  
 即使按照上述所有的最佳实践执行操作，随着时间的推移，移至 BizTalkDTADb 数据库的跟踪数据量也将变得很大。 实施数据库维护计划以定期存档跟踪数据是非常重要的，以使系统的执行性能保持最佳。  
  
 可在 BizTalkDTADb 数据库中保留的历史数据量取决于通过系统推送的消息量。 对于工作负担不重和吞吐量不高的系统，数据库的增长速度会较慢，并且可以将更多的历史数据保留在 BizTalkDTADb 数据库中。  
  
 建议在 BizTalkDTADb 数据库中保留尽可能少的数据，以免影响运行时性能。