---
title: 更新对 BAM 分析服务器和星型架构数据库名称的引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 319caa26-1292-4453-a316-efca4fbffdb6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6052da82dd121d25f4cb160521d7c31f646a2305
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400594"
---
# <a name="update-references-to-the-bam-analysis-server-and-star-schema-database-names"></a>更新对 BAM 分析服务器和星型架构数据库名称
如果备份了 BAM 分析数据库，则在系统或数据发生故障，可以将该备份还原到另一台计算机，并可以重命名该备份。  
  
 若要还原 BAM 分析和星型架构数据库，请执行中的步骤[如何还原数据库备份 BizTalk Server 作业中](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)。 此外，还必须更新 BAM[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]用新的服务器名称和数据库名称的 Integration Services (SSIS) 包。  
  
## <a name="how-to-update-references-to-bam-analysis-server-and-star-schema-database-names"></a>如何更新对 BAM 分析服务器和星型架构数据库名称的引用  
 有关如何更新对 BAM 分析服务器数据库的引用的说明，请参阅[更新到新的 BAM 分析数据库的引用](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate)。 有关如何更新对 BAM 星型架构数据库的引用的说明，请参阅[更新到新的 BAM 星型架构数据库的引用](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate)。