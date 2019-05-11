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
# <a name="correlationid"></a><span data-ttu-id="0bee6-102">CorrelationID</span><span class="sxs-lookup"><span data-stu-id="0bee6-102">CorrelationID</span></span>
<span data-ttu-id="0bee6-103">`CorrelationID`元素用于指定一条消息的相关 ID。</span><span class="sxs-lookup"><span data-stu-id="0bee6-103">The `CorrelationID` element is used to specify a correlation ID for a message.</span></span>  
  
## <a name="format"></a><span data-ttu-id="0bee6-104">格式</span><span class="sxs-lookup"><span data-stu-id="0bee6-104">Format</span></span>  
 <span data-ttu-id="0bee6-105">`CorrelationID`元素组成`Expression`元素使用一个或多个`Operation`元素，以指定的字符串以用作相关 id。</span><span class="sxs-lookup"><span data-stu-id="0bee6-105">The `CorrelationID` element consists of an `Expression` element that uses one or more `Operation` elements to specify the string to use as the correlation ID.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="remarks"></a><span data-ttu-id="0bee6-106">备注</span><span class="sxs-lookup"><span data-stu-id="0bee6-106">Remarks</span></span>  
 <span data-ttu-id="0bee6-107">Correlation ID 表达式中不允许以下常见运算：</span><span class="sxs-lookup"><span data-stu-id="0bee6-107">The following common operations are not allowed in correlation ID expressions:</span></span>  
  
-   <span data-ttu-id="0bee6-108">And</span><span class="sxs-lookup"><span data-stu-id="0bee6-108">And</span></span>  
  
-   <span data-ttu-id="0bee6-109">等于</span><span class="sxs-lookup"><span data-stu-id="0bee6-109">Equals</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bee6-110">示例</span><span class="sxs-lookup"><span data-stu-id="0bee6-110">Example</span></span>  
 <span data-ttu-id="0bee6-111">以下 Workflow Foundation (WF) 侦听器示例配置块使用"OrderNum"建立一个相关 id。</span><span class="sxs-lookup"><span data-stu-id="0bee6-111">The following Workflow Foundation (WF) interceptor sample configuration block uses "OrderNum" to establish a correlation ID.</span></span> <span data-ttu-id="0bee6-112">使用 WF 和常用操作，可以构建复杂的表达式构造工作流的适当的相关 ID。</span><span class="sxs-lookup"><span data-stu-id="0bee6-112">Using the WF and common operations, you can build sophisticated expressions to construct an appropriate correlation ID for your workflow.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>OrderNum</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 <span data-ttu-id="0bee6-113">对于 Windows Communication Foundation (WCF) 应用程序，您可以使用特定于 WCF 的和常用操作构造相关 id。</span><span class="sxs-lookup"><span data-stu-id="0bee6-113">For Windows Communication Foundation (WCF) applications, you can use WCF-specific and common operations to construct a correlation ID.</span></span> <span data-ttu-id="0bee6-114">下面的示例使用**XPath**操作和 XPath 从将其用作相关 ID 的消息中检索信用卡卡号：</span><span class="sxs-lookup"><span data-stu-id="0bee6-114">The following sample uses the **XPath** operation and XPath to retrieve a credit card number from a message for use as a correlation ID:</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wcf:Operation Name ="XPath">  
      <wcf:Argument>//s:Body/creditCard:CreditCardNumber</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0bee6-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bee6-115">See Also</span></span>  
 [<span data-ttu-id="0bee6-116">侦听器 OnEvent 元素</span><span class="sxs-lookup"><span data-stu-id="0bee6-116">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)