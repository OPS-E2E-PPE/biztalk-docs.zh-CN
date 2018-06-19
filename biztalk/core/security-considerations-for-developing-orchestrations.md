---
title: 有关开发业务流程的安全注意事项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, orchestrations
- messages, subscriptions
- orchestrations, security
- messages, security
ms.assetid: a29b2018-4a8f-49ad-a817-6f279db3f801
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e020759a8d389461978a4de4138bcc139d527539
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269317"
---
# <a name="security-considerations-for-developing-orchestrations"></a>有关开发业务流程的安全注意事项
在设计业务流程时，应考虑潜在的安全问题。  
  
## <a name="avoid-subscriptions-based-on-content-from-untrusted-messages"></a>避免基于来自不可信消息的内容的订阅  
 为确保低权限的消息不会启动可能基于该消息内容或上下文创建订阅的业务流程实例，强烈建议您的业务流程不要基于不可信消息的内容或上下文来创建其消息订阅。  
  
 有关中的安全信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[保护 BizTalk Server](../core/securing-biztalk-server.md)。  
  
## <a name="see-also"></a>另请参阅  
 [创建业务流程](../core/creating-orchestrations.md)   
 [有关业务流程](../core/about-orchestrations.md)