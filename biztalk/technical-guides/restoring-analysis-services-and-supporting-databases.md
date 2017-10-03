---
title: "还原 Analysis Services 和支持的数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 490ad0fb-7805-4ebc-9bc5-117d52d7c3a8
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da16bde7b69071b71b794c4c46407feab3ef4512
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="restoring-analysis-services-and-supporting-databases"></a>还原 Analysis Services 和支持的数据库
有两个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，必须在灾难恢复方案中还原的 Analysis Services 数据库：  
  
-   BAM 分析 (BAMAnalysis)  
  
-   跟踪 Analysis Server (BizTalkAnalysisdb)  
  
 BAM[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库可能会进行备份的备份 BizTalk Server 作业一部分如果 BAM 已启用但尚未配置。  
  
> [!NOTE]  
>  BAM 主导入始终备份数据库的备份 BizTalk Server 作业一部分因为它参与 DTC 事务。  
  
 以下的 BAM 数据库将 BizTalk Server 中备份作业的一部分，如果 BAM 已启用但尚未配置：  
  
-   BAMStarSchema  
  
-   BAMArchive  
  
 按照中的步骤[如何还原数据库备份 BizTalk Server 作业](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)还原这些数据库。  
  
 **否则为**  
 **如果 BAM 已启用，而且还配置使用 BM.exe，正确的一套 BAM 数据库必须为一组一起还原。** 若要确保恢复一组完整的已存档的数据，BAM 存档备份数据库分区复制到 BAM 存档之后，但之前从 BAM 主导入数据库中删除分区。 通过修改每个活动数据维护 SSIS 包的方法是插入 BAM 存档数据库备份，最后一个步骤"结束存档。"之前的步骤执行此操作  
  
 BAM 数据库还原过程是： 如果 x 的最后备份日期还原 BAM 主导入数据库，则将对应的 BAM 存档和 BAM 星型架构的数据库的副本还原到数据维护 SSIS 包时的最新日期在 x 的日期之前运行。  
  
 标识正确的一套 BAM 数据库之后，将还原[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services 数据库中所述使用标准过程[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]有关还原联机丛书[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services 数据库。  
  
## <a name="see-also"></a>另请参阅  
 [备份 BAM 分析和跟踪 Analysis Server 数据库](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)