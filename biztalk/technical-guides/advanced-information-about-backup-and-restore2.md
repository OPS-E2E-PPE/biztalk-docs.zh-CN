---
title: 有关备份和 Restore2 的高级信息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa6a3527-4889-40ae-aacb-b8ea75be0329
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6991e417afaee807d999f7123f7a853dbd955eb3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295541"
---
# <a name="advanced-information-about-backup-and-restore"></a><span data-ttu-id="4c4ed-102">有关备份和还原的高级信息</span><span class="sxs-lookup"><span data-stu-id="4c4ed-102">Advanced Information About Backup and Restore</span></span>
<span data-ttu-id="4c4ed-103">此处列出的主题介绍备份和还原进程在更详细介绍，并且应由高级用户使用的全面了解[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c4ed-103">The topics listed here describe the backup and restore processes in more detail and are intended to be used by advanced users with a thorough understanding of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="4c4ed-104">有关标记的事务、 完整备份和日志的信息，请参阅[标记事务、 完整备份和日志备份](http://go.microsoft.com/fwlink/?LinkId=151565)(http://go.microsoft.com/fwlink/?LinkId=151565)。</span><span class="sxs-lookup"><span data-stu-id="4c4ed-104">For information about marked transaction, full backups, and logs, see [Marked Transactions, Full Backups, and Log Backups](http://go.microsoft.com/fwlink/?LinkId=151565) (http://go.microsoft.com/fwlink/?LinkId=151565).</span></span>  
  
-   <span data-ttu-id="4c4ed-105">璝惠[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送，请参阅[BizTalk Server 日志传送](http://go.microsoft.com/fwlink/?LinkId=151566)(http://go.microsoft.com/fwlink/?LinkId=151566)。</span><span class="sxs-lookup"><span data-stu-id="4c4ed-105">For information about [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping, see [BizTalk Server Log Shipping](http://go.microsoft.com/fwlink/?LinkId=151566) (http://go.microsoft.com/fwlink/?LinkId=151566).</span></span>  
  
-   <span data-ttu-id="4c4ed-106">有关计划备份信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业，请参阅[如何安排备份 BizTalk Server 作业](http://go.microsoft.com/fwlink/?LinkId=151568)(http://go.microsoft.com/fwlink/?LinkId=151568)。</span><span class="sxs-lookup"><span data-stu-id="4c4ed-106">For information about scheduling backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job, see [How to Schedule the Backup BizTalk Server Job](http://go.microsoft.com/fwlink/?LinkId=151568) (http://go.microsoft.com/fwlink/?LinkId=151568).</span></span>  
  
-   <span data-ttu-id="4c4ed-107">有关备份自定义数据库的信息，请参阅[如何返回自定义数据库](http://go.microsoft.com/fwlink/?LinkId=151569)(http://go.microsoft.com/fwlink/?LinkId=151569)。</span><span class="sxs-lookup"><span data-stu-id="4c4ed-107">For information about backing up custom databases, see [How to Back Up Custom Databases](http://go.microsoft.com/fwlink/?LinkId=151569) (http://go.microsoft.com/fwlink/?LinkId=151569).</span></span>  
  
-   <span data-ttu-id="4c4ed-108">有关创建链接的服务器的信息，请参阅[如何创建链接服务器](http://go.microsoft.com/fwlink/?LinkId=151570)(http://go.microsoft.com/fwlink/?LinkId=151570)。</span><span class="sxs-lookup"><span data-stu-id="4c4ed-108">For information about creating a linked server, see [How to Create a Linked Server](http://go.microsoft.com/fwlink/?LinkId=151570) (http://go.microsoft.com/fwlink/?LinkId=151570).</span></span>  
  
-   <span data-ttu-id="4c4ed-109">有关查看的已恢复的备份历史记录的信息，请参阅[查看还原的备份历史记录](http://go.microsoft.com/fwlink/?LinkId=151572)(http://go.microsoft.com/fwlink/?LinkId=151572)。</span><span class="sxs-lookup"><span data-stu-id="4c4ed-109">For information about viewing the history of restored backups, see [Viewing the History of Restored Backups](http://go.microsoft.com/fwlink/?LinkId=151572) (http://go.microsoft.com/fwlink/?LinkId=151572).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c4ed-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="4c4ed-110">In This Section</span></span>  
  
-   [<span data-ttu-id="4c4ed-111">BizTalk Server 日志传送使用 Windows 群集名称和 IP 地址</span><span class="sxs-lookup"><span data-stu-id="4c4ed-111">BizTalk Server Log Shipping Using a Windows Cluster Name and IP Address</span></span>](../technical-guides/biztalk-server-log-shipping-using-a-windows-cluster-name-and-ip-address.md)  
  
-   [<span data-ttu-id="4c4ed-112">从暖备份中还原生产</span><span class="sxs-lookup"><span data-stu-id="4c4ed-112">Restoring Production from a Warm Backup</span></span>](../technical-guides/restoring-production-from-a-warm-backup.md)