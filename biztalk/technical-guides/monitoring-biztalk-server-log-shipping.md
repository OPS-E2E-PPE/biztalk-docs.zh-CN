---
title: 监视 BizTalk Server 日志传送 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fae4ff40-7d86-4e9b-b1cc-4f00486ae4b9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 578a587bbf500d5f49244fb8a56aac9d9fe83d19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379469"
---
# <a name="monitoring-biztalk-server-log-shipping"></a>监视 BizTalk Server 日志传送
若要确定 BizTalk Server 数据库和已还原的日志的最后一个成功备份集，请查看 Master.dbo.bts_LogShippingHistory 表在目标上的内容[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]个实例。 此表填充由 BizTalk Server 日志传送获取备份历史记录作业和还原作业的更新。 已成功还原备份，则 Restored 列设置为值 1 和 1,restoreddatetime 将设为当前日期和时间。  
  
 已成功还原所有数据库还原到服务器，从特定备份集在 Master.dbo.bts_LogShippingHistory 表中列出，则备份集 ID 都写入 Master.dbo.bts_LogShippingLastRestoreSet 表。 此表存储设置还原上一次，并且可用于确定日志哪些备份集需要还原的灾难恢复事件的匹配项后将目标 BizTalk 组。  
  
## <a name="see-also"></a>请参阅  
 [配置 BizTalk Server 日志传送](../technical-guides/configuring-biztalk-server-log-shipping.md)