---
title: AS2 解决方案体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41e493ba-919b-4520-9c12-92d6757984ef
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60f25fb229a37896846f81e37c3cc71e8419d854
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528861"
---
# <a name="as2-solution-architecture"></a>AS2 解决方案体系结构
AS2 处理是独立于 EDI 处理执行的。 AS2 消息的接收、处理以及确认的发送均独立于 EDI 负载的处理进行。 因此，AS2 处理与 EDI 处理的设计和配置也是分别完成的。 另外，可使用 AS2 传输 EDI 消息或非 EDI 消息。  
  
 本节介绍 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 AS2 解决方案的体系结构，包括端对端、接收端和发送端处理。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [AS2 消息传送](../core/as2-messaging.md)  
  
-   [协议在 AS2 处理中的角色](../core/the-role-of-agreements-in-as2-processing.md)  
  
-   [BizTalk Server 如何接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md)  
  
-   [BizTalk Server 如何发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md)