---
title: CorrelationID |Microsoft 文档
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
ms.openlocfilehash: 1192de4a49c300220ce0b297bbc1ee02ce64c6dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237765"
---
# <a name="correlationid"></a>CorrelationID
`CorrelationID` 元素用于为消息指定一个相关 ID。  
  
## <a name="format"></a>格式  
 `CorrelationID` 元素由一个 `Expression` 元素组成，后者使用一个或多个 `Operation` 元素指定要用作相关 ID 的字符串。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="remarks"></a>注释  
 correlation ID 表达式中不允许使用以下常见运算：  
  
-   And  
  
-   等于  
  
## <a name="example"></a>示例  
 以下 Workflow Foundation (WF) 侦听器示例配置块使用“OrderNum”建立一个相关 ID。 使用 WF 和常用操作，可以建立复杂的表达式，为工作流构造适当的相关 ID。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>OrderNum</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 对于 Windows Communication Foundation (WCF) 应用程序，可以使用特定于 WCF 的操作及常用操作构造相关 ID。 下面的示例使用**XPath**操作和 XPath 从消息以用作相关 ID 检索信用卡卡号：  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wcf:Operation Name ="XPath">  
      <wcf:Argument>//s:Body/creditCard:CreditCardNumber</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a>另请参阅  
 [拦截器 OnEvent 元素](../core/interceptor-onevent-element.md)