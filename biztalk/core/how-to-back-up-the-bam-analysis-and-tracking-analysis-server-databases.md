---
title: 如何备份 BAM 分析和跟踪分析服务器数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, DTS packages
- backing up [BAM], Tracking Analysis Server database
- backing up [BAM], OLAP cubes
- backing up [BAM], DTS packages
- purging, OLAP cubes
- Analysis database [BAM], backing up
- scheduling, BAM backups
- backing up [BAM], Analysis database
- OLAP cubes, purging
- backing up, BAM
- backing up [BAM], database order
- DTS packages, backing up
- backing up [BAM], Star Schema database
- backing up [BAM], scheduling
- Tracking Analysis Server database [BAM], backing up
- Star Schema database [BAM], backing up
ms.assetid: d39e3491-ab54-44f2-990a-7b8ee86f0501
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1b7dca60859d0dcda69d6c9110b4be08d90586b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983374"
---
# <a name="how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases"></a>如何备份 BAM 分析数据库和跟踪分析服务器数据库
业务活动监视 (BAM) 分析数据库和跟踪分析服务器数据库存储 SQL Server Analysis Services 多维数据集中的内容。 备份 BizTalk Server 作业不备份这些数据库。 若要备份这些数据库，必须使用 SQL Server 分析管理器。  
  
 备份完这些数据库后，您可能希望清除 OLAP 多维数据集。 清除 OLAP 多维数据集时，还必须执行以下步骤：  
  
1. 在清除 OLAP 多维数据集之前，在 BAMStarSchema 数据库中截断要清除的多维数据集的事实表。 表命名约定为"bam_*\<多维数据集名称\>*_Facts"。  
  
2. 清除完 OLAP 多维数据集后，必须彻底处理活动的、已完成的和虚拟的多维数据集。  
  
   有关备份分析数据库的说明，请参阅 SQL Server 联机丛书中的“存档 Analysis Services 数据库”。  
  
   **计划备份 BAM 数据库**  
  
   如果要使用 BAM，请验证备份包在按计划运行时 BAM 多维数据集处理和数据维护数据转换服务 (DTS) 包都不会运行。  
  
   若要确保所有 BAM 数据库的架构一致，请在每次部署或取消部署 BAM 活动时都备份 BAM 数据库和 DTS 包。  
  
   每次部署或取消部署 BAM 视图时都备份 BAM 分析数据库和 BAMStarSchema 数据库。  
  
   按以下顺序备份 BAM 数据库：  
  
3. 运行备份 BizTalk Server 作业备份 BAMPrimaryImport 数据库和其他 BizTalk Server 数据库。  
  
4. 运行所有活动的 BAM 数据维护 DTS 包。  
  
    将这些步骤并入 DTS 包，然后安排该 DTS 包定期运行。 为了确保数据完整性，请确保此备份包在按计划运行时没有其他 BAM 多维数据集或数据维护 DTS 包在运行。  
  
    若要确保 BAMArchive 数据库发生故障时能够完整地恢复存档数据，请在将分区复制到 BAMArchive 数据库之后，且在从 BAMPrimaryImport 数据库删除分区之前备份 BAMArchive 数据库。 为此，请修改每个活动的数据维护 DTS 包，在 DTS 包的最后一步“结束存档”之前插入备份 BAMArchive 数据库这一步。  
  
5. 备份 BAMAnalysis 数据库，然后备份 BAMStarSchema 数据库。  
  
## <a name="see-also"></a>请参阅  
 [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)