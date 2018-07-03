---
title: 如何还原备份 BizTalk Server 作业中的数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9bcac40f-ef0b-4ff0-8743-cf1614e14422
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fde33b46937118aa29aa8259225da2c4d2c0439
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992406"
---
# <a name="how-to-restore-databases-in-the-backup-biztalk-server-job"></a>如何还原备份 BizTalk Server 作业中的数据库
本部分介绍的步骤进行联机备份的备份 BizTalk Server 作业中的 BizTalk 组的数据库。 默认情况下，通过使用除 BAM 数据库的备份 BizTalk Server 作业备份所有数据库。 请参阅[还原 Analysis Services 和支持数据库](../technical-guides/restoring-analysis-services-and-supporting-databases.md)有关备份和还原 BAM 数据库的详细信息。 必须将所有数据库还原到相同的标记，以确保各个数据库间的事务状态一致。 有关详细信息，请参阅[标记的事务、 完整备份和日志备份](http://go.microsoft.com/fwlink/?LinkId=151565)(http://go.microsoft.com/fwlink/?LinkId=151565)。  
  
 有关详细信息和有关还原的数据库的说明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[如何还原您的数据库](http://go.microsoft.com/fwlink/?LinkId=151406)(<http://go.microsoft.com/fwlink/?LinkId=151406>)。  
  
## <a name="see-also"></a>请参阅  
 [还原备份 BizTalk Server 作业中不包含的数据库](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)