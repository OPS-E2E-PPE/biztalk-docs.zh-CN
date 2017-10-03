---
title: "备份和还原最佳实践 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aaf721ba-50ce-4334-b86d-e856b54d3486
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23657dcc843744741d6315b6a8c18ca3d35e1fe4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-backup-and-restore"></a>备份和还原的最佳实践
-   **创建备份和还原计划**  
  
     确保备份计划中指定以下内容：  
  
    -   存储备份的计算机  
  
    -   用于备份系统的程序  
  
    -   要进行备份的计算机  
  
    -   安排进行备份的时间  
  
    -   存档备份的非现场位置  
  
-   **记录写入的所有更改对你的 BizTalk Server 系统**  
  
     确保记下对系统所做的所有更改，比如已经应用的 Service Pack、修补程序和 QFE。 这对于使系统尽可能地还原到发生硬件故障之前的状态至关重要。  
  
-   **实现以下措施来帮助防止或最小灾难的影响：**  
  
    -   使软件和固件更新随时可用。  
  
    -   使所有软件安装磁盘随时可用。 这既包含系统软件（如专用驱动程序），也包含应用程序软件（如 BizTalk Server）。  
  
    -   制订计划主动监控服务器。 这点非常重要，因为在长达十分钟之内失败主机上的业务流程实例可能无法由另一台主机恢复。  
  
    -   保留硬件记录。  
  
    -   保留软件记录。  
  
-   **在你的组织在硬件或软件级别中实现容错**  
  
     实现群集和独立磁盘冗余阵列 (RAID) 有助于确保您的系统幸免于硬件故障。  
  
-   **存档在定期在安全的位置的备份介质**  
  
     制订定期存档备份媒体的计划并将存档保存在安全的非现场位置。 这样可以确保在需要备份时有可用备份。  
  
-   **验证你的备份的完整性，并没有错误发生**  
  
     监视所有备份作业，并确保备份作业在不发生任何错误的情况下完成。  
  
-   **提供的相同备用硬件**  
  
     保留完全相同的备用硬件可以确保快速更换有故障的硬件，以便实现快速恢复并重新运行。  
  
-   **文档和测试恢复过程**  
  
     理想情况下，灾难恢复测试应在运行生产系统之前进行。 制订好计划并执行预发布测试可确保您的 IT 员工能够恢复 BizTalk Server 系统。 这通常表示必须定期尝试将系统备份还原到您将使用的实际硬件  
  
-   **训练你的 IT 员工在灾难恢复过程**  
  
     确保您的 IT 员工在需要时随时可以对系统进行恢复。  
  
-   **练习从测试环境中的备份中还原**  
  
     在测试环境中练习还原 BizTalk Server 系统可确保在发生故障时能够将系统还原到生产环境中。  
  
## <a name="see-also"></a>另请参阅  
 [备份和还原 BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)