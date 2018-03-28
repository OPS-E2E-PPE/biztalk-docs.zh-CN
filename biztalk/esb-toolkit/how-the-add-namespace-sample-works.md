---
title: 如何添加 Namespace 示例适用 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c76a90a9-5898-43b3-98af-ff546dd97153
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 212364030353001cae0589d4d7562641db4b77e6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-the-add-namespace-sample-works"></a><span data-ttu-id="e674b-102">如何添加 Namespace 示例的工作机制</span><span class="sxs-lookup"><span data-stu-id="e674b-102">How the Add Namespace Sample Works</span></span>
<span data-ttu-id="e674b-103">第一，第二和第四个测试使用**添加 Namespace**组件位于 NamespaceSampleReceivePipeline 管道。</span><span class="sxs-lookup"><span data-stu-id="e674b-103">The first, second, and fourth tests use the **Add Namespace** component located in the NamespaceSampleReceivePipeline pipeline.</span></span> <span data-ttu-id="e674b-104">它将作为输入具有根节点，如下所示上没有命名空间的文档：</span><span class="sxs-lookup"><span data-stu-id="e674b-104">It takes as input a document with no namespace on the root node, such as the following:</span></span>  
  
```  
<CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1" Status="Status_2">  
```  
  
 <span data-ttu-id="e674b-105">下表显示设置的属性值**添加 Namespace**组件。</span><span class="sxs-lookup"><span data-stu-id="e674b-105">The following table shows the property values set for the **Add Namespace** component.</span></span>  
  
|<span data-ttu-id="e674b-106">属性</span><span class="sxs-lookup"><span data-stu-id="e674b-106">Property</span></span>|<span data-ttu-id="e674b-107">类型</span><span class="sxs-lookup"><span data-stu-id="e674b-107">Type</span></span>|<span data-ttu-id="e674b-108">“值”</span><span class="sxs-lookup"><span data-stu-id="e674b-108">Value</span></span>|  
|--------------|----------|-----------|  
|<span data-ttu-id="e674b-109">ExtractionNodeXPath</span><span class="sxs-lookup"><span data-stu-id="e674b-109">ExtractionNodeXPath</span></span>|<span data-ttu-id="e674b-110">静态</span><span class="sxs-lookup"><span data-stu-id="e674b-110">Static</span></span>|<span data-ttu-id="e674b-111">（空）</span><span class="sxs-lookup"><span data-stu-id="e674b-111">(empty)</span></span>|  
|<span data-ttu-id="e674b-112">NamespaceBase</span><span class="sxs-lookup"><span data-stu-id="e674b-112">NamespaceBase</span></span>|<span data-ttu-id="e674b-113">静态</span><span class="sxs-lookup"><span data-stu-id="e674b-113">Static</span></span>|http://schemas.microsoft.biztalk.esb.test.com/test|  
|<span data-ttu-id="e674b-114">NamespacePrefix</span><span class="sxs-lookup"><span data-stu-id="e674b-114">NamespacePrefix</span></span>|<span data-ttu-id="e674b-115">静态</span><span class="sxs-lookup"><span data-stu-id="e674b-115">Static</span></span>|<span data-ttu-id="e674b-116">esbTest</span><span class="sxs-lookup"><span data-stu-id="e674b-116">esbTest</span></span>|  
|<span data-ttu-id="e674b-117">分隔符</span><span class="sxs-lookup"><span data-stu-id="e674b-117">Separator</span></span>|<span data-ttu-id="e674b-118">静态</span><span class="sxs-lookup"><span data-stu-id="e674b-118">Static</span></span>|/|  
|<span data-ttu-id="e674b-119">Xpath</span><span class="sxs-lookup"><span data-stu-id="e674b-119">XPaths</span></span>|<span data-ttu-id="e674b-120">Dynamic</span><span class="sxs-lookup"><span data-stu-id="e674b-120">Dynamic</span></span>|<span data-ttu-id="e674b-121">/CanonicalOrder/@OrderID&#124;/CanonicalOrder/@OrderDate</span><span class="sxs-lookup"><span data-stu-id="e674b-121">/CanonicalOrder/@OrderID&#124;/CanonicalOrder/@OrderDate</span></span>|  
  
 <span data-ttu-id="e674b-122">表所示的属性设置会导致将要通过执行两个 XPath 查询搜索 XML 文档的组件/CanonicalOrder/@OrderID和/CanonicalOrder/@OrderDate(为指定的两个查询**Xpath**属性，"管道"分隔字符）。</span><span class="sxs-lookup"><span data-stu-id="e674b-122">The property settings shown in the table cause the component to search the XML document by executing the two XPath queries /CanonicalOrder/@OrderID and /CanonicalOrder/@OrderDate (the two queries specified for the **XPaths** property, separated by a "pipe" character).</span></span> <span data-ttu-id="e674b-123">这些查询返回的值**OrderID**和**OrderDate**属性的根节点的文档; 在此示例中，两个值是"OrderID_0"和"OrderDate_1"。</span><span class="sxs-lookup"><span data-stu-id="e674b-123">These queries return the values of the **OrderID** and **OrderDate** attributes of the root node of the document; in this example, the two values are "OrderID_0" and "OrderDate_1".</span></span>  
  
 <span data-ttu-id="e674b-124">组件然后使用这些值和其他属性时，值构造的新的根命名空间。</span><span class="sxs-lookup"><span data-stu-id="e674b-124">The component then uses these values, and the values of the other properties, to construct the new root namespace.</span></span> <span data-ttu-id="e674b-125">它整合了**NamespaceBase**、 **NamespacePrefix**、**分隔符**，以及采用以下格式的两个 XPath 查询中的值：</span><span class="sxs-lookup"><span data-stu-id="e674b-125">It combines the **NamespaceBase**, the **NamespacePrefix**, the **Separator**, and the values from the two XPath queries in the following format:</span></span>  
  
```  
xmlns:{NamespacePrefix}="{NamespaceBase}{Separator}{XPaths[1]}{Seperator}  
                         {XPaths[2]}{Separator}...{XPaths[n]}"  
```  
  
 <span data-ttu-id="e674b-126">这将产生新的命名空间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e674b-126">This produces the new namespace, as shown here:</span></span>  
  
```  
xmlns:esbTest="http://schemas.microsoft.biztalk.esb.test.com/test  
               /OrderID_0/OrderDate_1"  
```  
  
 <span data-ttu-id="e674b-127">因此，在通过处理后的更新的文档**NamespaceSampleReceivePipeline**管道是在以下：</span><span class="sxs-lookup"><span data-stu-id="e674b-127">Therefore, the updated document after processing by the **NamespaceSampleReceivePipeline** pipeline is the following:</span></span>  
  
```  
<esbTest:CanonicalOrder xmlns:esbTest=  
    "http://schemas.microsoft.biztalk.esb.test.com/test/OrderID_0  
    /OrderDate_1" OrderID="OrderID_0" OrderDate="OrderDate_1"   
    Status="Status_2">  
```  
  
## <a name="using-the-extractionnodexpath-property"></a><span data-ttu-id="e674b-128">使用 ExtractionNodeXPath 属性</span><span class="sxs-lookup"><span data-stu-id="e674b-128">Using the ExtractionNodeXPath Property</span></span>  
 <span data-ttu-id="e674b-129">默认情况下，**添加 Namespace**组件添加命名空间和前缀信息时使用的消息中的 XML 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="e674b-129">By default, the **Add Namespace** component uses the root element of the XML document within the message when adding namespace and prefix information.</span></span> <span data-ttu-id="e674b-130">如果你想要使用 XML 文档的一个子集作为消息正文 （在某些信封方案中，或仅为一部分的入站文档具有相关性的情况下很有用），则可以设置**ExtractionNodeXPath**属性以强制**添加 Namespace**组件要查找用于生成消息的指定的元素。</span><span class="sxs-lookup"><span data-stu-id="e674b-130">If you want to use only a subset of the XML document as the message body (useful in certain envelope scenarios or when only a portion of an inbound document has relevance), you can set the **ExtractionNodeXPath** property to force the **Add Namespace** component to seek the specified element for use as the resultant message.</span></span> <span data-ttu-id="e674b-131">例如，如果你知道收到的 CanonicalOrder 消息将具有只有一个**OrderDetails**适用于其中包含此消息的使用者的元素，可以设置**ExtractionNodeXPath**属性指定的路径**OrderDetails**元素。</span><span class="sxs-lookup"><span data-stu-id="e674b-131">For example, if you know that a received CanonicalOrder message will have only one **OrderDetails** element that is relevant for consumers of this message contained within it, you can set the **ExtractionNodeXPath** property to specify the path to the **OrderDetails** element.</span></span> <span data-ttu-id="e674b-132">你可以看到举例说明中添加通过提取到前面所述的传递测试此过程。</span><span class="sxs-lookup"><span data-stu-id="e674b-132">You can see an example of this process in the Add Via Extraction to Pass-through test described earlier.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e674b-133">**ExtractionNodeXPath**属性必须返回仅有一个元素的 XPath。</span><span class="sxs-lookup"><span data-stu-id="e674b-133">The **ExtractionNodeXPath** property must be an XPath that returns only one element.</span></span> <span data-ttu-id="e674b-134">如果结果不是元素或 XPath 查询返回多个元素，该组件将引发的异常。</span><span class="sxs-lookup"><span data-stu-id="e674b-134">The component will raise an exception if the result is not an element or if the XPath query returns more than one element.</span></span>