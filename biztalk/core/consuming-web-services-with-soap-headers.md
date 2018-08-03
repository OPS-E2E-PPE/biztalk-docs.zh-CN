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
ms.openlocfilehash: 45a3efa628e435092505fdc3884704baa15be34c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237805"
---
# <a name="consuming-web-services-with-soap-headers"></a>使用 SOAP 标头使用的 Web 服务
使用具有定义的 SOAP 标头的 Web 服务后，这些标头可供你的业务流程和管道组件作为上下文属性。 这些上下文属性包含的 SOAP 标头的字符串表示形式。 对于 Web 服务中每个定义 SOAP 标头，你可以使用对应于 SOAP 标头的根元素的名称来创建上下文属性。 所有定义的 SOAP 标头上下文属性位于**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**命名空间。  
  
 下面的示例演示如何创建 SOAP 标头上下文属性**OrigDest**使用中的 SOAP 标头示例[与使用 Web 服务的 SOAP 标头](../core/soap-headers-with-consumed-web-services.md):  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<OrigDest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns=" http://SOAPHeaderWS.ItemAvailability">  
   <Origination xmlns="">Home</Origination>  
      <Destination xmlns="">Work</Destination>  
</OrigDest>  
```  
  
 响应 SOAP 标头还包含定义 SOAP 标头的字符串表示形式。 此值类似于创建一个请求 SOAP 标头。  
  
## <a name="see-also"></a>另请参阅  
 [与使用的 Web 服务的 SOAP 标头](../core/soap-headers-with-consumed-web-services.md)