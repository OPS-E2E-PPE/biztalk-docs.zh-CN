---
title: 如何配置构造消息形状 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Construct Message shape [Orchestration Designer], configuring
- Construct Message shape [Orchestration Designer]
- configuring [Orchestration Designer], Construct Message shapes
- Construct Message shape [Orchestration Designer], about Construct Message shape
ms.assetid: 8d052b4e-0873-4102-9462-6604423d0524
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07b73e7fe62463767894808d7e95f12cf963e4dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248421"
---
# <a name="how-to-configure-the-construct-message-shape"></a>如何配置构造消息形状
![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")  
构造消息形状  
  
 指定要构造的消息变量，并对消息或其部分进行赋值。 必须在同一构造消息形状中对任何给定消息进行彻底赋值。  
  
 若要修改已构造的消息的属性（例如已收到的消息），必须构造新的消息实例，方法是：将第一个值赋予第二个值，然后在新的消息实例中修改该属性；在同一构造消息形状中同时发生了构造和修改操作。  
  
### <a name="to-configure-a-construct-message-shape"></a>若要配置构造消息形状  
  
1.  在属性窗口中，使用**消息构造**属性来指定哪些消息此形状将构造。  
  
2.  添加和配置一个或多个**转换**或**消息分配**内的形状**构造消息形状**。