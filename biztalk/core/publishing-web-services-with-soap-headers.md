---
title: "发布 Web 服务服务与 SOAP 标头 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, code samples
- SOAP headers, pipelines
- SOAP headers, BizTalk Web Services Publishing Wizard
- pipelines, SOAP headers
- orchestrations, SOAP headers
ms.assetid: c362caff-b75f-4c1b-9013-d2b9c74f5c65
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7baf6af0e4505e448a854fe6def372614bfdaa49
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-web-services-with-soap-headers"></a><span data-ttu-id="703d6-102">使用 SOAP 标头的发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="703d6-102">Publishing Web Services with SOAP Headers</span></span>
<span data-ttu-id="703d6-103">运行 BizTalk Web Services 发布向导时，会将 SOAP 标头添加到 Web Services 中。</span><span class="sxs-lookup"><span data-stu-id="703d6-103">You add SOAP headers to your Web services when you run the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="703d6-104">当发布支持 SOAP 标头的 Web 服务时，标头可供业务流程和管道组件作为包含的 SOAP 标头的字符串表示形式之间实现的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="703d6-104">When you publish a Web service that supports SOAP headers, the headers become available to orchestrations and pipeline components as context properties that contain string representations of the SOAP headers.</span></span>  
  
## <a name="defined-soap-headers"></a><span data-ttu-id="703d6-105">已定义的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="703d6-105">Defined SOAP headers</span></span>  
 <span data-ttu-id="703d6-106">当使用向导添加已定义的 SOAP 标头时，向导会使用对应于 SOAP 标头的根元素的名称创建上下文属性。</span><span class="sxs-lookup"><span data-stu-id="703d6-106">When you add a defined SOAP header using the wizard, the wizard creates a context property with a name that corresponds to the root element of the SOAP header.</span></span> <span data-ttu-id="703d6-107">所有定义的 SOAP 标头上下文属性具有命名空间**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**。</span><span class="sxs-lookup"><span data-stu-id="703d6-107">All defined SOAP header context properties have the namespace **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**.</span></span> <span data-ttu-id="703d6-108">当 SOAP 适配器将 SOAP 请求转换为 BizTalk 消息时，它会创建一个 SOAP 标头上下文属性。</span><span class="sxs-lookup"><span data-stu-id="703d6-108">When the SOAP adapter converts the SOAP request to a BizTalk message, it creates one SOAP header context property.</span></span>  
  
 <span data-ttu-id="703d6-109">下面的示例显示一个简单的 SOAP 请求：</span><span class="sxs-lookup"><span data-stu-id="703d6-109">The following example shows a simple SOAP request:</span></span>  
  
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
  
 <span data-ttu-id="703d6-110">对于简单的 SOAP 请求中，SOAP 适配器创建 BizTalk 消息具有一个 SOAP 标头的上下文属性**OrigDest**和字符串。</span><span class="sxs-lookup"><span data-stu-id="703d6-110">For the simple SOAP request, the SOAP adapter created a BizTalk message with one SOAP header context property **OrigDest** and the string.</span></span>  
  
 <span data-ttu-id="703d6-111">以下示例显示由 SOAP 适配器创建的字符串：</span><span class="sxs-lookup"><span data-stu-id="703d6-111">The following example shows the string created by the SOAP adapter:</span></span>  
  
```  
"<?xml version="1.0" encoding="utf-16"?><OrigDest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader"><Origination xmlns="">Home</Origination><Destination xmlns="">Work</Destination> </OrigDest>"  
```  
  
## <a name="unknown-soap-headers"></a><span data-ttu-id="703d6-112">未知的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="703d6-112">Unknown SOAP headers</span></span>  
 <span data-ttu-id="703d6-113">如果你选择在向导中支持未知的 SOAP 标头，向导将创建同名的上下文属性**UnknownHeaders**和命名空间**http://schemas.microsoft.com/BizTalk/2003/soap-properties**.</span><span class="sxs-lookup"><span data-stu-id="703d6-113">If you choose to support unknown SOAP headers in the wizard, the wizard creates a context property with the name **UnknownHeaders** and the namespace **http://schemas.microsoft.com/BizTalk/2003/soap-properties**.</span></span> <span data-ttu-id="703d6-114">**UnknownHeaders**上下文属性包含所有收到的未知 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="703d6-114">The **UnknownHeaders** context property contains all of the received unknown SOAP headers.</span></span>  
  
 <span data-ttu-id="703d6-115">例如，如果你收到具有根元素名称的未知的 SOAP 标头**CustomerGroup**、 **UnknownHeaders**上下文属性包含字符串：</span><span class="sxs-lookup"><span data-stu-id="703d6-115">For example, if you receive an unknown SOAP header with the root element name, **CustomerGroup**, the **UnknownHeaders** context property contains the string:</span></span>  
  
```  
"<?xml version="1.0" encoding="utf-16"?><UnknownHeaders><CustomerGroup xmlns="http://SOAPHeaderWS/CustomerGroup"><Id xmlns="">My Customer</Id>  
</CustomerGroup></UnknownHeaders>"  
```  
  
 <span data-ttu-id="703d6-116">有关添加定义 SOAP 标头或支持未知的 SOAP 标头，请参阅[发布作为 Web 服务业务流程](../core/publishing-an-orchestration-as-a-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="703d6-116">For more information about adding defined SOAP headers or supporting unknown SOAP headers, see [Publishing an Orchestration as a Web Service](../core/publishing-an-orchestration-as-a-web-service.md).</span></span> <span data-ttu-id="703d6-117">另请参阅[作为 Web 服务的发布架构](../core/publishing-schemas-as-a-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="703d6-117">Also see [Publishing Schemas as a Web Service](../core/publishing-schemas-as-a-web-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="703d6-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="703d6-118">See Also</span></span>  
 [<span data-ttu-id="703d6-119">与发布的 Web 服务的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="703d6-119">SOAP Headers with Published Web Services</span></span>](../core/soap-headers-with-published-web-services.md)