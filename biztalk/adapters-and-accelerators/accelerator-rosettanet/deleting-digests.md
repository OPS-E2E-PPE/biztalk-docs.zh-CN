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
ms.openlocfilehash: 10e32f8d86d6723965e8a27ad51f7551fdda0b60
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002398"
---
# <a name="deleting-digests"></a>删除摘要
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]存储为传出消息的摘要，以便它可以根据信号内容验证它们。 不过，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不会在验证后删除摘要。 您可能希望定期删除这些摘要以保持系统性能。  
  
## <a name="when-and-how-to-delete-digests"></a>何时及如何删除摘要  
 摘要存储在 BTARNDATA 数据库的 MessageDigestHelper 表中。 若要定期从表中删除这些摘要，您可以使用存储过程仅删除那些早于某段时间的摘要。 MessageDigestHelper 表中包含`TimeCreated`属性，可以使用实现此目的。  
  
 请使用以下 SQL 语句创建存储过程（可根据您的目的修改），并运行存储过程来删除旧摘要。 此示例语句删除所有保存了七天以上的摘要：  
  
```  
delete from MessageDigestHelper where datediff(day, TimeCreated, getutcdate()) > 7  
```  
  
> [!NOTE]
>  存储的过程必须包括对`getutcdate`，而非`getdate`，因为所有[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库使用 UTC （协调通用时间） 时间。  
  
## <a name="see-also"></a>请参阅  
 [维护 BTARN 数据库](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)