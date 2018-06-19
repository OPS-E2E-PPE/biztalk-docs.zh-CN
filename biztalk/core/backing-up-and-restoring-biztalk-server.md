---
title: 备份和还原 BizTalk Server |Microsoft 文档
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
ms.openlocfilehash: 1adac25b23c69b51e07ed5f30768d046a453887a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230781"
---
# <a name="backing-up-and-restoring-biztalk-server"></a>备份和还原 BizTalk Server
在发生硬件故障时，对 BizTalk Server 数据库和组件有完善的备份至关重要。 完善的备份使您能够进行恢复，而数据损失很少甚至毫无损失。 如何还原 BizTalk Server，取决于发生硬件故障的系统上安装了什么组件。 本指南涉及以下硬件故障情形：  
  
 **在运行 BizTalk Server 的计算机的硬件故障**  
  
 如果 BizTalk 组不具备高可用性设计，那么运行 BizTalk Server 的计算机发生硬件故障可能会导致系统停机或性能下降。 有关如何创建高度可用的 BizTalk 组的详细信息，请参阅[高可用性规划](../core/planning-for-high-availability3.md)。  
  
 要确保在硬件故障后可以更换运行 BizTalk Server 的计算机，必须备份计算机上的 BizTalk Server 组件。 有关如何备份和还原运行 BizTalk Server 的计算机的详细信息，请参阅[Backing Up a 计算机运行 BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md)和[恢复计算机运行的 BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md)。  
  
 **在运行 SQL Server 的计算机的硬件故障**  
  
 通过使用 SQL Server 群集，可以尽可能减少运行 SQL Server 的计算机发生硬件故障的风险。 不过，在使用 SQL Server 群集时，可能会出现包含 BizTalk Server 数据库的 SQL 服务器发生不可恢复的硬件故障的情况。 例如，整个数据层发生故障。 在这种情况下，必须通过还原最新的一组备份的数据库来恢复 BizTalk 组。  
  
 有关为 BizTalk Server 数据库提供容错功能的详细信息，请参阅[BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)。 发生灾难性的 SQL Server 故障发生停机时间，应按照中的说明[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)。  
  
 如果既安装了 SQL Server 又安装了 BizTalk Server 的计算机发生硬件故障，应该还原 BizTalk Server 数据库，然后恢复 BizTalk Server 组件。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [清单： 备份和还原](../core/checklist-backup-and-restore.md)  
  
-   [备份和还原最佳实践](../core/best-practices-for-backup-and-restore.md)  
  
-   [备份和还原的 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)  
  
-   [运行 BizTalk Server 的计算机的灾难恢复](../core/disaster-recovery-for-computers-running-biztalk-server.md)  
  
-   [备份运行 BizTalk Server 的计算机](../core/backing-up-a-computer-running-biztalk-server.md)  
  
-   [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)