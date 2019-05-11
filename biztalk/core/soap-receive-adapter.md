---
title: SOAP 接收适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, receive adapters
- receive adapters, SOAP adapters
ms.assetid: bb968fa8-0515-4f3a-bb39-9effb83e960c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 908554ad129fed6c99f4b8bb7e1b197cb4bc0ca6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244436"
---
# <a name="soap-receive-adapter"></a>SOAP 接收适配器
您可以使用 SOAP 接收适配器来接收 Web 服务请求。 SOAP 接收适配器创建一个 BizTalk 消息对象，并将升级到消息上下文关联的属性。  
  
 SOAP 接收的适配器 URI 必须关联到一个或多个 BizTalk 业务流程或架构的已发布为 web 服务与**BizTalk Web Services 发布向导**。 已发布的 web 服务公开一个或多个 BizTalk Server 业务流程或架构中的 BizTalk 程序集关联的一个或多个 web 方法。 实际上，已发布的 web 服务充当 BizTalk 业务流程或转发请求和响应客户端和 BizTalk 业务流程或架构之间的服务器代理。 有关发布 BizTalk 业务流程或架构作为 web 服务的详细信息请参阅[发布 Web Services](../core/publishing-web-services.md)。  
  
 使用 SOAP 适配器的接收位置可以配置为单向或请求响应 （双向）。 当单向接收位置配置为使用 SOAP 适配器时，关联的 web 服务调用绑定到接收端口的 BizTalk 程序集，并返回到客户端请求的状态。 当请求响应 （双向） 接收位置配置为使用 SOAP 适配器时，关联的 web 服务调用绑定到接收端口的 BizTalk 程序集，并将响应文档返回到客户端。 有关请求响应消息传送的详细信息请参阅[请求-响应消息传送](../core/request-response-messaging.md)。  
  
## <a name="see-also"></a>请参阅  
 [SOAP 适配器是什么？](../core/what-is-the-soap-adapter.md)   
 [SOAP 适配器的安全建议](../core/soap-adapter-security-recommendations.md)