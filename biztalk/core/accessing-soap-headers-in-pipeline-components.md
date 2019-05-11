---
title: 访问在管道组件中的 SOAP 标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, pipelines
- SOAP headers, properties
- pipelines, SOAP headers
ms.assetid: a2fb074e-0fde-487e-a6ec-7e2b543b7c8b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1acb8f56a4318695584abb074ddfcc0cf0c28c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361923"
---
# <a name="accessing-soap-headers-in-pipeline-components"></a>访问在管道组件中的 SOAP 标头
你可以访问在管道组件中的 SOAP 标头上下文属性。 使用上下文属性名称和目标命名空间的组合**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**。  
  
 下面的代码示例获取请求的 SOAP 标头中接收管道组件的属性**OrigDest**:  
  
```  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
   try  
   {  
   string stringVar = inmsg.Context.Read("OrigDest",    "http://schemas.microsoft.com/BizTalk/2003/SOAPHeader").ToString();  
   }  
   catch (Exception ex)  
   {  
   throw new Exception("Pipeline component exception - " + ex.Message);  
   }  
return inmsg;  
}  
```  
  
 有关管道组件的详细信息，请参阅[开发自定义管道组件](../core/developing-custom-pipeline-components.md)。  
  
## <a name="see-also"></a>另请参阅  
 [与发布的 Web 服务的 SOAP 标头](../core/soap-headers-with-published-web-services.md)