---
title: 删除摘要 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, digests
- messages, digests
- digests
- databases, deleting digests
- maintaining databases, deleting digests
ms.assetid: bcc7cb11-2f6a-4996-ad50-040d41993e09
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fefa59a7638b7dc4627d5d7a019d753b4f6290b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206741"
---
# <a name="deleting-digests"></a><span data-ttu-id="0c9ff-102">删除摘要</span><span class="sxs-lookup"><span data-stu-id="0c9ff-102">Deleting Digests</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="0c9ff-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]存储为传出消息的摘要，以便它可以针对信号内容对它们进行验证。</span><span class="sxs-lookup"><span data-stu-id="0c9ff-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] stores digests for outgoing messages, so it can validate them against signal content.</span></span> <span data-ttu-id="0c9ff-104">不过，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不会在验证后删除摘要。</span><span class="sxs-lookup"><span data-stu-id="0c9ff-104">However, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not delete the digests after validation.</span></span> <span data-ttu-id="0c9ff-105">您可能希望定期删除这些摘要以保持系统性能。</span><span class="sxs-lookup"><span data-stu-id="0c9ff-105">Periodically, you may want to delete these digests to maintain system performance.</span></span>  
  
## <a name="when-and-how-to-delete-digests"></a><span data-ttu-id="0c9ff-106">何时及如何删除摘要</span><span class="sxs-lookup"><span data-stu-id="0c9ff-106">When and How to Delete Digests</span></span>  
 <span data-ttu-id="0c9ff-107">摘要存储在 BTARNDATA 数据库的 MessageDigestHelper 表中。</span><span class="sxs-lookup"><span data-stu-id="0c9ff-107">Digests are stored in the MessageDigestHelper table of the BTARNDATA database.</span></span> <span data-ttu-id="0c9ff-108">若要定期从表中删除这些摘要，您可以使用存储过程仅删除那些早于某段时间的摘要。</span><span class="sxs-lookup"><span data-stu-id="0c9ff-108">Periodically, you may want to delete these digests from the table by using a stored procedure that deletes only those digests that are older than a certain period.</span></span> <span data-ttu-id="0c9ff-109">MessageDigestHelper 表包含`TimeCreated`可用于此目的的属性。</span><span class="sxs-lookup"><span data-stu-id="0c9ff-109">The MessageDigestHelper table contains a `TimeCreated` property that you can use for this purpose.</span></span>  
  
 <span data-ttu-id="0c9ff-110">请使用以下 SQL 语句创建存储过程（可根据您的目的修改），并运行存储过程来删除旧摘要。</span><span class="sxs-lookup"><span data-stu-id="0c9ff-110">Create a stored procedure with the following SQL statement (as modified for your purposes), and run the stored procedure to delete old digests.</span></span> <span data-ttu-id="0c9ff-111">此示例语句删除所有保存了七天以上的摘要：</span><span class="sxs-lookup"><span data-stu-id="0c9ff-111">This sample statement deletes all digests more than seven days old:</span></span>  
  
```  
delete from MessageDigestHelper where datediff(day, TimeCreated, getutcdate()) > 7  
```  
  
> [!NOTE]
>  <span data-ttu-id="0c9ff-112">存储的过程必须包括调用`getutcdate`，而不`getdate`，因为所有[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库使用 UTC （协调世界时） 时间。</span><span class="sxs-lookup"><span data-stu-id="0c9ff-112">The stored procedure must include a call to `getutcdate`, not `getdate`, because all [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] databases use UTC (Universal Time Coordinate) time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c9ff-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c9ff-113">See Also</span></span>  
 [<span data-ttu-id="0c9ff-114">维护 BTARN 数据库</span><span class="sxs-lookup"><span data-stu-id="0c9ff-114">Maintaining BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)