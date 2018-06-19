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
# <a name="correlationid"></a><span data-ttu-id="07db7-102">CorrelationID</span><span class="sxs-lookup"><span data-stu-id="07db7-102">CorrelationID</span></span>
<span data-ttu-id="07db7-103">`CorrelationID` 元素用于为消息指定一个相关 ID。</span><span class="sxs-lookup"><span data-stu-id="07db7-103">The `CorrelationID` element is used to specify a correlation ID for a message.</span></span>  
  
## <a name="format"></a><span data-ttu-id="07db7-104">格式</span><span class="sxs-lookup"><span data-stu-id="07db7-104">Format</span></span>  
 <span data-ttu-id="07db7-105">`CorrelationID` 元素由一个 `Expression` 元素组成，后者使用一个或多个 `Operation` 元素指定要用作相关 ID 的字符串。</span><span class="sxs-lookup"><span data-stu-id="07db7-105">The `CorrelationID` element consists of an `Expression` element that uses one or more `Operation` elements to specify the string to use as the correlation ID.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="remarks"></a><span data-ttu-id="07db7-106">注释</span><span class="sxs-lookup"><span data-stu-id="07db7-106">Remarks</span></span>  
 <span data-ttu-id="07db7-107">correlation ID 表达式中不允许使用以下常见运算：</span><span class="sxs-lookup"><span data-stu-id="07db7-107">The following common operations are not allowed in correlation ID expressions:</span></span>  
  
-   <span data-ttu-id="07db7-108">And</span><span class="sxs-lookup"><span data-stu-id="07db7-108">And</span></span>  
  
-   <span data-ttu-id="07db7-109">等于</span><span class="sxs-lookup"><span data-stu-id="07db7-109">Equals</span></span>  
  
## <a name="example"></a><span data-ttu-id="07db7-110">示例</span><span class="sxs-lookup"><span data-stu-id="07db7-110">Example</span></span>  
 <span data-ttu-id="07db7-111">以下 Workflow Foundation (WF) 侦听器示例配置块使用“OrderNum”建立一个相关 ID。</span><span class="sxs-lookup"><span data-stu-id="07db7-111">The following Workflow Foundation (WF) interceptor sample configuration block uses "OrderNum" to establish a correlation ID.</span></span> <span data-ttu-id="07db7-112">使用 WF 和常用操作，可以建立复杂的表达式，为工作流构造适当的相关 ID。</span><span class="sxs-lookup"><span data-stu-id="07db7-112">Using the WF and common operations, you can build sophisticated expressions to construct an appropriate correlation ID for your workflow.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>OrderNum</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 <span data-ttu-id="07db7-113">对于 Windows Communication Foundation (WCF) 应用程序，可以使用特定于 WCF 的操作及常用操作构造相关 ID。</span><span class="sxs-lookup"><span data-stu-id="07db7-113">For Windows Communication Foundation (WCF) applications, you can use WCF-specific and common operations to construct a correlation ID.</span></span> <span data-ttu-id="07db7-114">下面的示例使用**XPath**操作和 XPath 从消息以用作相关 ID 检索信用卡卡号：</span><span class="sxs-lookup"><span data-stu-id="07db7-114">The following sample uses the **XPath** operation and XPath to retrieve a credit card number from a message for use as a correlation ID:</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wcf:Operation Name ="XPath">  
      <wcf:Argument>//s:Body/creditCard:CreditCardNumber</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a><span data-ttu-id="07db7-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07db7-115">See Also</span></span>  
 [<span data-ttu-id="07db7-116">拦截器 OnEvent 元素</span><span class="sxs-lookup"><span data-stu-id="07db7-116">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)