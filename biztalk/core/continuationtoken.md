---
title: "ContinuationToken |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d4911fc-c6fb-4628-9177-bd723d4d8ebc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54cf9b9326661925f2d55bacd2fb22d02f565f89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="continuationtoken"></a><span data-ttu-id="00614-102">ContinuationToken</span><span class="sxs-lookup"><span data-stu-id="00614-102">ContinuationToken</span></span>
<span data-ttu-id="00614-103">继续标记用来关联 BAM 基础结构中各种不同的信息。</span><span class="sxs-lookup"><span data-stu-id="00614-103">A continuation token is used to correlate heterogeneous information within the BAM infrastructure.</span></span> <span data-ttu-id="00614-104">假设有一个业务流程用于构造以下类型的消息：</span><span class="sxs-lookup"><span data-stu-id="00614-104">Consider a business process that constructs the following types of messages:</span></span>  
  
-   <span data-ttu-id="00614-105">由采购订单号标识的采购订单</span><span class="sxs-lookup"><span data-stu-id="00614-105">Purchase order identified by a purchase order number</span></span>  
  
-   <span data-ttu-id="00614-106">由销售订单号标识的销售订单</span><span class="sxs-lookup"><span data-stu-id="00614-106">Sales order identified by a sales order number</span></span>  
  
-   <span data-ttu-id="00614-107">由发货订单号标识的发货订单</span><span class="sxs-lookup"><span data-stu-id="00614-107">Shipping order identified by a shipping order number</span></span>  
  
 <span data-ttu-id="00614-108">在此过程中，有以下三个重要标识符： 采购订单 ID、 销售订单 ID 和传送顺序 id。</span><span class="sxs-lookup"><span data-stu-id="00614-108">In this process, there are three important identifiers: purchase order ID, sales order ID and shipping order ID.</span></span> <span data-ttu-id="00614-109">其中每个标识符都表示原始订单生存期内的一个重要事件，但这些标示符无法直接关联。</span><span class="sxs-lookup"><span data-stu-id="00614-109">Each of these identifiers signals an important event in the lifetime of the original order, but they cannot be directly correlated.</span></span> <span data-ttu-id="00614-110">若要跟踪与采购订单相关的事件，必须标识各消息间共有的信息，这样 BAM 跟踪基础结构才能准确地关联事件。</span><span class="sxs-lookup"><span data-stu-id="00614-110">To track events related to a purchase order, the information that is common between the messages must be identified to help the BAM tracking infrastructure accurately correlate the events.</span></span>  
  
## <a name="format"></a><span data-ttu-id="00614-111">格式</span><span class="sxs-lookup"><span data-stu-id="00614-111">Format</span></span>  
 <span data-ttu-id="00614-112">继续标记由一个表达式元素和一项或多项运算组成：</span><span class="sxs-lookup"><span data-stu-id="00614-112">A continuation token consists of an expression element and one or more operations:</span></span>  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="remarks"></a><span data-ttu-id="00614-113">注释</span><span class="sxs-lookup"><span data-stu-id="00614-113">Remarks</span></span>  
 <span data-ttu-id="00614-114">ContinuationToken 表达式中不允许使用以下常见运算：</span><span class="sxs-lookup"><span data-stu-id="00614-114">The following common operations are not allowed in ContinuationToken expressions:</span></span>  
  
-   <span data-ttu-id="00614-115">And</span><span class="sxs-lookup"><span data-stu-id="00614-115">And</span></span>  
  
-   <span data-ttu-id="00614-116">等于</span><span class="sxs-lookup"><span data-stu-id="00614-116">Equals</span></span>  
  
 <span data-ttu-id="00614-117">[WF/WCF 中的运算部分标头应具有相似的图表及其他图表，具体视需要而定]</span><span class="sxs-lookup"><span data-stu-id="00614-117">[Operations section header in WF/WCF should have similar chart and other charts as needed]</span></span>  
  
## <a name="example"></a><span data-ttu-id="00614-118">示例</span><span class="sxs-lookup"><span data-stu-id="00614-118">Example</span></span>  
 <span data-ttu-id="00614-119">在此示例中，WF 进程的继续标记将从工作流中检索使用`GetWorkflowProperty`。</span><span class="sxs-lookup"><span data-stu-id="00614-119">In this example, a continuation token for a WF process is retrieved from the workflow by using `GetWorkflowProperty`.</span></span> <span data-ttu-id="00614-120">在此开发人员之所以决定通过使用自定义代码为工作流中的连续符提供支持，可能是因为确定继续标记的流程涉及两个或三个以上的表达式并且可能依赖外部数据。</span><span class="sxs-lookup"><span data-stu-id="00614-120">Here the developer decided to provide support for continuation in the workflow by using custom code, probably because the process for determining the continuation token involves more than two or three expressions and may rely on external data.</span></span>  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>ContinuationToken</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
 <span data-ttu-id="00614-121">您可以选择在您的新 WF 或 WCF 应用程序中提供类似功能，或者，如果使用表达式运算创建标记非常简便，则无需编写额外的代码。</span><span class="sxs-lookup"><span data-stu-id="00614-121">You may choose to provide similar functionality in your new WF or WCF applications or, if the token is easy to establish using expression operations, you can avoid writing additional code.</span></span>  
  
 <span data-ttu-id="00614-122">下面的示例通过使用建立 WCF 进程的继续标记**XPath**操作以检索从当前消息的信用卡号和**常量**和**串联**前面预置的检索到的数字的字符串"CID_"的操作：</span><span class="sxs-lookup"><span data-stu-id="00614-122">The following example establishes a continuation token for a WCF process by using an **XPath** operation to retrieve the credit card number from the current message and the **constant** and **concatenate** operations to prepend the string "CID_" to the retrieved number:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="00614-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00614-123">See Also</span></span>  
 [<span data-ttu-id="00614-124">拦截器 OnEvent 元素</span><span class="sxs-lookup"><span data-stu-id="00614-124">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)