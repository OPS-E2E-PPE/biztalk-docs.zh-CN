---
title: "为其他数据库配置 BizTalk 日志传送 |Microsoft 文档"
description: "将自定义数据库添加到备份 BizTalk Server 作业以及 BizTalk Server 中的日志传送"
ms.custom: 
ms.date: 11/01/2017
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
ms.openlocfilehash: 1f4eb0b690f81b16d739183633c6507b2ad87226
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="configuring-biztalk-server-log-shipping-for-additional-databases"></a>配置 BizTalk Server 日志传送有关的其他数据库

## <a name="overview"></a>概述
在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，添加到 BizTalk Server 中备份作业的作业会自动添加到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送。 无需执行其他步骤来配置新的数据库添加到 BizTalk Server 中备份作业的日志传送。 但是，请务必根据需要在添加自定义数据库\<OtherDatabases > SampleUpdateInfo.xml 文件部分。 [为日志传送配置目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md)和[返回自定义数据库](../core/how-to-back-up-custom-databases.md)提供了一些指导。
  
## <a name="see-also"></a>另请参阅  
 [配置 BizTalk Server 日志传送](../technical-guides/configuring-biztalk-server-log-shipping.md)