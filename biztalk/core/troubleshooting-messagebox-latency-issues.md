---
title: MessageBox 延迟问题疑难解答 |Microsoft Docs
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
ms.openlocfilehash: 1d62bbe76a618b03c4cd57d764152e250ecbc3ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295710"
---
# <a name="troubleshooting-messagebox-latency-issues"></a>MessageBox 延迟问题疑难解答
在理想情况下，所有消息将进行处理和传递只要它们所发布到 MessageBox 数据库和 MessageBox 数据库将会永远不会增长过大。 定期清理 MessageBox 数据库表的 SQL 代理作业会立即删除不再被引用的任何消息在 MessageBox 中。  
  
 但是，在实际情况下，消息不会以可预测的线性方式通常接收和 SQL 代理作业需要时间来清理 MessageBox 数据库表。  
  
 因此，在某些情况下;MessageBox 可以非常快速地增长相当大。  
  
 以下各项可能会导致 MessageBox 变得过大并因此影响整体性能：  
  
-   **发送设置"允许主机跟踪"选项的 Biztalk 主机实例停止**。 这是负责将跟踪数据从 MessageBox 数据库移至 Biztalk 跟踪数据库 （biztalkdtadb） 的主机。  
  
-   **SQL Server 代理未运行**未运行的 SQL 作业负责将数据从 MessageBox 数据库移至 BizTalkDTADb 数据库 [随后清除所移动的数据在 MessageBox 中] 如果发生这种情况。 它是命令性 SQL 代理服务运行所有的时间，若要避免此问题。  
  
-   **SQL Server 作业被禁用**即使 SQL Server 代理正在运行，也是命令性，无默认 SQL Server 作业被禁用。  
  
-   **BizTalkDTADb 数据库增长过快**如果 BizTalkDTADb 数据库变得非常大，导致插入到 BizTalkDTADb 数据库需要更长时间发生这种情况。 在此情况下移动数据的方式来跟踪数据传送服务 (TDDS) 速度变慢，导致 MessageBox 数据库中的积压工作逐渐累积。 若要避免此问题是必须运行 SQL server 存档和清除作业定期对 BizTalkDTADb 数据库。  
  
-   **过多的磁盘 I/O 延迟**如果到 MessageBox 数据库中的数据的传入速率速度比系统可以处理更快，并将数据移到 BizTalkDTADb 数据库中，会产生积压在 MessageBox 数据库中。 如果积压工作数据持续增加，这是很严重的问题，随着时间的推移将会降低系统性能。 若要缓解此问题的一种方法是安装速度更快的磁盘和/或升级硬件，以帮助确保系统能够从任何消息积压现象随着时间的推移恢复。  
  
## <a name="plan-for-the-future"></a>规划未来  
 即使遵循所有遵循上述最佳做法，随时间的跟踪数据量移至 BizTalkDTADb 数据库将变得很大。 请务必实施数据库维护计划以定期存档跟踪数据，以便系统可以继续以最佳方式执行。  
  
 可以保留在 BizTalkDTADb 数据库中的历史数据量取决于通过系统推送的消息量。 对于系统，而不能用于高压力和数据库的增长速度较慢的吞吐量，并将有可能保留在 BizTalkDTADb 数据库中的多个历史数据。  
  
 建议保留在 BizTalkDTADb 数据库中的最小数据，以便运行时性能不丧失。