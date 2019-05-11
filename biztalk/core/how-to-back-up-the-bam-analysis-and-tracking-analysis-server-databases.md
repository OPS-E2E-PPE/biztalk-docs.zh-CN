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
ms.openlocfilehash: f2fdd707375404f26f9310c6c2d38a6f2dfcb4ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387119"
---
# <a name="how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases"></a>如何备份 BAM 分析数据库和跟踪分析服务器数据库
业务活动监视 (BAM) 分析数据库和跟踪分析服务器数据库存储在 SQL Server Analysis Services 多维数据集中的内容。 备份 BizTalk Server 作业不会备份这些数据库。 相反，若要备份这些数据库，必须使用 SQL Server 分析管理器。  
  
 备份这些数据库后，你可能想要清除 OLAP 多维数据集。 当清除 OLAP 多维数据集时，您还必须执行以下步骤：  
  
1. 在清除 OLAP 多维数据集之前, BAMStarSchema 数据库中截断要清除的多维数据集的事实表。 表命名约定为"bam_*\<多维数据集名称\>*_Facts"。  
  
2. 清除 OLAP 多维数据集后，必须完全处理活动的、 已完成的、 和虚拟多维数据集。  
  
   有关备份分析数据库的说明，请参阅"存档 Analysis Services 数据库"SQL Server 联机丛书中。  
  
   **计划备份 BAM 数据库**  
  
   如果在使用 BAM，验证备份包在按计划运行时运行两 BAM 多维数据集处理和数据维护数据转换服务 (DTS) 包。  
  
   若要确保所有 BAM 数据库一致的架构，备份 BAM 数据库和 DTS 包每次部署或取消部署 BAM 活动。  
  
   备份 BAM 分析数据库和 BAMStarSchema 数据库每次部署或取消部署 BAM 视图。  
  
   备份 BAM 数据库按以下顺序：  
  
3. 运行备份 BizTalk Server 作业备份 BAMPrimaryImport 数据库和其他 BizTalk Server 数据库。  
  
4. 运行的所有活动的 BAM 数据维护 DTS 包。  
  
    这些步骤并入 DTS 包，并计划定期运行的包。 若要确保数据完整性，请确保没有其他 BAM 多维或数据维护 DTS 包运行时此备份包在按计划运行。  
  
    若要确保 BAMArchive 数据库发生故障时，备份 BAMArchive 数据库将分区复制到 BAMArchive 数据库之后但在从 BAMPrimaryImport 数据库删除分区之前能够恢复完整的已存档的数据集。 若要执行此操作，修改数据维护 DTS 包的每个活动以插入一个步骤来备份 BAMArchive 数据库之前，在 DTS 包的最后一步"结束存档"。  
  
5. 备份 BAMAnalysis 数据库，然后备份 BAMStarSchema 数据库。  
  
## <a name="see-also"></a>请参阅  
 [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)