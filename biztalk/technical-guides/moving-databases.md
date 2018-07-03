---
title: 移动数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a0d09a1-90a5-4a5d-a783-b979724e101b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15562fc1fb642a4766190dabe912e81b38bb1ea8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972414"
---
# <a name="moving-databases"></a>移动数据库
移动的建议的方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]（除业务活动监视 (BAM) 数据库中） 的数据库是配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部分中所述日志传送[灾难恢复](../technical-guides/disaster-recovery.md)。 使用 BAM，所有的数据库除外[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库可以通过使用备份**备份 BizTalk Server** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业。 有关此作业的详细信息，请参阅[如何安排备份 BizTalk Server 作业](http://go.microsoft.com/fwlink/?LinkId=154674)(<http://go.microsoft.com/fwlink/?LinkId=154674>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
 本部分介绍如何移动 BAM 相关数据库以及如何移动剩余[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不使用第一个配置数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送。 升级时，此方法可能会很有用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]存放计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库或在其他方案中不与灾难恢复。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [移动 BAM 数据库](../technical-guides/moving-bam-databases.md)  
  
-   [移动非 BAM 数据库](../technical-guides/moving-non-bam-databases.md)  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk Server2](../technical-guides/managing-biztalk-server2.md)