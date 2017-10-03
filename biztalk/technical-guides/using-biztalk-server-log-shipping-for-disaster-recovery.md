---
title: "使用 BizTalk Server 日志传送以实现灾难恢复 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d65015c-de53-4590-b644-5c2f66f763db
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16f2cf9e1d8b717ff42536ef9c0dba79132b9663
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-server-log-shipping-for-disaster-recovery"></a>使用 BizTalk Server 日志传送以实现灾难恢复
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]实现数据库的备用容量通过数据库使用日志传送。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]备份和还原的数据库和事务日志文件，允许备用服务器恢复数据库处理的事件中生产数据库服务器出现故障，可以自动执行日志传送。  
  
## <a name="how-log-shipping-works"></a>如何日志传送工作原理  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业由[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送同步在生产中使用的源服务器和目标服务器作为备用每隔 15 分钟默认情况下使用 （每个备份 BizTalk Server 作业运行的时间） 之间的数据。  
  
## <a name="using-log-shipping-for-disaster-recovery"></a>使用日志传送以实现灾难恢复  
 执行以下操作时使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送灾难恢复：  
  
-   按照本主题中的步骤[清单： 增加可用性与灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)以提高可用性的生产型的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用灾难恢复的环境。  
  
-   验证灾难恢复服务器具有处理生产负载的能力。  
  
     确保备用服务器具有相同或类似可用的资源 （CPU/内存/磁盘） 与生产服务器。  
  
-   确保你的灾难恢复日常活动期间细节很好地进行了说明。  
  
     记录你的灾难恢复准备和详细信息中的实现的每个步骤。 灾难很少反击方便时假定其第一天，方负责实现灾难恢复过程开始工作，以及将执行此操作在第一次。  
  
-   作为正则的测试，实际故障转移到灾难恢复站点的一部分，尤其是当新的 BizTalk 应用程序都将置于生产。  
  
     执行故障转移测试作为常规的测试和维护，以确保顺利执行的一部分。  
  
## <a name="see-also"></a>另请参阅  
 [灾难恢复](../technical-guides/disaster-recovery.md)