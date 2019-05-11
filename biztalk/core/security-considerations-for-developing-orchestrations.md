---
title: 有关开发业务流程的安全注意事项 |Microsoft Docs
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
ms.openlocfilehash: e6d159a96052871796c102dc628dae2a06d85046
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280326"
---
# <a name="security-considerations-for-developing-orchestrations"></a>有关开发业务流程的安全注意事项
在设计您的业务流程时，应考虑潜在的安全问题。  
  
## <a name="avoid-subscriptions-based-on-content-from-untrusted-messages"></a>避免基于来自不可信消息的内容的订阅  
 若要确保低权限的消息不会启动业务流程实例可能无法创建基于消息内容或上下文的订阅，强烈建议您的业务流程不会创建其消息订阅基于内容或不受信任的消息的上下文。  
  
 有关中的安全性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[保护 BizTalk Server](../core/securing-biztalk-server.md)。  
  
## <a name="see-also"></a>请参阅  
 [创建业务流程](../core/creating-orchestrations.md)   
 [关于业务流程](../core/about-orchestrations.md)