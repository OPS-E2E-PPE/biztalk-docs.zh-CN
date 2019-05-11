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
# <a name="deleting-digests"></a>删除摘要
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]存储为传出消息的摘要，以便它可以根据信号内容验证它们。 但是，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不会验证后删除摘要。 定期，您可能想要删除这些摘要以保持系统性能。  
  
## <a name="when-and-how-to-delete-digests"></a>何时以及如何删除摘要  
 摘要存储在 BTARNDATA 数据库的 MessageDigestHelper 表中。 定期，您可能想要通过删除早于特定时间段的这些摘要的存储的过程从表中删除这些摘要。 MessageDigestHelper 表中包含`TimeCreated`属性，可以使用实现此目的。  
  
 使用以下 SQL 语句 （如修改您的要求），创建一个存储的过程并运行存储的过程来删除旧摘要。 此示例语句删除超过七天的所有摘要：  
  
```  
delete from MessageDigestHelper where datediff(day, TimeCreated, getutcdate()) > 7  
```  
  
> [!NOTE]
>  存储的过程必须包括对`getutcdate`，而非`getdate`，因为所有[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库使用 UTC （协调通用时间） 时间。  
  
## <a name="see-also"></a>请参阅  
 [维护 BTARN 数据库](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)