---
title: 删除摘要 |Microsoft Docs
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
ms.openlocfilehash: a3564b89c69183133bcc31e692aff5b1c85af80d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283736"
---
# <a name="deleting-digests"></a><span data-ttu-id="2d920-102">删除摘要</span><span class="sxs-lookup"><span data-stu-id="2d920-102">Deleting Digests</span></span>
<span data-ttu-id="2d920-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]存储为传出消息的摘要，以便它可以根据信号内容验证它们。</span><span class="sxs-lookup"><span data-stu-id="2d920-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] stores digests for outgoing messages, so it can validate them against signal content.</span></span> <span data-ttu-id="2d920-104">但是，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不会验证后删除摘要。</span><span class="sxs-lookup"><span data-stu-id="2d920-104">However, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not delete the digests after validation.</span></span> <span data-ttu-id="2d920-105">定期，您可能想要删除这些摘要以保持系统性能。</span><span class="sxs-lookup"><span data-stu-id="2d920-105">Periodically, you may want to delete these digests to maintain system performance.</span></span>  
  
## <a name="when-and-how-to-delete-digests"></a><span data-ttu-id="2d920-106">何时以及如何删除摘要</span><span class="sxs-lookup"><span data-stu-id="2d920-106">When and How to Delete Digests</span></span>  
 <span data-ttu-id="2d920-107">摘要存储在 BTARNDATA 数据库的 MessageDigestHelper 表中。</span><span class="sxs-lookup"><span data-stu-id="2d920-107">Digests are stored in the MessageDigestHelper table of the BTARNDATA database.</span></span> <span data-ttu-id="2d920-108">定期，您可能想要通过删除早于特定时间段的这些摘要的存储的过程从表中删除这些摘要。</span><span class="sxs-lookup"><span data-stu-id="2d920-108">Periodically, you may want to delete these digests from the table by using a stored procedure that deletes only those digests that are older than a certain period.</span></span> <span data-ttu-id="2d920-109">MessageDigestHelper 表中包含`TimeCreated`属性，可以使用实现此目的。</span><span class="sxs-lookup"><span data-stu-id="2d920-109">The MessageDigestHelper table contains a `TimeCreated` property that you can use for this purpose.</span></span>  
  
 <span data-ttu-id="2d920-110">使用以下 SQL 语句 （如修改您的要求），创建一个存储的过程并运行存储的过程来删除旧摘要。</span><span class="sxs-lookup"><span data-stu-id="2d920-110">Create a stored procedure with the following SQL statement (as modified for your purposes), and run the stored procedure to delete old digests.</span></span> <span data-ttu-id="2d920-111">此示例语句删除超过七天的所有摘要：</span><span class="sxs-lookup"><span data-stu-id="2d920-111">This sample statement deletes all digests more than seven days old:</span></span>  
  
```  
delete from MessageDigestHelper where datediff(day, TimeCreated, getutcdate()) > 7  
```  
  
> [!NOTE]
>  <span data-ttu-id="2d920-112">存储的过程必须包括对`getutcdate`，而非`getdate`，因为所有[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库使用 UTC （协调通用时间） 时间。</span><span class="sxs-lookup"><span data-stu-id="2d920-112">The stored procedure must include a call to `getutcdate`, not `getdate`, because all [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] databases use UTC (Universal Time Coordinate) time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d920-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d920-113">See Also</span></span>  
 [<span data-ttu-id="2d920-114">维护 BTARN 数据库</span><span class="sxs-lookup"><span data-stu-id="2d920-114">Maintaining BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)