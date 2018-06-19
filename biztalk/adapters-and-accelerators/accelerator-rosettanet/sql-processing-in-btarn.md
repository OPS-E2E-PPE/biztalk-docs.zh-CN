---
title: SQL 中 BTARN 处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- LOBs
- SQL processing
- messages, message flow
- BTARN, SQL processing
ms.assetid: cfaf804f-3803-438e-a22e-50f487fe21c3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24798038ef7110a87efef2850c7787c066ae9511
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005054"
---
# <a name="sql-processing-in-btarn"></a>SQL 中 BTARN 处理
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]使用 SQL 适配器路由中的业务线 (LOB) 应用程序的消息。 它使用 SQL 发送端口将消息路由至 LOB 应用程序。  
  
## <a name="message-flow"></a>消息流  
 发起方还是响应方计算机，在后端 LOB 应用程序将消息路由到的 MessagesFromLOB 表[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]使用 SQL 适配器将消息从 MessagesFromLOB 表移动到专用的流程。 有关详细信息，请参阅 BizTalk Server 帮助中的"SQL 适配器"。  
  
 您可以选择使用 FILE 适配器（而不是使用默认的 SQL 适配器）将服务内容提交给 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。 如果你选择使用一个文件适配器，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不支持附件。  
  
## <a name="see-also"></a>另请参阅  
 [BTARN 中的消息处理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)