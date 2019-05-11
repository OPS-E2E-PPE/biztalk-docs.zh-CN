---
title: 备份和还原 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe03a75a-1ea6-4ccc-9543-7989ec6b1cff
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b04e6db4a125b2c90e3417c53d77b10e06f63ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358684"
---
# <a name="backing-up-and-restoring-biztalk-server"></a>备份和还原 BizTalk Server
如果发生硬件故障，具有良好的备份 BizTalk Server 数据库和组件非常重要。 一个好的备份以便可以使用很少或没有数据丢失中恢复。 如何还原 BizTalk Server 取决于发生硬件故障在系统上安装了什么组件。 本指南涉及以下硬件故障情形：  
  
 **运行 BizTalk Server 的计算机发生硬件故障**  
  
 运行 BizTalk Server 的计算机发生硬件故障可能会导致系统停机时间，或如果 BizTalk 组不具备高可用性设计性能下降。 有关如何创建高度可用的 BizTalk 组的详细信息，请参阅[以实现高可用性规划](../core/planning-for-high-availability3.md)。  
  
 若要确保您可以替换在硬件故障后运行 BizTalk Server 的计算机，必须在该计算机上备份 BizTalk Server 组件。 有关如何备份和还原运行 BizTalk Server 的计算机的详细信息，请参阅[Backing Up a 计算机运行 BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md)并[恢复计算机运行的 BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md)。  
  
 **运行 SQL Server 的计算机发生硬件故障**  
  
 可以通过使用 SQL Server 群集中运行 SQL Server 的计算机发生硬件故障的风险降至最低。 即使使用 SQL Server 群集，但是，有可能的情况下包含 BizTalk Server 数据库的 SQL 服务器遇到了不可恢复的硬件故障时。 例如，整个数据层发生故障。 在这些情况下，必须通过还原备份的数据库的最新一套恢复 BizTalk 组。  
  
 有关为 BizTalk Server 数据库提供容错功能的详细信息，请参阅[的 BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)。 在发生灾难性 SQL Server 故障发生导致停机，应按照中的说明[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)。  
  
 如果遇到硬件故障，安装 SQL Server 和 BizTalk Server 的计算机上，您应还原 BizTalk Server 数据库中，然后再恢复 BizTalk Server 组件。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [清单：备份和还原](../core/checklist-backup-and-restore.md)  
  
-   [备份和还原的最佳做法](../core/best-practices-for-backup-and-restore.md)  
  
-   [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)  
  
-   [运行 BizTalk Server 的计算机的灾难恢复](../core/disaster-recovery-for-computers-running-biztalk-server.md)  
  
-   [对运行 BizTalk Server 的计算机进行备份](../core/backing-up-a-computer-running-biztalk-server.md)  
  
-   [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)