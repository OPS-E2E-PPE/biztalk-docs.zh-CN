---
title: 如何配置构造消息形状 |Microsoft Docs
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
ms.openlocfilehash: 8a16900b1ee5c98c059b01f92a770f845330b9ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386169"
---
# <a name="how-to-configure-the-construct-message-shape"></a>如何配置构造消息形状
![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")  
构造消息形状  
  
 指定你想要构造，消息变量，并对消息或其成分进行赋值。 对任何给定消息的所有分配必须都发生在同一构造消息形状。  
  
 如果你想要修改已构造的消息的属性 — 例如已收到的消息，必须通过将第一个分配到第二个，然后修改新的消息实例; 属性来构造新的消息实例构造和修改发生在同一构造消息形状内。  
  
### <a name="to-configure-a-construct-message-shape"></a>若要配置构造消息形状  
  
1.  在属性窗口中，使用**构造的消息**属性指定的消息此形状将构造。  
  
2.  添加并配置一个或多个**转换**或**消息赋值**形状内**构造消息形状**。