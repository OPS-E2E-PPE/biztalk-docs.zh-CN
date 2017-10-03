---
title: "GetEndpointName |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5a06850-ff6d-4fe4-9834-61d14b117391
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1567f0b4bceb756381c4033f3243ac7a58fda366
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getendpointname"></a><span data-ttu-id="6ea96-102">GetEndpointName</span><span class="sxs-lookup"><span data-stu-id="6ea96-102">GetEndpointName</span></span>
<span data-ttu-id="6ea96-103">将当前侦听终结点的名称推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="6ea96-103">Pushes the name of the current interception endpoint onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea96-104">语法</span><span class="sxs-lookup"><span data-stu-id="6ea96-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="GetEndpointName" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ea96-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6ea96-105">Parameters</span></span>  
 <span data-ttu-id="6ea96-106">无。</span><span class="sxs-lookup"><span data-stu-id="6ea96-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="6ea96-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="6ea96-107">Pushed Value</span></span>  
 <span data-ttu-id="6ea96-108">包含当前侦听终结点名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="6ea96-108">String containing the current interception endpoint name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ea96-109">注释</span><span class="sxs-lookup"><span data-stu-id="6ea96-109">Remarks</span></span>  
 <span data-ttu-id="6ea96-110">请务必注意，对于在 App.config 文件中指定的相同终结点名称，客户端和服务器应用程序将返回不同的名称。</span><span class="sxs-lookup"><span data-stu-id="6ea96-110">It is important to note that the client and server applications will return different names for the same endpoint name specified in the App.config files.</span></span>  
  
 <span data-ttu-id="6ea96-111">对于客户端应用程序，GetEndPointName 操作检索到的终结点名称是后跟下划线和约定名称的绑定名称。</span><span class="sxs-lookup"><span data-stu-id="6ea96-111">For client applications, the endpoint name retrieved by the GetEndPointName operation is the binding name followed by an underscore and the contract name.</span></span>  
  
 <span data-ttu-id="6ea96-112">例如，如果未设置 ServiceEndpoint 上的名称属性，但设置绑定，该名称将设置\<*绑定*> _\<*协定*>。</span><span class="sxs-lookup"><span data-stu-id="6ea96-112">For example, if the Name property on ServiceEndpoint is not set but the binding is set, the name will be set to \<*binding*>_\<*contract*>.</span></span>  
  
 <span data-ttu-id="6ea96-113">如果未设置的名称和绑定，将名称属性设置为\<*协定*>。</span><span class="sxs-lookup"><span data-stu-id="6ea96-113">If the name and binding are not set, the Name property will be set to \<*contract*>.</span></span>  
  
 <span data-ttu-id="6ea96-114">对于服务而言，检索到的名称是在 App.config 文件中指定的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="6ea96-114">For the service, the name retrieved is the endpoint name specified in the App.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ea96-115">示例</span><span class="sxs-lookup"><span data-stu-id="6ea96-115">Example</span></span>  
 <span data-ttu-id="6ea96-116">下面的示例筛选器表达式为 PurchaseOrder_EP 终结点的 ServiceRequest 约定调用点的 Receive 操作定义了侦听。</span><span class="sxs-lookup"><span data-stu-id="6ea96-116">The following example filter expression defines an interception for the Receive operation for the ServiceRequest contract call point for the PurchaseOrder_EP endpoint.</span></span> <span data-ttu-id="6ea96-117">这是通过以下逻辑步骤完成的：</span><span class="sxs-lookup"><span data-stu-id="6ea96-117">This is done in the following logical steps:</span></span>  
  
1.  <span data-ttu-id="6ea96-118">将当前操作名称与“Receive”进行比较，并将结果（True 或 False）推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="6ea96-118">Compare the current operation name to "Receive" and push the result (true or false) onto the stack.</span></span>  
  
2.  <span data-ttu-id="6ea96-119">将当前服务约定调用点与“ServiceRequest”进行比较，并将结果（True 或 False）推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="6ea96-119">Compare the current service contract call point to "ServiceRequest" and push the result (true or false) onto the stack.</span></span> <span data-ttu-id="6ea96-120">现在堆栈上有两个布尔值。</span><span class="sxs-lookup"><span data-stu-id="6ea96-120">There are now two Boolean values on the stack.</span></span>  
  
3.  <span data-ttu-id="6ea96-121">比较两个结果的前面的步骤中使用布尔型**和**操作和堆栈上的推送结果。</span><span class="sxs-lookup"><span data-stu-id="6ea96-121">Compare the results of the preceding steps using a Boolean **And** operation and push the result on the stack.</span></span> <span data-ttu-id="6ea96-122">这样，堆栈上就只剩一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="6ea96-122">This leaves one Boolean value on the stack.</span></span>  
  
4.  <span data-ttu-id="6ea96-123">将当前终结点与“PurchaseOrder_EP”进行比较，并将结果（True 或 False）推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="6ea96-123">Compare the current endpoint to "PurchaseOrder_EP" and push the result (true or false) onto the stack.</span></span> <span data-ttu-id="6ea96-124">现在堆栈上有两个布尔值。</span><span class="sxs-lookup"><span data-stu-id="6ea96-124">There are now two Boolean values on the stack.</span></span>  
  
5.  <span data-ttu-id="6ea96-125">最后，将使用一个布尔值在堆栈上的两个布尔值进行比较**和**操作和推送到堆栈的结果。</span><span class="sxs-lookup"><span data-stu-id="6ea96-125">Finally, compare the two Boolean values on the stack using a Boolean **And** operation and push the result onto the stack.</span></span> <span data-ttu-id="6ea96-126">这会将终结点比较的结果与一个布尔值核对，如果操作名称与约定调用点成功匹配，则此布尔值为 True，否则为 False。</span><span class="sxs-lookup"><span data-stu-id="6ea96-126">This checks the result of the endpoint comparison against a Boolean value, which is true if the operation name and contract call point successfully matched, and which is false otherwise.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wcf:Operation Name="GetOperationName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Receive</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wcf:Operation Name="GetServiceContractCallPoint" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ServiceRequest</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wcf:Operation Name="GetEndpointName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>PurchaseOrder_EP</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ea96-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ea96-127">See Also</span></span>  
 [<span data-ttu-id="6ea96-128">Windows Communication Foundation 中的操作</span><span class="sxs-lookup"><span data-stu-id="6ea96-128">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)