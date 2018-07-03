---
title: 损坏的备份文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc48197c-944a-4f0a-ba01-8e1d91c88ad3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5947b527dea1206255daf52f128569fd7a4f659c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987910"
---
# <a name="corrupt-backup-files"></a><span data-ttu-id="8c4ae-102">损坏的备份文件</span><span class="sxs-lookup"><span data-stu-id="8c4ae-102">Corrupt Backup Files</span></span>
<span data-ttu-id="8c4ae-103">备份文件可能已损坏、 损坏或缺失。</span><span class="sxs-lookup"><span data-stu-id="8c4ae-103">A backup file may become corrupt, damaged, or missing.</span></span> <span data-ttu-id="8c4ae-104">如果发生这种情况，则无法还原至少一个文件。</span><span class="sxs-lookup"><span data-stu-id="8c4ae-104">If this occurs, at least one file cannot be restored.</span></span> <span data-ttu-id="8c4ae-105">还原作业之间发生故障的系统上搜索下一个有效的完整备份集。</span><span class="sxs-lookup"><span data-stu-id="8c4ae-105">The restore job on the system that suffered the failure searches for the next valid full backup set.</span></span> <span data-ttu-id="8c4ae-106">在大多数情况下将需要强制源系统上执行完整备份。</span><span class="sxs-lookup"><span data-stu-id="8c4ae-106">In most cases it will be necessary to force a full backup on the source system.</span></span> <span data-ttu-id="8c4ae-107">如果没有此类集存在，还原作业失败，并且还每次运行时失败，直到到达时有效的完全备份集。</span><span class="sxs-lookup"><span data-stu-id="8c4ae-107">If no such set exists, the restore job fails and each subsequent run also fails until a valid full backup set arrives.</span></span> <span data-ttu-id="8c4ae-108">如果一组不存在，它用于修复环境。</span><span class="sxs-lookup"><span data-stu-id="8c4ae-108">If a set does exist, it is used to repair the environment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c4ae-109">考虑在其中方式[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]将备份数据写入到文件中，可能的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]即使备份失败，在实际写入的数据将报告已成功完成。</span><span class="sxs-lookup"><span data-stu-id="8c4ae-109">Due to the manner in which [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] writes backup data to a file, it is possible that [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] will report successful completion even if the backup failed during the actual writing of the data.</span></span> <span data-ttu-id="8c4ae-110">正在写入到的磁盘不在本地计算机和网络故障或中断发生时主要出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="8c4ae-110">This scenario primarily occurs when the disk being written to is not local to the computer and a network failure or interruption occurs.</span></span> <span data-ttu-id="8c4ae-111">作为常规的预防措施，如果备份作业运行时出现网络故障，强制完整备份后解决网络连接问题。</span><span class="sxs-lookup"><span data-stu-id="8c4ae-111">As a general precaution, if a network failure occurs while the backup job is running, force a full backup after the network connectivity problem is resolved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c4ae-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c4ae-112">See Also</span></span>  
 [<span data-ttu-id="8c4ae-113">日志传送疑难解答</span><span class="sxs-lookup"><span data-stu-id="8c4ae-113">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)