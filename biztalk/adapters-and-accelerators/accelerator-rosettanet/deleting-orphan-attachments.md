---
title: 删除孤立附件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maintaining databases, deleting orphaned attachments
- databases, deleting orphaned attachments
- attachments
ms.assetid: 38280464-9c9d-4890-9fc5-4b8031dd3f88
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 927bedacd4aed0554b90b634bd0b9ec813d6ef3e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283757"
---
# <a name="deleting-orphan-attachments"></a><span data-ttu-id="7c120-102">删除孤立附件</span><span class="sxs-lookup"><span data-stu-id="7c120-102">Deleting Orphan Attachments</span></span>
<span data-ttu-id="7c120-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]存储为接收的消息的附件。</span><span class="sxs-lookup"><span data-stu-id="7c120-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] stores attachments for received messages.</span></span> <span data-ttu-id="7c120-104">在某些情况下，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]保存附件，但从 MessagesToLOB 表中，从而导致孤立附件中删除相关联的消息。</span><span class="sxs-lookup"><span data-stu-id="7c120-104">In certain circumstances, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves the attachment, but deletes the associated message from the MessagesToLOB table, resulting in an orphan attachment.</span></span> <span data-ttu-id="7c120-105">这可能时提交的消息包含附件，并且有一个清单，不是有效的例如，清单中 NumberOfAttachments = 0。</span><span class="sxs-lookup"><span data-stu-id="7c120-105">This can occur when you submit a message that has an attachment and has a manifest that is not valid, for example, a manifest in which NumberOfAttachments = 0.</span></span> <span data-ttu-id="7c120-106">定期，您可能想要删除孤立附件以维护系统性能。</span><span class="sxs-lookup"><span data-stu-id="7c120-106">Periodically, you may want to delete orphan attachments to maintain system performance.</span></span>  
  
## <a name="how-to-delete-orphan-attachments"></a><span data-ttu-id="7c120-107">如何删除孤立附件</span><span class="sxs-lookup"><span data-stu-id="7c120-107">How to Delete Orphan Attachments</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="7c120-108">将附件存储在 BTARNDATA 数据库的 Attachments 表。</span><span class="sxs-lookup"><span data-stu-id="7c120-108">stores attachments in the Attachments table of the BTARNDATA database.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="7c120-109">将关联的消息存储在 MessagesToLOB 表中。</span><span class="sxs-lookup"><span data-stu-id="7c120-109">stores the associated messages in the MessagesToLOB table.</span></span> <span data-ttu-id="7c120-110">当附件时产生了孤立附件`outMessageID`不对应的属性`MessageID`MessagesToLOB 表中的消息的属性。</span><span class="sxs-lookup"><span data-stu-id="7c120-110">An orphan attachment results when the attachment has an `outMessageID` property that does not correspond to the `MessageID` property of a message in the MessagesToLOB table.</span></span>  
  
 <span data-ttu-id="7c120-111">定期，您可能想要通过删除在 MessagesToLOB 表中没有相应的消息的这些附件的存储的过程从表中删除附件。</span><span class="sxs-lookup"><span data-stu-id="7c120-111">Periodically, you may want to delete attachments from the table by using a stored procedure that deletes only those attachments that do not have a corresponding message in the MessagesToLOB table.</span></span> <span data-ttu-id="7c120-112">存储过程的示例 SQL 语句是：</span><span class="sxs-lookup"><span data-stu-id="7c120-112">A sample SQL statement for the stored procedure is:</span></span>  
  
```  
delete from attachments where outMessageID not in (select messageid from messagestolob)  
```  
  
 <span data-ttu-id="7c120-113">此外，建议删除早于特定时间段，并且不需要任何进一步的调查的附件。</span><span class="sxs-lookup"><span data-stu-id="7c120-113">Additionally, it is recommended that you delete attachments that are older than a certain period, and do not require any more investigation.</span></span> <span data-ttu-id="7c120-114">Attachments 表包含`TimeCreated`可用于删除旧的附件的属性。</span><span class="sxs-lookup"><span data-stu-id="7c120-114">The Attachments table contains a `TimeCreated` property that you can use to delete old attachments.</span></span> <span data-ttu-id="7c120-115">此过程是类似于用于删除旧摘要的过程。</span><span class="sxs-lookup"><span data-stu-id="7c120-115">This process is similar to the process used to delete old digests.</span></span> <span data-ttu-id="7c120-116">删除旧摘要的存储过程的示例 SQL 语句，请参阅[删除摘要](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md)。</span><span class="sxs-lookup"><span data-stu-id="7c120-116">For a sample SQL statement for a stored procedure that deletes old digests, see [Deleting Digests](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md).</span></span>  
  
 <span data-ttu-id="7c120-117">此外，还建议索引对 Attachments 和 MessagestoLOB 各自的 MessageID 列上的表。</span><span class="sxs-lookup"><span data-stu-id="7c120-117">It is also recommended that you index the Attachments and MessagestoLOB tables on the respective MessageID columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c120-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c120-118">See Also</span></span>  
 [<span data-ttu-id="7c120-119">维护 BTARN 数据库</span><span class="sxs-lookup"><span data-stu-id="7c120-119">Maintaining BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)