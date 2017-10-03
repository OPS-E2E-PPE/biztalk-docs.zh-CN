---
title: "什么是 WCF-Custom 适配器？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-Custom adapters, about WCF-Custom adapters
ms.assetid: 7b2178dd-f737-4784-9bcb-e2b3979bfb0d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e090f82bc43d96dc14295af2fac2807cf1fd137
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-custom-adapter"></a>什么是 WCF-Custom 适配器？
WCF-Custom 适配器用于在 BizTalk Server 中启用 WCF 扩展性组件。 该适配器为 WCF 框架赋予了完整的灵活性。 用户使用此适配器可以为接收位置和发送端口选择和配置 WCF 绑定。 它还允许用户设置终结点行为和安全设置。  
  
 WCF-Custom 适配器由两个适配器组成：一个接收适配器和一个发送适配器。  
  
 **WCF 自定义接收适配器**  
  
 使用 WCF-Custom 接收适配器可通过在接收位置中的传输属性对话框中选择和配置的绑定、服务行为、终结点行为、安全机制以及入站消息正文的来源接收 WCF 服务请求。 使用 WCF-Custom 接收适配器的接收位置可以配置为单向或请求-响应（双向）。  
  
 **WCF 自定义发送适配器**  
  
 使用 WCF-Custom 发送适配器可通过您选择和配置的无类型约定（带有绑定）、服务行为、终结点行为、安全机制以及出站消息正文的来源调用 WCF 服务。  
  
 有关 WCF 的详细信息接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置 WCF 自定义适配器](../core/configuring-the-wcf-custom-adapter.md)   
 [WCF 适配器](../core/wcf-adapters.md)