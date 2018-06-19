---
title: 与使用的 WCF 服务的 SOAP 标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- SOAP headers, WCF services
- consuming, SOAP headers
- WCF services, SOAP headers
- SOAP headers, consuming [WCF services]
ms.assetid: 0582ee26-b549-4b50-b365-36824010dab0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f60e0ae7f9cf2e6a224ce9d919c7c4d5e6f3119c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277485"
---
# <a name="soap-headers-with-consumed-wcf-services"></a>SOAP 标头与使用的 WCF 服务
若要将消息发送到 WCF 服务与自定义 SOAP 标头，这些标头必须设置在你的业务流程 （在表达式形状中，例如中） 和 （在代码中） 的管道组件中为上下文属性**OutboundCustomHeaders**。 此上下文属性是目标命名空间中**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**，并包含的自定义 SOAP 标头的字符串表示形式。  
  
 下面的 XML 传出消息中的数据显示的字符串表示形式的自定义 SOAP 标头的示例**OutboundCustomHeaders**属性：  
  
```  
<headers>  
<Origination xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader">Home</Origination>  
<Destination xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader">Work</Destination>  
</headers>  
```  
  
 入站 SOAP 标头还包含 SOAP 标头的字符串表示形式。 此值类似于创建一个请求 SOAP 标头。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在与业务流程的 WCF 消息中使用 SOAP 标头](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md)  
  
-   [在与管道组件的 WCF 消息中使用 SOAP 标头](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)  
  
## <a name="see-also"></a>另请参阅  
 [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)   
 [与已发布的 WCF 服务的 SOAP 标头](../core/soap-headers-with-published-wcf-services.md)