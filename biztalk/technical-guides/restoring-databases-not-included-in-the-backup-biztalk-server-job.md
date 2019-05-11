---
title: 还原数据库不包含在备份 BizTalk Server 作业 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7141980-d4a6-4409-be9b-c94a7f733376
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e4555b9a3f635d733d698109614c1ed673125f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291253"
---
# <a name="restoring-databases-not-included-in-the-backup-biztalk-server-job"></a>还原数据库不包含在备份 BizTalk Server 作业
本部分介绍如何还原作为整体的 BizTalk 解决方案的一部分，但不是由备份 BizTalk Server 作业备份的数据库。 将备份作为 BizTalk 解决方案的一部分的所有数据库使用备份 BizTalk Server 作业，以下除外：  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services 数据库  
  
- 如果启用了 BAM，并且使用 BM.exe 配置 BAM 数据库  
  
  本部分还介绍如何还原上面列出的数据库后更新数据库的引用，并且包括有关解决不完整的 BAM 活动实例的信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [还原 Analysis Services 和支持数据库](../technical-guides/restoring-analysis-services-and-supporting-databases.md)  
  
-   [更新数据库引用](../technical-guides/updating-database-references.md)  
  
-   [如何解析不完整的 BAM 活动实例](../technical-guides/how-to-resolve-incomplete-bam-activity-instances.md)