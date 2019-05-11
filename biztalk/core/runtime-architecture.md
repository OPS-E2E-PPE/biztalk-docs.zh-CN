---
title: 运行时体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- runtime, architecture
- architecture, runtime
- runtime
ms.assetid: feff9a84-f19b-44c9-8d05-8e6015bb1ef9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b6b7a01f8919a1c2bee415df3733394462d59f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393976"
---
# <a name="runtime-architecture"></a>运行时体系结构
然后再进行查看更多详细信息中的各种组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，很重要，必须了解如何将这些组件组合到产品的整体体系结构。 BizTalk Server 运行时是基于发布/订阅体系结构构建其中一条消息是发布到系统，，然后由一个或多个活动订户接收。 此体系结构的不同方式存在，但 BizTalk Server 中实现的模型通常称为*基于内容的发布/订阅*。  
  
 在基于内容的发布/订阅模型中，订阅服务器指定他们想要接收使用一组消息有关的条件的消息。 在发布时计算消息和所有具有匹配订阅 （由筛选器表达式指示），活动订户接收消息。 适用于 BizTalk Server，基于内容的少量的用词不当，但是，是因为用于生成订阅的条件，而无需来自消息内容，并且可能包括有关消息的上下文信息。 有关订阅机制的详细信息，请参阅[发布和订阅体系结构](../core/publish-and-subscribe-architecture.md)。  
  
 以下各节介绍了 BizTalk Server 运行时体系结构的各种组件。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [BizTalk Server 消息](../core/the-biztalk-server-message.md)  
  
-   [消息的生命周期](../core/lifecycle-of-a-message.md)  
  
-   [处理消息](../core/processing-the-message.md)  
  
-   [请求-响应消息](../core/request-response-messaging.md)  
  
-   [消息引擎](../core/the-messaging-engine.md)  
  
-   [实体](../core/entities.md)  
  
-   [项目](../core/artifacts.md)  
  
-   [企业单一登录 (SSO)](../core/enterprise-single-sign-on-sso.md)  
  
-   [业务规则引擎](../core/business-rules-engine.md)  
  
-   [BizTalk 程序集](../core/biztalk-assemblies.md)