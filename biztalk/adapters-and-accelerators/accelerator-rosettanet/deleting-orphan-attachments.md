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
ms.openlocfilehash: 99b31633c27aaed7cb8ae7289f383a5bfcac8d1b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971886"
---
# <a name="deleting-orphan-attachments"></a>删除孤立附件
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]存储为接收的消息的附件。 在某些情况下，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 保存附件，但从 MessagesToLOB 表中删除相关联的消息，以致产生了孤立附件。 这可能时提交的消息包含附件，并且有一个清单，不是有效的例如，清单中 NumberOfAttachments = 0。 定期，您可能想要删除孤立附件以维护系统性能。  
  
## <a name="how-to-delete-orphan-attachments"></a>如何删除孤立附件  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将附件存储在 BTARNDATA 数据库的 Attachments 表。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将关联的消息存储在 MessagesToLOB 表中。 当附件时产生了孤立附件`outMessageID`不对应的属性`MessageID`MessagesToLOB 表中的消息的属性。  
  
 您可能需要定期地使用存储过程删除表中的附件，该过程仅删除在 MessagesToLOB 表中没有相符的消息的附件。 存储过程的 SQL 语句示例如下所示：  
  
```  
delete from attachments where outMessageID not in (select messageid from messagestolob)  
```  
  
 此外，建议删除已存在了一定时间的附件，并且删除时不需要任何其他的检查。 Attachments 表包含`TimeCreated`可用于删除旧的附件的属性。 此过程与用于删除旧摘要的过程相似。 删除旧摘要的存储过程的示例 SQL 语句，请参阅[删除摘要](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md)。  
  
 同时建议对 Attachments 和 MessagestoLOB 表中各自的 MessageID 列编制索引。  
  
## <a name="see-also"></a>请参阅  
 [维护 BTARN 数据库](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)