---
title: "SOAP 接收适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP adapters, receive adapters
- receive adapters, SOAP adapters
ms.assetid: bb968fa8-0515-4f3a-bb39-9effb83e960c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06fac19580d6083ed1b0d4be315d3285acf14fcc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="soap-receive-adapter"></a>SOAP 接收适配器
您可以使用 SOAP 接收适配器来接收 Web Services 请求。 SOAP 接收适配器可创建 BizTalk 消息对象，并将关联的属性升级到消息上下文中。  
  
 SOAP 接收 URI 必须关联到一个或多个 BizTalk 业务流程的适配器或作为 web 服务与已发布的架构**BizTalk Web 服务发布向导**。 已发布的 Web Services 公开一个或多个与 BizTalk 程序集中一个或多个 BizTalk Server 业务流程或架构关联的 Web 方法。 实际上，已发布的 Web Services 用作 BizTalk 业务流程或架构的服务器代理，在客户端与 BizTalk 业务流程或架构之间转发请求和响应。 有关发布 BizTalk 业务流程或作为 web 服务的架构的详细信息请参阅[发布 Web 服务](../core/publishing-web-services.md)。  
  
 使用 SOAP 适配器的接收位置可以配置为单向或请求响应（双向）。 当单向接收位置配置为使用 SOAP 适配器时，关联的 Web Services 会调用绑定到接收端口的 BizTalk 程序集，并将请求的状态返回给客户端。 当请求响应（双向）接收位置配置为使用 SOAP 适配器时，关联的 Web Services 会调用绑定到接收端口的 BizTalk 程序集，并将响应文档返回给客户端。 有关请求响应消息传送的详细信息请参阅[请求-响应消息传送](../core/request-response-messaging.md)。  
  
## <a name="see-also"></a>另请参阅  
 [什么是 SOAP 适配器？](../core/what-is-the-soap-adapter.md)   
 [SOAP 适配器安全建议](../core/soap-adapter-security-recommendations.md)