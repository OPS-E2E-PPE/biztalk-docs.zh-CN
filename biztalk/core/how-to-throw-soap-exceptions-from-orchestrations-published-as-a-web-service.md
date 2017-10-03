---
title: "作为 Web 服务如何支持业务流程引发 SOAP 异常发布 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, SOAP exceptions
- orchestrations, SOAP errors
- Web services, orchestrations
ms.assetid: e1c7cd74-d1c8-4b9d-a418-4601b1f040d7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4ef3d975632b6230cf1e3df299d0d9455f39da0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service"></a>如何从作为 Web 服务发布的业务流程引发 SOAP 异常
你可以从业务流程中已发布作为 Web 服务返回 SOAP 异常。 将错误消息添加到 SOAP 端口和发送错误消息，而不是响应。  
  
### <a name="to-throw-a-soap-exception-from-an-orchestration-published-as-a-web-service"></a>若要引发 SOAP 异常从业务流程发布作为 Web 服务  
  
1.  将错误消息添加到 SOAP 端口类型。 错误消息的消息类型可以是任何符合 XML 架构 (XSD) 架构或简单类型。  
  
    > [!NOTE]
    >  返回一个字符串作为**SoapException**错误信息，你可以使用简单类型字符串，作为错误消息类型。  
  
2.  在您的业务流程，将创建的错误消息。  
  
3.  使用**发送**形状链接到与 SOAP 端口对应的错误消息中的错误操作。 SOAP 异常会包装返回的错误消息。  
  
 如果您的业务流程不返回错误，使用不同**发送**形状将使用正常响应操作标准的 SOAP 响应消息发送。  
  
## <a name="see-also"></a>另请参阅  
 [错误消息](../core/fault-messages.md)   
 [发布作为 Web 服务业务流程](../core/publishing-an-orchestration-as-a-web-service.md)