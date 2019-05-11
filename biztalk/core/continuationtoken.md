---
title: ContinuationToken |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d4911fc-c6fb-4628-9177-bd723d4d8ebc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5509fe9ec6b4d1966af84e56ca1b1571ebc3f55
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390267"
---
# <a name="continuationtoken"></a><span data-ttu-id="b6d68-102">ContinuationToken</span><span class="sxs-lookup"><span data-stu-id="b6d68-102">ContinuationToken</span></span>
<span data-ttu-id="b6d68-103">使用继续标记来关联 BAM 基础结构中各种不同的信息。</span><span class="sxs-lookup"><span data-stu-id="b6d68-103">A continuation token is used to correlate heterogeneous information within the BAM infrastructure.</span></span> <span data-ttu-id="b6d68-104">请考虑一个业务流程来构造以下类型的消息：</span><span class="sxs-lookup"><span data-stu-id="b6d68-104">Consider a business process that constructs the following types of messages:</span></span>  
  
- <span data-ttu-id="b6d68-105">根据采购订单号标识的采购订单</span><span class="sxs-lookup"><span data-stu-id="b6d68-105">Purchase order identified by a purchase order number</span></span>  
  
- <span data-ttu-id="b6d68-106">由销售订单号标识的销售订单</span><span class="sxs-lookup"><span data-stu-id="b6d68-106">Sales order identified by a sales order number</span></span>  
  
- <span data-ttu-id="b6d68-107">由发货订单号标识的发货订单</span><span class="sxs-lookup"><span data-stu-id="b6d68-107">Shipping order identified by a shipping order number</span></span>  
  
  <span data-ttu-id="b6d68-108">在此过程中，有三个重要的标识符： 采购订单 ID、 销售订单 ID 和发货订单 id。</span><span class="sxs-lookup"><span data-stu-id="b6d68-108">In this process, there are three important identifiers: purchase order ID, sales order ID and shipping order ID.</span></span> <span data-ttu-id="b6d68-109">每个这些标识符向原始订单生存期内发出信号的重要事件，但无法直接关联。</span><span class="sxs-lookup"><span data-stu-id="b6d68-109">Each of these identifiers signals an important event in the lifetime of the original order, but they cannot be directly correlated.</span></span> <span data-ttu-id="b6d68-110">若要跟踪与采购订单相关的事件，必须标识各消息间共有的信息来帮助准确地关联事件的 BAM 跟踪基础结构。</span><span class="sxs-lookup"><span data-stu-id="b6d68-110">To track events related to a purchase order, the information that is common between the messages must be identified to help the BAM tracking infrastructure accurately correlate the events.</span></span>  
  
## <a name="format"></a><span data-ttu-id="b6d68-111">格式</span><span class="sxs-lookup"><span data-stu-id="b6d68-111">Format</span></span>  
 <span data-ttu-id="b6d68-112">继续标记包含一个表达式元素和一个或多个操作：</span><span class="sxs-lookup"><span data-stu-id="b6d68-112">A continuation token consists of an expression element and one or more operations:</span></span>  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="remarks"></a><span data-ttu-id="b6d68-113">备注</span><span class="sxs-lookup"><span data-stu-id="b6d68-113">Remarks</span></span>  
 <span data-ttu-id="b6d68-114">ContinuationToken 表达式中不允许以下常见运算：</span><span class="sxs-lookup"><span data-stu-id="b6d68-114">The following common operations are not allowed in ContinuationToken expressions:</span></span>  
  
- <span data-ttu-id="b6d68-115">And</span><span class="sxs-lookup"><span data-stu-id="b6d68-115">And</span></span>  
  
- <span data-ttu-id="b6d68-116">等于</span><span class="sxs-lookup"><span data-stu-id="b6d68-116">Equals</span></span>  
  
  <span data-ttu-id="b6d68-117">[WF/WCF 中的运算部分标头应具有相似的图表和其他图表根据]</span><span class="sxs-lookup"><span data-stu-id="b6d68-117">[Operations section header in WF/WCF should have similar chart and other charts as needed]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6d68-118">示例</span><span class="sxs-lookup"><span data-stu-id="b6d68-118">Example</span></span>  
 <span data-ttu-id="b6d68-119">在此示例中，WF 流程的继续标记检索从工作流使用`GetWorkflowProperty`。</span><span class="sxs-lookup"><span data-stu-id="b6d68-119">In this example, a continuation token for a WF process is retrieved from the workflow by using `GetWorkflowProperty`.</span></span> <span data-ttu-id="b6d68-120">此处，开发人员决定通过使用自定义代码，可能因为确定继续标记的过程只是涉及到两个或三个表达式，并可能依赖外部数据的工作流中的连续符提供支持。</span><span class="sxs-lookup"><span data-stu-id="b6d68-120">Here the developer decided to provide support for continuation in the workflow by using custom code, probably because the process for determining the continuation token involves more than two or three expressions and may rely on external data.</span></span>  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>ContinuationToken</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
 <span data-ttu-id="b6d68-121">您可以选择提供新 WF 或 WCF 应用程序中类似的功能，或者，如果令牌十分容易使用表达式运算创建的则可以避免编写额外代码。</span><span class="sxs-lookup"><span data-stu-id="b6d68-121">You may choose to provide similar functionality in your new WF or WCF applications or, if the token is easy to establish using expression operations, you can avoid writing additional code.</span></span>  
  
 <span data-ttu-id="b6d68-122">下面的示例通过使用建立为 WCF 流程的继续标记**XPath**操作从当前消息中检索信用卡卡号和**常量**和**串联**操作前面加上"CID_"字符串检索到的号码：</span><span class="sxs-lookup"><span data-stu-id="b6d68-122">The following example establishes a continuation token for a WCF process by using an **XPath** operation to retrieve the credit card number from the current message and the **constant** and **concatenate** operations to prepend the string "CID_" to the retrieved number:</span></span>  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CID_</ic:Argument>  
    </ic:Operation>  
    <wcf:Operation Name="XPath">  
      <wcf:Argument>//Purchase/Payment/CreditCardNumber</wcf:Argument>  
    </wcf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6d68-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6d68-123">See Also</span></span>  
 [<span data-ttu-id="b6d68-124">侦听器 OnEvent 元素</span><span class="sxs-lookup"><span data-stu-id="b6d68-124">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)