---
title: 还原 Analysis Services 和支持数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 490ad0fb-7805-4ebc-9bc5-117d52d7c3a8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa686dd149643c10760156018b72af141c2081ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291289"
---
# <a name="restoring-analysis-services-and-supporting-databases"></a>还原 Analysis Services 和支持数据库
有两个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，必须在灾难恢复方案中还原的 Analysis Services 数据库：  
  
- BAM 分析 (BAMAnalysis)  
  
- 跟踪分析服务器 (BizTalkAnalysisdb)  
  
  BAM[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库可能备份作为备份 BizTalk Server 作业的一部分如果已启用但未配置 BAM。  
  
> [!NOTE]  
>  BAM 主导入数据库是始终作为备份的备份 BizTalk Server 作业一部分因为它参与 DTC 事务。  
  
 如果已启用但未配置 BAM，以下 BAM 数据库将成为备份 BizTalk Server 作业的一部分：  
  
- BAMStarSchema  
  
- BAMArchive  
  
  按照中的步骤[如何还原数据库备份 BizTalk Server 作业中](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)来还原这些数据库。  
  
  **否则为**  
  **如果 BAM 已启用，并且也使用 BM.exe 进行配置，一组正确的 BAM 数据库必须作为一组一起还原。** 若要确保恢复了一整套的存档数据，BAM 存档数据库备份分区复制到 BAM 存档之后，但之前从 BAM 主导入数据库删除分区。 这被通过修改每个活动的数据维护 SSIS 包的方法是插入一个步骤来备份 BAM 存档数据库之前最后一个步骤"结束存档"。  
  
  BAM 数据库的还原过程是：如果 x 的最后备份日期还原 BAM 主导入数据库，则相对应的 BAM 存档和 BAM 星型架构数据库的副本还原到 x 的日期之前的数据维护 SSIS 包运行时的最晚日期。  
  
  标识一组正确的 BAM 数据库后，将还原[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]并[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services 数据库使用标准过程中所述[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]还原联机丛书[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services 数据库。  
  
## <a name="see-also"></a>请参阅  
 [备份 BAM 分析和跟踪 Analysis Server 数据库](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)