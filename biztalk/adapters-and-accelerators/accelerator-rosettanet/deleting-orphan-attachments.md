---
title: "删除孤立的附件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maintaining databases, deleting orphaned attachments
- databases, deleting orphaned attachments
- attachments
ms.assetid: 38280464-9c9d-4890-9fc5-4b8031dd3f88
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7660182793cc82ac938f0dd25011a7c4ad7d7e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deleting-orphan-attachments"></a><span data-ttu-id="68924-102">删除孤立的附件</span><span class="sxs-lookup"><span data-stu-id="68924-102">Deleting Orphan Attachments</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="68924-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]将接收的消息的附件存储。</span><span class="sxs-lookup"><span data-stu-id="68924-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] stores attachments for received messages.</span></span> <span data-ttu-id="68924-104">在某些情况下，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 保存附件，但从 MessagesToLOB 表中删除相关联的消息，以致产生了孤立附件。</span><span class="sxs-lookup"><span data-stu-id="68924-104">In certain circumstances, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves the attachment, but deletes the associated message from the MessagesToLOB table, resulting in an orphan attachment.</span></span> <span data-ttu-id="68924-105">这会时发生提交一条消息，具有附件，并且具有清单无效，例如，清单中哪些 NumberOfAttachments = 0。</span><span class="sxs-lookup"><span data-stu-id="68924-105">This can occur when you submit a message that has an attachment and has a manifest that is not valid, for example, a manifest in which NumberOfAttachments = 0.</span></span> <span data-ttu-id="68924-106">定期，你可能想要删除孤立的附件，若要维护系统性能。</span><span class="sxs-lookup"><span data-stu-id="68924-106">Periodically, you may want to delete orphan attachments to maintain system performance.</span></span>  
  
## <a name="how-to-delete-orphan-attachments"></a><span data-ttu-id="68924-107">如何删除孤立附件</span><span class="sxs-lookup"><span data-stu-id="68924-107">How to Delete Orphan Attachments</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="68924-108">将附件存储在 BTARNDATA 数据库的附件表。</span><span class="sxs-lookup"><span data-stu-id="68924-108"> stores attachments in the Attachments table of the BTARNDATA database.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="68924-109">MessagesToLOB 表中存储相关联的消息。</span><span class="sxs-lookup"><span data-stu-id="68924-109"> stores the associated messages in the MessagesToLOB table.</span></span> <span data-ttu-id="68924-110">孤立附件结果附件具有时`outMessageID`不对应的属性`MessageID`MessagesToLOB 表中消息的属性。</span><span class="sxs-lookup"><span data-stu-id="68924-110">An orphan attachment results when the attachment has an `outMessageID` property that does not correspond to the `MessageID` property of a message in the MessagesToLOB table.</span></span>  
  
 <span data-ttu-id="68924-111">您可能需要定期地使用存储过程删除表中的附件，该过程仅删除在 MessagesToLOB 表中没有相符的消息的附件。</span><span class="sxs-lookup"><span data-stu-id="68924-111">Periodically, you may want to delete attachments from the table by using a stored procedure that deletes only those attachments that do not have a corresponding message in the MessagesToLOB table.</span></span> <span data-ttu-id="68924-112">存储过程的 SQL 语句示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="68924-112">A sample SQL statement for the stored procedure is:</span></span>  
  
```  
delete from attachments where outMessageID not in (select messageid from messagestolob)  
```  
  
 <span data-ttu-id="68924-113">此外，建议删除已存在了一定时间的附件，并且删除时不需要任何其他的检查。</span><span class="sxs-lookup"><span data-stu-id="68924-113">Additionally, it is recommended that you delete attachments that are older than a certain period, and do not require any more investigation.</span></span> <span data-ttu-id="68924-114">附件表包含`TimeCreated`可用于删除旧的附件的属性。</span><span class="sxs-lookup"><span data-stu-id="68924-114">The Attachments table contains a `TimeCreated` property that you can use to delete old attachments.</span></span> <span data-ttu-id="68924-115">此过程与用于删除旧摘要的过程相似。</span><span class="sxs-lookup"><span data-stu-id="68924-115">This process is similar to the process used to delete old digests.</span></span> <span data-ttu-id="68924-116">删除旧的摘要的存储过程的示例 SQL 语句，请参阅[删除摘要](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md)。</span><span class="sxs-lookup"><span data-stu-id="68924-116">For a sample SQL statement for a stored procedure that deletes old digests, see [Deleting Digests](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md).</span></span>  
  
 <span data-ttu-id="68924-117">同时建议对 Attachments 和 MessagestoLOB 表中各自的 MessageID 列编制索引。</span><span class="sxs-lookup"><span data-stu-id="68924-117">It is also recommended that you index the Attachments and MessagestoLOB tables on the respective MessageID columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68924-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68924-118">See Also</span></span>  
 [<span data-ttu-id="68924-119">维护 BTARN 数据库</span><span class="sxs-lookup"><span data-stu-id="68924-119">Maintaining BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)