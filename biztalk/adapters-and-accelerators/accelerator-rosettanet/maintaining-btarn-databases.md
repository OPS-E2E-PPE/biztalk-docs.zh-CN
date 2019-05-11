---
title: 维护 BTARN 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maintaining databases
- databases, maintaining
ms.assetid: b048f68c-1e12-42e3-b7bb-2a87fe977f4e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09cfcebd3acd4a8b744bd14095f681f69e0c5e9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283270"
---
# <a name="maintaining-btarn-databases"></a><span data-ttu-id="78426-102">维护 BTARN 数据库</span><span class="sxs-lookup"><span data-stu-id="78426-102">Maintaining BTARN Databases</span></span>
<span data-ttu-id="78426-103">Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]数据库日益庞大，其大小可能会影响系统性能。</span><span class="sxs-lookup"><span data-stu-id="78426-103">Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] databases can grow so large that their size can affect system performance.</span></span> <span data-ttu-id="78426-104">这可能导致从特定的情况下，未使用的条目不在表中，例如孤立附件或不使用的摘要。</span><span class="sxs-lookup"><span data-stu-id="78426-104">This can result from specific circumstances that leave unused entries in the tables, such as orphan attachments or unused digests.</span></span> <span data-ttu-id="78426-105">它也可能不会删除表中的旧条目。</span><span class="sxs-lookup"><span data-stu-id="78426-105">It can also occur from not deleting old entries in the tables.</span></span> <span data-ttu-id="78426-106">请按照来维护此部分中的过程在[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据库以便对性能没有影响。</span><span class="sxs-lookup"><span data-stu-id="78426-106">Follow the procedures in this section to maintain your [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] databases so there is no effect on performance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="78426-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="78426-107">In This Section</span></span>  
  
-   [<span data-ttu-id="78426-108">维护不可否认性数据库表</span><span class="sxs-lookup"><span data-stu-id="78426-108">Maintaining the Non-Repudiation Database Tables</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-the-non-repudiation-database-tables.md)  
  
-   [<span data-ttu-id="78426-109">删除摘要</span><span class="sxs-lookup"><span data-stu-id="78426-109">Deleting Digests</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md)  
  
-   [<span data-ttu-id="78426-110">删除孤立附件</span><span class="sxs-lookup"><span data-stu-id="78426-110">Deleting Orphan Attachments</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/deleting-orphan-attachments.md)