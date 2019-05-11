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
# <a name="monitoring-biztalk-server-log-shipping"></a><span data-ttu-id="19d8e-102">监视 BizTalk Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="19d8e-102">Monitoring BizTalk Server Log Shipping</span></span>
<span data-ttu-id="19d8e-103">若要确定 BizTalk Server 数据库和已还原的日志的最后一个成功备份集，请查看 Master.dbo.bts_LogShippingHistory 表在目标上的内容[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]个实例。</span><span class="sxs-lookup"><span data-stu-id="19d8e-103">To determine the last successful backup set of BizTalk Server databases and logs that have been restored, review the contents of the Master.dbo.bts_LogShippingHistory table on the destination [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span> <span data-ttu-id="19d8e-104">此表填充由 BizTalk Server 日志传送获取备份历史记录作业和还原作业的更新。</span><span class="sxs-lookup"><span data-stu-id="19d8e-104">This table is populated by the BizTalk Server Log Shipping Get Backup History job and is updated by the restore job.</span></span> <span data-ttu-id="19d8e-105">已成功还原备份，则 Restored 列设置为值 1 和 1,restoreddatetime 将设为当前日期和时间。</span><span class="sxs-lookup"><span data-stu-id="19d8e-105">When a backup is successfully restored, the Restored column is set to a value of 1 and the RestoredDateTime is set to the current date and time.</span></span>  
  
 <span data-ttu-id="19d8e-106">已成功还原所有数据库还原到服务器，从特定备份集在 Master.dbo.bts_LogShippingHistory 表中列出，则备份集 ID 都写入 Master.dbo.bts_LogShippingLastRestoreSet 表。</span><span class="sxs-lookup"><span data-stu-id="19d8e-106">When all of the databases restored to the server from a particular backup set listed in the Master.dbo.bts_LogShippingHistory table have been successfully restored, the backup set ID is written to the Master.dbo.bts_LogShippingLastRestoreSet table.</span></span> <span data-ttu-id="19d8e-107">此表存储设置还原上一次，并且可用于确定日志哪些备份集需要还原的灾难恢复事件的匹配项后将目标 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="19d8e-107">This table stores the last set restored and is useful for determining what backup set of logs need to be restored to bring the destination BizTalk group online after the occurrence of a disaster recovery event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19d8e-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="19d8e-108">See Also</span></span>  
 [<span data-ttu-id="19d8e-109">配置 BizTalk Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="19d8e-109">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)