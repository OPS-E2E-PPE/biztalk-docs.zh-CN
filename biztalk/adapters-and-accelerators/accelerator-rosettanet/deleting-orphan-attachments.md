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
# <a name="deleting-orphan-attachments"></a>删除孤立附件
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]存储为接收的消息的附件。 在某些情况下，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]保存附件，但从 MessagesToLOB 表中，从而导致孤立附件中删除相关联的消息。 这可能时提交的消息包含附件，并且有一个清单，不是有效的例如，清单中 NumberOfAttachments = 0。 定期，您可能想要删除孤立附件以维护系统性能。  
  
## <a name="how-to-delete-orphan-attachments"></a>如何删除孤立附件  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将附件存储在 BTARNDATA 数据库的 Attachments 表。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将关联的消息存储在 MessagesToLOB 表中。 当附件时产生了孤立附件`outMessageID`不对应的属性`MessageID`MessagesToLOB 表中的消息的属性。  
  
 定期，您可能想要通过删除在 MessagesToLOB 表中没有相应的消息的这些附件的存储的过程从表中删除附件。 存储过程的示例 SQL 语句是：  
  
```  
delete from attachments where outMessageID not in (select messageid from messagestolob)  
```  
  
 此外，建议删除早于特定时间段，并且不需要任何进一步的调查的附件。 Attachments 表包含`TimeCreated`可用于删除旧的附件的属性。 此过程是类似于用于删除旧摘要的过程。 删除旧摘要的存储过程的示例 SQL 语句，请参阅[删除摘要](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md)。  
  
 此外，还建议索引对 Attachments 和 MessagestoLOB 各自的 MessageID 列上的表。  
  
## <a name="see-also"></a>请参阅  
 [维护 BTARN 数据库](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)