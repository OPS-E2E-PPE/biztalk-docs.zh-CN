---
title: "维护 BTARN 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maintaining databases
- databases, maintaining
ms.assetid: b048f68c-1e12-42e3-b7bb-2a87fe977f4e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ba898931c4fe295c90d6eb94cad60b69d0910d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="maintaining-btarn-databases"></a><span data-ttu-id="23f71-102">维护 BTARN 数据库</span><span class="sxs-lookup"><span data-stu-id="23f71-102">Maintaining BTARN Databases</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="23f71-103">® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 的数据库日益庞大，可能会影响到系统的性能。</span><span class="sxs-lookup"><span data-stu-id="23f71-103">® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] databases can grow so large that their size can affect system performance.</span></span> <span data-ttu-id="23f71-104">这可能是由于某些特殊情况造成的，在这些情况下，许多不用的条目被留在表中，例如孤立附件或不使用的摘要。</span><span class="sxs-lookup"><span data-stu-id="23f71-104">This can result from specific circumstances that leave unused entries in the tables, such as orphan attachments or unused digests.</span></span> <span data-ttu-id="23f71-105">也可能是由于未删除表中的旧条目造成的。</span><span class="sxs-lookup"><span data-stu-id="23f71-105">It can also occur from not deleting old entries in the tables.</span></span> <span data-ttu-id="23f71-106">请按照本节中所述的步骤来维护您的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 数据库，从而确保系统性能不受影响。</span><span class="sxs-lookup"><span data-stu-id="23f71-106">Follow the procedures in this section to maintain your [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] databases so there is no effect on performance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23f71-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="23f71-107">In This Section</span></span>  
  
-   [<span data-ttu-id="23f71-108">维护不可否认性数据库表</span><span class="sxs-lookup"><span data-stu-id="23f71-108">Maintaining the Non-Repudiation Database Tables</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-the-non-repudiation-database-tables.md)  
  
-   [<span data-ttu-id="23f71-109">删除摘要</span><span class="sxs-lookup"><span data-stu-id="23f71-109">Deleting Digests</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md)  
  
-   [<span data-ttu-id="23f71-110">删除孤立的附件</span><span class="sxs-lookup"><span data-stu-id="23f71-110">Deleting Orphan Attachments</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/deleting-orphan-attachments.md)