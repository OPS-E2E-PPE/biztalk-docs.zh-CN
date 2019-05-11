---
title: 如何从业务流程引发 SOAP 异常发布为 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, SOAP exceptions
- orchestrations, SOAP errors
- Web services, orchestrations
ms.assetid: e1c7cd74-d1c8-4b9d-a418-4601b1f040d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12c849d592a7cdce5968678f524ec15562830eba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333795"
---
# <a name="how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service"></a>如何从发布为 Web 服务的业务流程引发 SOAP 异常
你可以从业务流程发布为 Web 服务返回 SOAP 异常。 将错误消息添加到 SOAP 端口和发送错误消息而不是响应。  
  
### <a name="to-throw-a-soap-exception-from-an-orchestration-published-as-a-web-service"></a>若要引发 SOAP 异常从业务流程发布为 Web 服务  
  
1. 将错误消息添加到 SOAP 端口类型。 错误消息的消息类型可以是任何符合的 XML 架构 (XSD) 架构或简单类型。  
  
   > [!NOTE]
   >  返回一个字符串作为**SoapException**错误信息，可以使用简单类型字符串，作为错误消息类型。  
  
2. 在业务流程中创建的错误消息。  
  
3. 使用**发送**形状链接到对应于错误消息的 SOAP 端口中的错误操作。 SOAP 异常包装返回的错误消息。  
  
   如果您的业务流程不返回错误，使用不同**发送**用于将使用正常响应操作的标准 SOAP 响应消息的发送形状。  
  
## <a name="see-also"></a>请参阅  
 [错误消息](../core/fault-messages.md)   
 [将业务流程发布为 Web 服务](../core/publishing-an-orchestration-as-a-web-service.md)