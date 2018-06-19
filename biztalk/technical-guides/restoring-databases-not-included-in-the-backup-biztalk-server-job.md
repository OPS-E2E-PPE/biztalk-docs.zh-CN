---
title: 不还原数据库备份的 BizTalk Server 作业中包含 |Microsoft 文档
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
ms.openlocfilehash: 3277886207e04a30fec8bb61f29b5fe8c5ec3545
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302117"
---
# <a name="restoring-databases-not-included-in-the-backup-biztalk-server-job"></a>还原数据库备份的 BizTalk Server 作业中不包括
本部分介绍如何还原总体 BizTalk 解决方案的一部分，但不是会备份 BizTalk Server 作业身份备份的数据库。 使用以下除外备份 BizTalk Server 作业，将备份作为 BizTalk 解决方案的一部分的所有数据库：  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services 数据库  
  
-   BAM 数据库时 BAM 启用和配置使用 BM.exe  
  
 本部分还描述如何在还原上面列出的数据库后更新数据库引用，并包含有关解决不完整 BAM 活动实例的信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [还原 Analysis Services 和支持的数据库](../technical-guides/restoring-analysis-services-and-supporting-databases.md)  
  
-   [更新数据库引用](../technical-guides/updating-database-references.md)  
  
-   [如何解决不完整 BAM 活动实例](../technical-guides/how-to-resolve-incomplete-bam-activity-instances.md)