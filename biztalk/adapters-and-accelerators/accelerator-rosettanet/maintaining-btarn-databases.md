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
ms.openlocfilehash: 496e83311c4ede6446bad8893fbe37b22cf8420d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000766"
---
# <a name="maintaining-btarn-databases"></a>维护 BTARN 数据库
Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]数据库日益庞大，其大小可能会影响系统性能。 这可能是由于某些特殊情况造成的，在这些情况下，许多不用的条目被留在表中，例如孤立附件或不使用的摘要。 也可能是由于未删除表中的旧条目造成的。 请按照本节中所述的步骤来维护您的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 数据库，从而确保系统性能不受影响。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [维护不可否认性数据库表](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-the-non-repudiation-database-tables.md)  
  
-   [删除摘要](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md)  
  
-   [删除孤立附件](../../adapters-and-accelerators/accelerator-rosettanet/deleting-orphan-attachments.md)