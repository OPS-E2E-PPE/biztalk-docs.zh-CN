---
title: "分布式系统问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 287b0adb-d5f9-4e47-80f8-0ba5d90c7864
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24abe471a66e8bc0724ad731388c5a0e7c07b573
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="distributed-system-problems"></a><span data-ttu-id="299dc-102">分布式的系统问题</span><span class="sxs-lookup"><span data-stu-id="299dc-102">Distributed System Problems</span></span>
<span data-ttu-id="299dc-103">分布式的目标系统中的还原作业不知道的错误或其他计算机上的问题。</span><span class="sxs-lookup"><span data-stu-id="299dc-103">In a distributed destination system the restore jobs are not aware of errors or problems on the other computers.</span></span> <span data-ttu-id="299dc-104">例如，假设计算机 A 正在还原 BizTalk 管理数据库和 BizTalk 跟踪数据库，并且计算机 B 正在还原的 BizTalk MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="299dc-104">For example, suppose that computer A is restoring the BizTalk Management database and the BizTalk Tracking database, and computer B is restoring the BizTalk MessageBox database.</span></span> <span data-ttu-id="299dc-105">这两台计算机成功还原备份集 1 到 25。</span><span class="sxs-lookup"><span data-stu-id="299dc-105">Both computers successfully restore backup sets 1 through 25.</span></span> <span data-ttu-id="299dc-106">集 26，但是，具有 BizTalk MessageBox 数据库的损坏的日志备份文件。</span><span class="sxs-lookup"><span data-stu-id="299dc-106">Set 26, however, has a corrupted log backup file of the BizTalk MessageBox database.</span></span> <span data-ttu-id="299dc-107">计算机 A 正确还原其数据库，但计算机 B 无法还原损坏的文件。</span><span class="sxs-lookup"><span data-stu-id="299dc-107">Computer A restores its databases correctly but computer B fails to restore the corrupted file.</span></span>  
  
 <span data-ttu-id="299dc-108">在此情况下，强制源系统上的完整备份。</span><span class="sxs-lookup"><span data-stu-id="299dc-108">In this situation, force a full backup on the source system.</span></span> <span data-ttu-id="299dc-109">继续上面的示例，假定已诊断问题并为集 35 创建完整备份。</span><span class="sxs-lookup"><span data-stu-id="299dc-109">Continuing the example above, assume that the problem was diagnosed and a full backup was created for set 35.</span></span> <span data-ttu-id="299dc-110">计算机 A 然后还原集 26 到 34，因为它并不知道的计算机。 计算机 B 上的问题将失败直到它看到完整备份集 35 和后续日志备份集 （请记住： 必须始终为一组的一个完整的后续日志备份还原的 36d)。</span><span class="sxs-lookup"><span data-stu-id="299dc-110">Computer A then restores sets 26 to 34, because it is not aware of the problem on Computer B. Computer B will fail until it sees full backup set 35 and subsequent log backup set 36 (remember that there must always be one subsequent complete log backup for a set to be restored).</span></span> <span data-ttu-id="299dc-111">当集 35 和 36 到达计算机 B 上时，它将修复本身使用 35。</span><span class="sxs-lookup"><span data-stu-id="299dc-111">When sets 35 and 36 arrive on computer B, it will repair itself using 35.</span></span> <span data-ttu-id="299dc-112">完成修复后，将同步计算机 A 和 B。</span><span class="sxs-lookup"><span data-stu-id="299dc-112">After the repair is complete, computer A and B will be in sync.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="299dc-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="299dc-113">See Also</span></span>  
 [<span data-ttu-id="299dc-114">故障排除日志传送</span><span class="sxs-lookup"><span data-stu-id="299dc-114">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)