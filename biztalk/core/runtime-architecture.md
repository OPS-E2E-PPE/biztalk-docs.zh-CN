---
title: 运行时体系结构 |Microsoft 文档
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
ms.openlocfilehash: 9e45ac745dbf6704f06f61155b3f57edfdec9e09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268989"
---
# <a name="runtime-architecture"></a>运行时体系结构
然后再进行查看更多详细信息中的各种组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，具有组件到产品的总体体系结构的适合程度的了解是很重要。 BizTalk Server 运行时是基于发布/订阅结构建立的，在该结构中消息发布到系统，然后由一个或多个活动订户接收。 此体系结构的不同方式存在，但在 BizTalk Server 中实现此模型通常称为*基于内容的发布/订阅*。  
  
 在基于内容的发布/订阅模型中，订户使用有关消息的一组条件来指定要接收的消息。 在发布消息时对消息进行评估，具有匹配订阅（由筛选器表达式指明）的所有活动订户将接收该消息。 但是，在应用于 BizTalk Server 时，基于内容有点名不副实，因为用于生成订阅的条件不一定必须来自消息内容，还可以包括有关消息的上下文信息。 有关订阅机制的详细信息，请参阅[发布和订阅体系结构](../core/publish-and-subscribe-architecture.md)。  
  
 后面的部分将介绍 BizTalk Server 运行时结构的各种组件。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [BizTalk Server 消息](../core/the-biztalk-server-message.md)  
  
-   [消息的生命周期](../core/lifecycle-of-a-message.md)  
  
-   [处理消息](../core/processing-the-message.md)  
  
-   [请求-响应消息传送](../core/request-response-messaging.md)  
  
-   [消息传送的引擎](../core/the-messaging-engine.md)  
  
-   [实体](../core/entities.md)  
  
-   [项目](../core/artifacts.md)  
  
-   [企业单一登录 (SSO)](../core/enterprise-single-sign-on-sso.md)  
  
-   [业务规则引擎](../core/business-rules-engine.md)  
  
-   [BizTalk 程序集](../core/biztalk-assemblies.md)