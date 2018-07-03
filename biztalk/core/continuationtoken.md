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
ms.openlocfilehash: 1f0d36737ddd16e34ecfe4680c7660e16c99f676
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001862"
---
# <a name="continuationtoken"></a><span data-ttu-id="a105e-102">ContinuationToken</span><span class="sxs-lookup"><span data-stu-id="a105e-102">ContinuationToken</span></span>
<span data-ttu-id="a105e-103">继续标记用来关联 BAM 基础结构中各种不同的信息。</span><span class="sxs-lookup"><span data-stu-id="a105e-103">A continuation token is used to correlate heterogeneous information within the BAM infrastructure.</span></span> <span data-ttu-id="a105e-104">假设有一个业务流程用于构造以下类型的消息：</span><span class="sxs-lookup"><span data-stu-id="a105e-104">Consider a business process that constructs the following types of messages:</span></span>  
  
- <span data-ttu-id="a105e-105">由采购订单号标识的采购订单</span><span class="sxs-lookup"><span data-stu-id="a105e-105">Purchase order identified by a purchase order number</span></span>  
  
- <span data-ttu-id="a105e-106">由销售订单号标识的销售订单</span><span class="sxs-lookup"><span data-stu-id="a105e-106">Sales order identified by a sales order number</span></span>  
  
- <span data-ttu-id="a105e-107">由发货订单号标识的发货订单</span><span class="sxs-lookup"><span data-stu-id="a105e-107">Shipping order identified by a shipping order number</span></span>  
  
  <span data-ttu-id="a105e-108">在此过程中，有三个重要的标识符： 采购订单 ID、 销售订单 ID 和发货订单 id。</span><span class="sxs-lookup"><span data-stu-id="a105e-108">In this process, there are three important identifiers: purchase order ID, sales order ID and shipping order ID.</span></span> <span data-ttu-id="a105e-109">其中每个标识符都表示原始订单生存期内的一个重要事件，但这些标示符无法直接关联。</span><span class="sxs-lookup"><span data-stu-id="a105e-109">Each of these identifiers signals an important event in the lifetime of the original order, but they cannot be directly correlated.</span></span> <span data-ttu-id="a105e-110">若要跟踪与采购订单相关的事件，必须标识各消息间共有的信息，这样 BAM 跟踪基础结构才能准确地关联事件。</span><span class="sxs-lookup"><span data-stu-id="a105e-110">To track events related to a purchase order, the information that is common between the messages must be identified to help the BAM tracking infrastructure accurately correlate the events.</span></span>  
  
## <a name="format"></a><span data-ttu-id="a105e-111">“格式”</span><span class="sxs-lookup"><span data-stu-id="a105e-111">Format</span></span>  
 <span data-ttu-id="a105e-112">继续标记由一个表达式元素和一项或多项运算组成：</span><span class="sxs-lookup"><span data-stu-id="a105e-112">A continuation token consists of an expression element and one or more operations:</span></span>  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="remarks"></a><span data-ttu-id="a105e-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="a105e-113">Remarks</span></span>  
 <span data-ttu-id="a105e-114">ContinuationToken 表达式中不允许使用以下常见运算：</span><span class="sxs-lookup"><span data-stu-id="a105e-114">The following common operations are not allowed in ContinuationToken expressions:</span></span>  
  
- <span data-ttu-id="a105e-115">And</span><span class="sxs-lookup"><span data-stu-id="a105e-115">And</span></span>  
  
- <span data-ttu-id="a105e-116">等于</span><span class="sxs-lookup"><span data-stu-id="a105e-116">Equals</span></span>  
  
  <span data-ttu-id="a105e-117">[WF/WCF 中的运算部分标头应具有相似的图表及其他图表，具体视需要而定]</span><span class="sxs-lookup"><span data-stu-id="a105e-117">[Operations section header in WF/WCF should have similar chart and other charts as needed]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a105e-118">示例</span><span class="sxs-lookup"><span data-stu-id="a105e-118">Example</span></span>  
 <span data-ttu-id="a105e-119">在此示例中，WF 流程的继续标记检索从工作流使用`GetWorkflowProperty`。</span><span class="sxs-lookup"><span data-stu-id="a105e-119">In this example, a continuation token for a WF process is retrieved from the workflow by using `GetWorkflowProperty`.</span></span> <span data-ttu-id="a105e-120">在此开发人员之所以决定通过使用自定义代码为工作流中的连续符提供支持，可能是因为确定继续标记的流程涉及两个或三个以上的表达式并且可能依赖外部数据。</span><span class="sxs-lookup"><span data-stu-id="a105e-120">Here the developer decided to provide support for continuation in the workflow by using custom code, probably because the process for determining the continuation token involves more than two or three expressions and may rely on external data.</span></span>  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>ContinuationToken</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
 <span data-ttu-id="a105e-121">您可以选择在您的新 WF 或 WCF 应用程序中提供类似功能，或者，如果使用表达式运算创建标记非常简便，则无需编写额外的代码。</span><span class="sxs-lookup"><span data-stu-id="a105e-121">You may choose to provide similar functionality in your new WF or WCF applications or, if the token is easy to establish using expression operations, you can avoid writing additional code.</span></span>  
  
 <span data-ttu-id="a105e-122">下面的示例通过使用建立为 WCF 流程的继续标记**XPath**操作从当前消息中检索信用卡卡号和**常量**和**串联**操作前面加上"CID_"字符串检索到的号码：</span><span class="sxs-lookup"><span data-stu-id="a105e-122">The following example establishes a continuation token for a WCF process by using an **XPath** operation to retrieve the credit card number from the current message and the **constant** and **concatenate** operations to prepend the string "CID_" to the retrieved number:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a105e-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="a105e-123">See Also</span></span>  
 [<span data-ttu-id="a105e-124">侦听器 OnEvent 元素</span><span class="sxs-lookup"><span data-stu-id="a105e-124">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)