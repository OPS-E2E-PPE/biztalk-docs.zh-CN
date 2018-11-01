---
title: 与使用的 WCF 服务的 SOAP 标头 |Microsoft Docs
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
ms.sourcegitcommit: e172dedfd00d4de3a40c8289f3a97ef65cdadd3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2018
ms.locfileid: "22277485"
---
# <a name="soap-headers-with-consumed-wcf-services"></a><span data-ttu-id="57da7-102">SOAP 标头与使用的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="57da7-102">SOAP Headers with Consumed WCF Services</span></span>
<span data-ttu-id="57da7-103">若要将消息发送到 WCF 服务与自定义 SOAP 标头，这些标头必须设置 （在示例中的表达式形状） 的业务流程和管道组件 （在代码中） 中为上下文属性**OutboundCustomHeaders**。</span><span class="sxs-lookup"><span data-stu-id="57da7-103">To send a message to a WCF service with the custom SOAP headers, these headers must be set in your orchestrations (in the Expression shape, for example) and pipeline components (in code) as the context property **OutboundCustomHeaders**.</span></span> <span data-ttu-id="57da7-104">此上下文属性位于目标命名空间 http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties ，并包含自定义 SOAP 标头的字符串表示形式。 </span><span class="sxs-lookup"><span data-stu-id="57da7-104">This context property is in the target namespace **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**, and contains string representations of the custom SOAP headers.</span></span>  
  
 <span data-ttu-id="57da7-105">以下 XML 传出消息中的数据显示的自定义 SOAP 标头的字符串表示形式示例**OutboundCustomHeaders**属性：</span><span class="sxs-lookup"><span data-stu-id="57da7-105">The data in the following XML outgoing message shows an example of the string representation of custom SOAP headers for the **OutboundCustomHeaders** property:</span></span>  
  
```  
<headers>  
<Origination xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader">Home</Origination>  
<Destination xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader">Work</Destination>  
</headers>  
```  
  
 <span data-ttu-id="57da7-106">入站 SOAP 标头还包含 SOAP 标头的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="57da7-106">Inbound SOAP headers also contain string representations of the SOAP headers.</span></span> <span data-ttu-id="57da7-107">此值类似于创建一个请求 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="57da7-107">The values are similar to creating a request SOAP header.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57da7-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="57da7-108">In This Section</span></span>  
  
-   [<span data-ttu-id="57da7-109">通过业务流程使用 WCF 消息中的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="57da7-109">Using SOAP Headers in WCF Messages with Orchestrations</span></span>](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md)  
  
-   [<span data-ttu-id="57da7-110">通过管道组件使用 WCF 消息中的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="57da7-110">Using SOAP Headers in WCF Messages with Pipeline Components</span></span>](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)  
  
## <a name="see-also"></a><span data-ttu-id="57da7-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="57da7-111">See Also</span></span>  
 <span data-ttu-id="57da7-112">[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="57da7-112">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="57da7-113">SOAP 标头与已发布的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="57da7-113">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)