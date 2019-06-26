---
title: 使用 Web 服务使用 SOAP 标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, consuming
- Web services, consuming
- Web services, SOAP headers
- SOAP headers, Web services
ms.assetid: c2dfe7d8-e2f0-4bc6-b79c-354d06a7ffd6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29781c8b68229e04d398a71d62b60b24ab04a3eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390265"
---
# <a name="consuming-web-services-with-soap-headers"></a><span data-ttu-id="cac50-102">使用 SOAP 标头使用的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="cac50-102">Consuming Web Services with SOAP Headers</span></span>
<span data-ttu-id="cac50-103">使用具有定义的 SOAP 标头的 Web 服务后，这些标头可供你的业务流程和管道组件作为上下文属性。</span><span class="sxs-lookup"><span data-stu-id="cac50-103">After you consume a Web service with defined SOAP headers, these headers become available to your orchestrations and pipeline components as context properties.</span></span> <span data-ttu-id="cac50-104">这些上下文属性包含的 SOAP 标头的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="cac50-104">These context properties contain string representations of the SOAP headers.</span></span> <span data-ttu-id="cac50-105">对于 Web 服务中每个定义 SOAP 标头，你可以使用对应于 SOAP 标头的根元素的名称来创建上下文属性。</span><span class="sxs-lookup"><span data-stu-id="cac50-105">For each defined SOAP header in the Web service, you can create a context property by using the name that corresponds to the root element of the SOAP header.</span></span> <span data-ttu-id="cac50-106">定义的 SOAP 标头上下文属性位于 **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader** 命名空间。</span><span class="sxs-lookup"><span data-stu-id="cac50-106">All defined SOAP header context properties are in the **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader** namespace.</span></span>  
  
 <span data-ttu-id="cac50-107">下面的示例演示如何创建 SOAP 标头上下文属性**OrigDest**使用中的 SOAP 标头示例[与使用 Web 服务的 SOAP 标头](../core/soap-headers-with-consumed-web-services.md):</span><span class="sxs-lookup"><span data-stu-id="cac50-107">The following example shows how to create a SOAP header context property **OrigDest** using the SOAP header example in [SOAP Headers with Consumed Web Services](../core/soap-headers-with-consumed-web-services.md):</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<OrigDest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns=" http://SOAPHeaderWS.ItemAvailability">  
   <Origination xmlns="">Home</Origination>  
      <Destination xmlns="">Work</Destination>  
</OrigDest>  
```  
  
 <span data-ttu-id="cac50-108">响应 SOAP 标头还包含定义 SOAP 标头的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="cac50-108">Response SOAP headers also contain string representations of the defined SOAP header.</span></span> <span data-ttu-id="cac50-109">此值类似于创建一个请求 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="cac50-109">The values are similar to creating a request SOAP header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac50-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cac50-110">See Also</span></span>  
 [<span data-ttu-id="cac50-111">与使用的 Web 服务的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="cac50-111">SOAP Headers with Consumed Web Services</span></span>](../core/soap-headers-with-consumed-web-services.md)