---
title: 发布 Web 服务服务与 SOAP 标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, code samples
- SOAP headers, pipelines
- SOAP headers, BizTalk Web Services Publishing Wizard
- pipelines, SOAP headers
- orchestrations, SOAP headers
ms.assetid: c362caff-b75f-4c1b-9013-d2b9c74f5c65
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7baf6af0e4505e448a854fe6def372614bfdaa49
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269021"
---
# <a name="publishing-web-services-with-soap-headers"></a>使用 SOAP 标头的发布 Web 服务
运行 BizTalk Web Services 发布向导时，会将 SOAP 标头添加到 Web Services 中。 当发布支持 SOAP 标头的 Web 服务时，标头可供业务流程和管道组件作为包含的 SOAP 标头的字符串表示形式之间实现的上下文属性。  
  
## <a name="defined-soap-headers"></a>已定义的 SOAP 标头  
 当使用向导添加已定义的 SOAP 标头时，向导会使用对应于 SOAP 标头的根元素的名称创建上下文属性。 所有定义的 SOAP 标头上下文属性具有命名空间**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**。 当 SOAP 适配器将 SOAP 请求转换为 BizTalk 消息时，它会创建一个 SOAP 标头上下文属性。  
  
 下面的示例显示一个简单的 SOAP 请求：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
       <soap:Header>  
             <OrigDest xmlns="http://SOAPHeaderWS.ItemAvailability">  
                    <Origination>Work</Origination>  
                    <Destination>Home</Destination>  
             </OrigDest>  
       </soap:Header>  
       <soap:Body>  
  
       </soap:Body>  
</soap:Envelope>  
```  
  
 对于简单的 SOAP 请求中，SOAP 适配器创建 BizTalk 消息具有一个 SOAP 标头的上下文属性**OrigDest**和字符串。  
  
 以下示例显示由 SOAP 适配器创建的字符串：  
  
```  
"<?xml version="1.0" encoding="utf-16"?><OrigDest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader"><Origination xmlns="">Home</Origination><Destination xmlns="">Work</Destination> </OrigDest>"  
```  
  
## <a name="unknown-soap-headers"></a>未知的 SOAP 标头  
 如果你选择在向导中支持未知的 SOAP 标头，向导将创建同名的上下文属性**UnknownHeaders**和命名空间**http://schemas.microsoft.com/BizTalk/2003/soap-properties**. **UnknownHeaders**上下文属性包含所有收到的未知 SOAP 标头。  
  
 例如，如果你收到具有根元素名称的未知的 SOAP 标头**CustomerGroup**、 **UnknownHeaders**上下文属性包含字符串：  
  
```  
"<?xml version="1.0" encoding="utf-16"?><UnknownHeaders><CustomerGroup xmlns="http://SOAPHeaderWS/CustomerGroup"><Id xmlns="">My Customer</Id>  
</CustomerGroup></UnknownHeaders>"  
```  
  
 有关添加定义 SOAP 标头或支持未知的 SOAP 标头，请参阅[发布作为 Web 服务业务流程](../core/publishing-an-orchestration-as-a-web-service.md)。 另请参阅[作为 Web 服务的发布架构](../core/publishing-schemas-as-a-web-service.md)。  
  
## <a name="see-also"></a>另请参阅  
 [与发布的 Web 服务的 SOAP 标头](../core/soap-headers-with-published-web-services.md)