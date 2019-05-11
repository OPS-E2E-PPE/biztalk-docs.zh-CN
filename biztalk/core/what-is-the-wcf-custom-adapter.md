---
title: 什么是 Wcf-custom 适配器？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom adapters, about WCF-Custom adapters
ms.assetid: 7b2178dd-f737-4784-9bcb-e2b3979bfb0d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eba1882957ed6974420d4827a43f90e1ef7ecba9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242759"
---
# <a name="what-is-the-wcf-custom-adapter"></a>什么是 Wcf-custom 适配器？
Wcf-custom 适配器用于启用 BizTalk Server 中的 WCF 扩展性组件使用。 该适配器能够完整 WCF 框架的灵活性。 它允许用户选择和配置 WCF 绑定的接收位置和发送端口。 它还允许用户设置终结点行为和安全设置。  
  
 WCF 自定义适配器由两个适配器组成： 一个接收适配器和一个发送适配器。  
  
 **WCF 自定义接收适配器**  
  
 使用 WCF 自定义接收适配器接收 WCF 服务请求通过绑定、 服务行为、 终结点行为、 安全机制和入站消息源的正文您选择和配置中的传输属性对话框中接收位置。 使用 Wcf-custom 接收适配器的接收位置可以配置为单向或请求-响应 （双向）。  
  
 **WCF 自定义发送适配器**  
  
 使用 Wcf-custom 发送适配器通过无类型协定的 WCF 服务调用具有绑定、 服务行为、 终结点行为、 安全机制和选择和配置的出站消息正文的源。  
  
 有关 WCF 接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。  
  
## <a name="see-also"></a>请参阅  
 [配置 WCF 自定义适配器](../core/configuring-the-wcf-custom-adapter.md)   
 [WCF 适配器](../core/wcf-adapters.md)