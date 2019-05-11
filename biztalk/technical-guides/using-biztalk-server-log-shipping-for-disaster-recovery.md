---
title: 使用 BizTalk Server 日志传送灾难恢复 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d65015c-de53-4590-b644-5c2f66f763db
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dc2ab707bb4620fdb4b45db2750514758f21300
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400360"
---
# <a name="using-biztalk-server-log-shipping-for-disaster-recovery"></a>使用 BizTalk Server 日志传送灾难恢复
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 实现数据库的备用容量通过数据库使用日志传送。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 备份和还原的数据库和事务日志文件，从而允许在备用服务器恢复数据库处理在的生产数据库服务器出现故障，可自动执行日志传送。  
  
## <a name="how-log-shipping-works"></a>如何日志传送的工作原理  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]使用的代理作业[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送同步在生产环境中使用的源服务器和目标服务器作为备用每隔 15 分钟默认情况下使用 （每个备份 BizTalk Server 作业运行的时间） 之间的数据。  
  
## <a name="using-log-shipping-for-disaster-recovery"></a>使用日志传送灾难恢复  
 执行以下操作时使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送灾难恢复：  
  
- 按照本主题中的步骤[核对清单：提供高可用性灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)以提高可用性的生产型的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用灾难恢复环境。  
  
- 验证的灾难恢复服务器都具有容量来处理生产负载。  
  
   确保备用服务器具有相同或相似可用的资源 （CPU/内存/磁盘） 作为生产服务器。  
  
- 请确保也记录在灾难恢复例程的详细信息。  
  
   记录你的灾难恢复准备和实现详细信息中的每个步骤。 灾难很少反击方便的时候假定方负责实现灾难恢复过程开始其第一天的工作，将会执行此操作的第一次。  
  
- 作为常规的测试，实际故障转移到灾难恢复站点的一部分，尤其是当新的 BizTalk 应用程序放在生产环境中。  
  
   执行故障转移测试作为常规测试和维护，以确保顺利地执行的一部分。  
  
## <a name="see-also"></a>请参阅  
 [灾难恢复](../technical-guides/disaster-recovery.md)