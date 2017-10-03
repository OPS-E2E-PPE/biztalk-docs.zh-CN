---
title: "损坏的备份文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc48197c-944a-4f0a-ba01-8e1d91c88ad3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fda5acae756fd2c4d0afc0263bc723af3ba77e15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="corrupt-backup-files"></a><span data-ttu-id="6a305-102">损坏的备份文件</span><span class="sxs-lookup"><span data-stu-id="6a305-102">Corrupt Backup Files</span></span>
<span data-ttu-id="6a305-103">备份文件可能已损坏、 损坏或缺失。</span><span class="sxs-lookup"><span data-stu-id="6a305-103">A backup file may become corrupt, damaged, or missing.</span></span> <span data-ttu-id="6a305-104">如果发生这种情况，则无法还原至少一个文件。</span><span class="sxs-lookup"><span data-stu-id="6a305-104">If this occurs, at least one file cannot be restored.</span></span> <span data-ttu-id="6a305-105">遇到的失败的系统上的还原作业搜索下一个有效的完整备份集。</span><span class="sxs-lookup"><span data-stu-id="6a305-105">The restore job on the system that suffered the failure searches for the next valid full backup set.</span></span> <span data-ttu-id="6a305-106">在大多数情况下它将需要强制源系统上进行完整备份。</span><span class="sxs-lookup"><span data-stu-id="6a305-106">In most cases it will be necessary to force a full backup on the source system.</span></span> <span data-ttu-id="6a305-107">如果没有此类集存在，恢复作业将失败并有效的完整备份集到达之前，每次后续运行也会失败。</span><span class="sxs-lookup"><span data-stu-id="6a305-107">If no such set exists, the restore job fails and each subsequent run also fails until a valid full backup set arrives.</span></span> <span data-ttu-id="6a305-108">如果存在一组，它用于修复环境。</span><span class="sxs-lookup"><span data-stu-id="6a305-108">If a set does exist, it is used to repair the environment.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6a305-109">由于在其中的方式[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]备份数据写入到文件，它是可能的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]将报告成功完成，即使数据实际写入期间备份失败。</span><span class="sxs-lookup"><span data-stu-id="6a305-109">Due to the manner in which [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] writes backup data to a file, it is possible that [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] will report successful completion even if the backup failed during the actual writing of the data.</span></span> <span data-ttu-id="6a305-110">主要，都将写入到的磁盘不是为本地计算机和网络故障或中断发生时，将出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="6a305-110">This scenario primarily occurs when the disk being written to is not local to the computer and a network failure or interruption occurs.</span></span> <span data-ttu-id="6a305-111">作为常规的预防措施，如果备份作业运行时，将发生网络故障，强制完整备份后解决网络连接问题。</span><span class="sxs-lookup"><span data-stu-id="6a305-111">As a general precaution, if a network failure occurs while the backup job is running, force a full backup after the network connectivity problem is resolved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a305-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a305-112">See Also</span></span>  
 [<span data-ttu-id="6a305-113">故障排除日志传送</span><span class="sxs-lookup"><span data-stu-id="6a305-113">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)