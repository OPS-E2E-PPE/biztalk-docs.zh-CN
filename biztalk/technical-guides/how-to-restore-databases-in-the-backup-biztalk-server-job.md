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
ms.openlocfilehash: 85530acdb59f166236e96d80b5de46085ab68015
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270524"
---
# <a name="how-to-restore-databases-in-the-backup-biztalk-server-job"></a><span data-ttu-id="4929f-102">如何还原备份 BizTalk Server 作业中的数据库</span><span class="sxs-lookup"><span data-stu-id="4929f-102">How to Restore Databases in the Backup BizTalk Server Job</span></span>
<span data-ttu-id="4929f-103">本部分介绍的步骤进行联机备份的备份 BizTalk Server 作业中的 BizTalk 组的数据库。</span><span class="sxs-lookup"><span data-stu-id="4929f-103">This section covers the steps to bring online the databases in the BizTalk group that are backed up by the Backup BizTalk Server job.</span></span> <span data-ttu-id="4929f-104">默认情况下，通过使用除 BAM 数据库的备份 BizTalk Server 作业备份所有数据库。</span><span class="sxs-lookup"><span data-stu-id="4929f-104">By default, all databases are backed up by using the Backup BizTalk Server job except for the BAM databases.</span></span> <span data-ttu-id="4929f-105">请参阅[还原 Analysis Services 和支持数据库](../technical-guides/restoring-analysis-services-and-supporting-databases.md)有关备份和还原 BAM 数据库的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4929f-105">See [Restoring Analysis Services and Supporting Databases](../technical-guides/restoring-analysis-services-and-supporting-databases.md) for more information about backup and restore of the BAM databases.</span></span> <span data-ttu-id="4929f-106">必须将所有数据库还原到相同的标记，以确保各个数据库间的事务状态一致。</span><span class="sxs-lookup"><span data-stu-id="4929f-106">You must restore all databases to the same mark to ensure a consistent transactional state among the databases.</span></span> <span data-ttu-id="4929f-107">有关详细信息，请参阅[标记的事务、 完整备份和日志备份](http://go.microsoft.com/fwlink/?LinkId=151565)(http://go.microsoft.com/fwlink/?LinkId=151565)。</span><span class="sxs-lookup"><span data-stu-id="4929f-107">For more information, see [Marked Transactions, Full Backups, and Log Backups](http://go.microsoft.com/fwlink/?LinkId=151565) (http://go.microsoft.com/fwlink/?LinkId=151565).</span></span>  
  
 <span data-ttu-id="4929f-108">有关详细信息和有关还原的数据库的说明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[如何还原您的数据库](http://go.microsoft.com/fwlink/?LinkId=151406)(<http://go.microsoft.com/fwlink/?LinkId=151406>)。</span><span class="sxs-lookup"><span data-stu-id="4929f-108">For more information and instructions about restoring databases for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [How to Restore Your Databases](http://go.microsoft.com/fwlink/?LinkId=151406) (<http://go.microsoft.com/fwlink/?LinkId=151406>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4929f-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="4929f-109">See Also</span></span>  
 [<span data-ttu-id="4929f-110">还原备份 BizTalk Server 作业中不包含的数据库</span><span class="sxs-lookup"><span data-stu-id="4929f-110">Restoring Databases Not Included in the Backup BizTalk Server Job</span></span>](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)