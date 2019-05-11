---
title: CorrelationID | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4faf210-7e7f-450d-8bb1-84d3d31c3022
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 374ae165d48e1d91bc60d83a285df3b0f3594357
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354427"
---
# <a name="correlationid"></a>CorrelationID
`CorrelationID`元素用于指定一条消息的相关 ID。  
  
## <a name="format"></a>格式  
 `CorrelationID`元素组成`Expression`元素使用一个或多个`Operation`元素，以指定的字符串以用作相关 id。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="remarks"></a>备注  
 Correlation ID 表达式中不允许以下常见运算：  
  
-   And  
  
-   等于  
  
## <a name="example"></a>示例  
 以下 Workflow Foundation (WF) 侦听器示例配置块使用"OrderNum"建立一个相关 id。 使用 WF 和常用操作，可以构建复杂的表达式构造工作流的适当的相关 ID。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>OrderNum</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 对于 Windows Communication Foundation (WCF) 应用程序，您可以使用特定于 WCF 的和常用操作构造相关 id。 下面的示例使用**XPath**操作和 XPath 从将其用作相关 ID 的消息中检索信用卡卡号：  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wcf:Operation Name ="XPath">  
      <wcf:Argument>//s:Body/creditCard:CreditCardNumber</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a>请参阅  
 [侦听器 OnEvent 元素](../core/interceptor-onevent-element.md)