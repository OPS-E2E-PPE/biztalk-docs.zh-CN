---
title: 维护 BTARN 数据库 |Microsoft 文档
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
ms.openlocfilehash: 2ba898931c4fe295c90d6eb94cad60b69d0910d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209757"
---
# <a name="maintaining-btarn-databases"></a>维护 BTARN 数据库
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 的数据库日益庞大，可能会影响到系统的性能。 这可能是由于某些特殊情况造成的，在这些情况下，许多不用的条目被留在表中，例如孤立附件或不使用的摘要。 也可能是由于未删除表中的旧条目造成的。 请按照本节中所述的步骤来维护您的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 数据库，从而确保系统性能不受影响。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [维护不可否认性数据库表](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-the-non-repudiation-database-tables.md)  
  
-   [删除摘要](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md)  
  
-   [删除孤立的附件](../../adapters-and-accelerators/accelerator-rosettanet/deleting-orphan-attachments.md)