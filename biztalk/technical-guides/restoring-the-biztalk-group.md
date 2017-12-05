---
title: "还原 BizTalk 组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14a9af44-d6de-49c7-9600-21ece389727f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e8d1741d89e8326cc68906644cf34e71bfcc8e1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="restoring-the-biztalk-group"></a>还原 BizTalk 组
BizTalk 组都由套[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services 数据库、 SSIS 包和 SQL 代理作业。 本部分介绍还原 BizTalk 组的过程。  
  
 事件中适配器转换到目标系统 （灾难恢复站点） 是必需的则必须完成以下步骤：  
  
1.  还原[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和 Analysis Services 数据库。  
  
2.  还原 BizTalk Server 运行时服务器和应用程序。  
  
 在灾难恢复站点上，在完成这些步骤，建立 BizTalk 组[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以配置运行时服务器，并且可以将应用程序部署到 BizTalk 组。 本部分中的主题介绍此过程的详细信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在源系统上停止应用程序处理](../technical-guides/stopping-application-processing-on-the-source-system.md)  
  
-   [如何在备份 BizTalk Server 作业中还原数据库](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)  
  
-   [还原备份 BizTalk Server 作业中不包含的数据库](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)