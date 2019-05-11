---
title: 发送和接收大型消息使用 MSMQ 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, large messages
- configuring [MSMQ adapters], large messages
- MSMQ adapters, large messages
ms.assetid: 208efbed-7b58-4da5-ba27-65a315c2713b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b5a1267aa0ee1ffc2d44326ad8922d6fac16a1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399032"
---
# <a name="sending-and-receiving-large-messages-using-the-msmq-adapter"></a>发送和接收大型消息使用 MSMQ 适配器
MSMQ 适配器默认消息处理部分取决于，，消息的大小。 一条消息时不超过四个兆字节 (4 MB)，MSMQ 适配器将使用.NET Framework 类库。 否则，它使用大消息扩展中 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 如果你的应用程序一致地接收或发送大消息，你可能需要控制适配器使用的内存量。 有关节省内存的详细信息，请参阅[优化性能的 MSMQ 适配器](../core/optimizing-performance-of-the-msmq-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
 [优化 MSMQ 适配器的性能](../core/optimizing-performance-of-the-msmq-adapter.md)   
 [配置 MSMQ 适配器](../core/configuring-the-msmq-adapter.md)