---
title: "监视 BizTalk Server 日志传送 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fae4ff40-7d86-4e9b-b1cc-4f00486ae4b9
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eacec106823afc8203e7cce9679cb27cd29d0b78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-biztalk-server-log-shipping"></a>监视 BizTalk Server 日志传送
若要确定 BizTalk Server 数据库和已还原的日志的最后一个成功备份集，请查看在目标上 Master.dbo.bts_LogShippingHistory 表的内容[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。 此表中填充了 BizTalk Server 日志传送获取备份历史记录作业，并由还原作业更新。 已成功还原备份，还原列设置为值为 1，并且 RestoredDateTime 设置为当前日期和时间。  
  
 时已经成功地还原所有从设置 Master.dbo.bts_LogShippingHistory 表中列出的特定备份还原到服务器的数据库，备份集 ID 将写入到 Master.dbo.bts_LogShippingLastRestoreSet 表。 此表存储设置还原上一次，并且可用于确定日志哪些备份集需要还原在灾难恢复事件的匹配项后将目标 BizTalk 组。  
  
## <a name="see-also"></a>另请参阅  
 [配置 BizTalk Server 日志传送](../technical-guides/configuring-biztalk-server-log-shipping.md)