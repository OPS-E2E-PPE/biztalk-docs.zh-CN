---
title: "配置 BizTalk Server 日志传送有关的其他数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fc2ae67-5cb9-4d53-9bf7-c88f84914960
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b16b1d262b07ecaa62e87456f10bece225b3b34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-biztalk-server-log-shipping-for-additional-databases"></a>配置 BizTalk Server 日志传送有关的其他数据库
在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，添加到 BizTalk Server 中备份作业的作业会自动添加到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送。 无需执行其他步骤来配置新的数据库添加到 BizTalk Server 中备份作业的日志传送。 但是，请务必根据需要在添加自定义数据库\<OtherDatabases > SampleUpdateInfo.xml 文件中的步骤 22 所述的部分[如何为日志传送配置目标系统](http://go.microsoft.com/fwlink/?LinkId=151402)(http: / / go.microsoft.com/fwlink/？LinkId = 151402) 中[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]帮助。  
  
## <a name="see-also"></a>另请参阅  
 [配置 BizTalk Server 日志传送](../technical-guides/configuring-biztalk-server-log-shipping.md)