---
title: 如何添加 Namespace 示例工作原理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c76a90a9-5898-43b3-98af-ff546dd97153
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33fc168ff5461ffc4145e83efaf2192cbc785820
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975062"
---
# <a name="how-the-add-namespace-sample-works"></a><span data-ttu-id="385d8-102">如何添加 Namespace 示例能够正常工作</span><span class="sxs-lookup"><span data-stu-id="385d8-102">How the Add Namespace Sample Works</span></span>
<span data-ttu-id="385d8-103">第一，第二和第四个测试使用**添加 Namespace**组件位于 NamespaceSampleReceivePipeline 管道中。</span><span class="sxs-lookup"><span data-stu-id="385d8-103">The first, second, and fourth tests use the **Add Namespace** component located in the NamespaceSampleReceivePipeline pipeline.</span></span> <span data-ttu-id="385d8-104">它将作为输入具有对根节点，如下所示没有命名空间的文档：</span><span class="sxs-lookup"><span data-stu-id="385d8-104">It takes as input a document with no namespace on the root node, such as the following:</span></span>  

```  
<CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1" Status="Status_2">  
```  

 <span data-ttu-id="385d8-105">下表显示了设置的属性值**添加 Namespace**组件。</span><span class="sxs-lookup"><span data-stu-id="385d8-105">The following table shows the property values set for the **Add Namespace** component.</span></span>  


|      <span data-ttu-id="385d8-106">“属性”</span><span class="sxs-lookup"><span data-stu-id="385d8-106">Property</span></span>       |  <span data-ttu-id="385d8-107">类型</span><span class="sxs-lookup"><span data-stu-id="385d8-107">Type</span></span>   |                          <span data-ttu-id="385d8-108">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="385d8-108">Value</span></span>                           |
|---------------------|---------|----------------------------------------------------------|
| <span data-ttu-id="385d8-109">ExtractionNodeXPath</span><span class="sxs-lookup"><span data-stu-id="385d8-109">ExtractionNodeXPath</span></span> | <span data-ttu-id="385d8-110">静态</span><span class="sxs-lookup"><span data-stu-id="385d8-110">Static</span></span>  |                         <span data-ttu-id="385d8-111">（空）</span><span class="sxs-lookup"><span data-stu-id="385d8-111">(empty)</span></span>                          |
|    <span data-ttu-id="385d8-112">NamespaceBase</span><span class="sxs-lookup"><span data-stu-id="385d8-112">NamespaceBase</span></span>    | <span data-ttu-id="385d8-113">静态</span><span class="sxs-lookup"><span data-stu-id="385d8-113">Static</span></span>  |    http://schemas.microsoft.biztalk.esb.test.com/test    |
|   <span data-ttu-id="385d8-114">NamespacePrefix</span><span class="sxs-lookup"><span data-stu-id="385d8-114">NamespacePrefix</span></span>   | <span data-ttu-id="385d8-115">静态</span><span class="sxs-lookup"><span data-stu-id="385d8-115">Static</span></span>  |                         <span data-ttu-id="385d8-116">esbTest</span><span class="sxs-lookup"><span data-stu-id="385d8-116">esbTest</span></span>                          |
|      <span data-ttu-id="385d8-117">分隔符</span><span class="sxs-lookup"><span data-stu-id="385d8-117">Separator</span></span>      | <span data-ttu-id="385d8-118">静态</span><span class="sxs-lookup"><span data-stu-id="385d8-118">Static</span></span>  |                            /                             |
|       <span data-ttu-id="385d8-119">Xpath</span><span class="sxs-lookup"><span data-stu-id="385d8-119">XPaths</span></span>        | <span data-ttu-id="385d8-120">Dynamic</span><span class="sxs-lookup"><span data-stu-id="385d8-120">Dynamic</span></span> | <span data-ttu-id="385d8-121">/CanonicalOrder/@OrderID&#124;/CanonicalOrder/@OrderDate</span><span class="sxs-lookup"><span data-stu-id="385d8-121">/CanonicalOrder/@OrderID&#124;/CanonicalOrder/@OrderDate</span></span> |

 <span data-ttu-id="385d8-122">表中显示的属性设置会导致要通过执行两个 XPath 查询来搜索 XML 文档的组件/CanonicalOrder/@OrderID并/CanonicalOrder/@OrderDate(为指定的两个查询**Xpath**分隔"管道"属性字符）。</span><span class="sxs-lookup"><span data-stu-id="385d8-122">The property settings shown in the table cause the component to search the XML document by executing the two XPath queries /CanonicalOrder/@OrderID and /CanonicalOrder/@OrderDate (the two queries specified for the **XPaths** property, separated by a "pipe" character).</span></span> <span data-ttu-id="385d8-123">这些查询返回的值**OrderID**并**OrderDate**属性的根节点的文档; 在此示例中，两个值是"OrderID_0"和"OrderDate_1"。</span><span class="sxs-lookup"><span data-stu-id="385d8-123">These queries return the values of the **OrderID** and **OrderDate** attributes of the root node of the document; in this example, the two values are "OrderID_0" and "OrderDate_1".</span></span>  

 <span data-ttu-id="385d8-124">该组件然后使用这些值和其他属性的值来构造新的根命名空间。</span><span class="sxs-lookup"><span data-stu-id="385d8-124">The component then uses these values, and the values of the other properties, to construct the new root namespace.</span></span> <span data-ttu-id="385d8-125">它将结合**NamespaceBase**，则**NamespacePrefix**，则**分隔符**，以及采用以下格式的两个 XPath 查询中的值：</span><span class="sxs-lookup"><span data-stu-id="385d8-125">It combines the **NamespaceBase**, the **NamespacePrefix**, the **Separator**, and the values from the two XPath queries in the following format:</span></span>  

```  
xmlns:{NamespacePrefix}="{NamespaceBase}{Separator}{XPaths[1]}{Seperator}  
                         {XPaths[2]}{Separator}...{XPaths[n]}"  
```  

 <span data-ttu-id="385d8-126">这会生成新的命名空间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="385d8-126">This produces the new namespace, as shown here:</span></span>  

```  
xmlns:esbTest="http://schemas.microsoft.biztalk.esb.test.com/test  
               /OrderID_0/OrderDate_1"  
```  

 <span data-ttu-id="385d8-127">因此，更新后的文档的处理后**NamespaceSampleReceivePipeline**管道是以下：</span><span class="sxs-lookup"><span data-stu-id="385d8-127">Therefore, the updated document after processing by the **NamespaceSampleReceivePipeline** pipeline is the following:</span></span>  

```  
<esbTest:CanonicalOrder xmlns:esbTest=  
    "http://schemas.microsoft.biztalk.esb.test.com/test/OrderID_0  
    /OrderDate_1" OrderID="OrderID_0" OrderDate="OrderDate_1"   
    Status="Status_2">  
```  

## <a name="using-the-extractionnodexpath-property"></a><span data-ttu-id="385d8-128">使用 ExtractionNodeXPath 属性</span><span class="sxs-lookup"><span data-stu-id="385d8-128">Using the ExtractionNodeXPath Property</span></span>  
 <span data-ttu-id="385d8-129">默认情况下**添加 Namespace**组件添加命名空间和前缀信息时使用的消息中的 XML 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="385d8-129">By default, the **Add Namespace** component uses the root element of the XML document within the message when adding namespace and prefix information.</span></span> <span data-ttu-id="385d8-130">如果你想要使用的 XML 文档的一个子集作为消息正文 （在某些方案中信封或仅为一部分的入站文档具有相关性的情况下很有用），则可以设置**ExtractionNodeXPath**属性强制**添加 Namespace**组件以查找用于生成消息的指定的元素。</span><span class="sxs-lookup"><span data-stu-id="385d8-130">If you want to use only a subset of the XML document as the message body (useful in certain envelope scenarios or when only a portion of an inbound document has relevance), you can set the **ExtractionNodeXPath** property to force the **Add Namespace** component to seek the specified element for use as the resultant message.</span></span> <span data-ttu-id="385d8-131">例如，如果您知道，收到的 CanonicalOrder 消息将仅包含一个**OrderDetails**适用于它所包含的此消息的使用者的元素，可以设置**ExtractionNodeXPath**属性指定的路径**OrderDetails**元素。</span><span class="sxs-lookup"><span data-stu-id="385d8-131">For example, if you know that a received CanonicalOrder message will have only one **OrderDetails** element that is relevant for consumers of this message contained within it, you can set the **ExtractionNodeXPath** property to specify the path to the **OrderDetails** element.</span></span> <span data-ttu-id="385d8-132">可以看到此过程中添加通过提取到直通测试前面所述的示例。</span><span class="sxs-lookup"><span data-stu-id="385d8-132">You can see an example of this process in the Add Via Extraction to Pass-through test described earlier.</span></span>  

> [!NOTE]
>  <span data-ttu-id="385d8-133">**ExtractionNodeXPath**属性必须返回只有一个元素的 XPath。</span><span class="sxs-lookup"><span data-stu-id="385d8-133">The **ExtractionNodeXPath** property must be an XPath that returns only one element.</span></span> <span data-ttu-id="385d8-134">如果结果不是一个元素或 XPath 查询返回多个元素，该组件会引发异常。</span><span class="sxs-lookup"><span data-stu-id="385d8-134">The component will raise an exception if the result is not an element or if the XPath query returns more than one element.</span></span>