---
title: "引用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b916c55a-c84c-4008-8927-f8e584c36fe9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3e32145e2340a4d86a6893db3e9209b79c2b5e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="reference"></a><span data-ttu-id="97e96-102">参考</span><span class="sxs-lookup"><span data-stu-id="97e96-102">Reference</span></span>
<span data-ttu-id="97e96-103">**引用**元素可以用来向 BAM 活动中添加一个或多个关系。</span><span class="sxs-lookup"><span data-stu-id="97e96-103">The **Reference** element can be used to add one or more relationships to a BAM activity.</span></span> <span data-ttu-id="97e96-104">当要将诸如主键、ID 或 URL 之类的指针附加到相关消息时，这特别有用。</span><span class="sxs-lookup"><span data-stu-id="97e96-104">This is useful when you want to attach a pointer like a primary key, ID, or URL to a related message.</span></span> <span data-ttu-id="97e96-105">例如，可能要在“采购订单”活动中存储指向“发货批”的引用。</span><span class="sxs-lookup"><span data-stu-id="97e96-105">For example, you might store a reference to a Shipment Batch in a Purchase Order activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="97e96-106">格式</span><span class="sxs-lookup"><span data-stu-id="97e96-106">Format</span></span>  
 <span data-ttu-id="97e96-107">`Reference`元素同时支持**数据**和**LongData**包含一个表达式来指定要将附加到 BAM 活动的数据的子元素。</span><span class="sxs-lookup"><span data-stu-id="97e96-107">The `Reference` element supports both the **Data** and **LongData** child elements that contain an expression specifying the data to attach to the BAM activity.</span></span> <span data-ttu-id="97e96-108">你可以使用的任意组合**数据**和**LongData**以满足你的跟踪要求。</span><span class="sxs-lookup"><span data-stu-id="97e96-108">You can use any combination of **Data** and **LongData** to meet your tracking requirements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97e96-109">属性</span><span class="sxs-lookup"><span data-stu-id="97e96-109">Attributes</span></span>  
  
|<span data-ttu-id="97e96-110">属性名称</span><span class="sxs-lookup"><span data-stu-id="97e96-110">Attribute name</span></span>|<span data-ttu-id="97e96-111">Description</span><span class="sxs-lookup"><span data-stu-id="97e96-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="97e96-112">Name</span><span class="sxs-lookup"><span data-stu-id="97e96-112">Name</span></span>|<span data-ttu-id="97e96-113">将附加到 BAM 活动的关系的名称。</span><span class="sxs-lookup"><span data-stu-id="97e96-113">Name of the relationship that will be attached to the BAM activity.</span></span>|  
|<span data-ttu-id="97e96-114">类型</span><span class="sxs-lookup"><span data-stu-id="97e96-114">Type</span></span>|<span data-ttu-id="97e96-115">任意字符串，用于指定将附加到 BAM 活动的关系的类型。</span><span class="sxs-lookup"><span data-stu-id="97e96-115">Arbitrary string specifying the type of relationship that will be attached to the BAM activity.</span></span> <span data-ttu-id="97e96-116">任意字符串和以下预定义 BAM 类型均受支持：</span><span class="sxs-lookup"><span data-stu-id="97e96-116">Both arbitrary strings and the following predefined BAM types are supported:</span></span><br /><br /> <span data-ttu-id="97e96-117">-BizTalkService</span><span class="sxs-lookup"><span data-stu-id="97e96-117">-   BizTalkService</span></span><br /><span data-ttu-id="97e96-118">-MessageID</span><span class="sxs-lookup"><span data-stu-id="97e96-118">-   MessageID</span></span><br /><span data-ttu-id="97e96-119">-活动</span><span class="sxs-lookup"><span data-stu-id="97e96-119">-   Activity</span></span><br /><span data-ttu-id="97e96-120">-DocumentUrl</span><span class="sxs-lookup"><span data-stu-id="97e96-120">-   DocumentUrl</span></span><br /><span data-ttu-id="97e96-121">-InstanceID</span><span class="sxs-lookup"><span data-stu-id="97e96-121">-   InstanceID</span></span><br /><br /> <span data-ttu-id="97e96-122">有关预定义 BAM 引用类型的详细信息，请参阅[引用属性](http://go.microsoft.com/fwlink/?LinkId=119601)。</span><span class="sxs-lookup"><span data-stu-id="97e96-122">For more information on predefined BAM reference types, see [Reference Properties](http://go.microsoft.com/fwlink/?LinkId=119601).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97e96-123">子元素</span><span class="sxs-lookup"><span data-stu-id="97e96-123">Child Elements</span></span>  
  
|<span data-ttu-id="97e96-124">执行状态</span><span class="sxs-lookup"><span data-stu-id="97e96-124">Execution status</span></span>|<span data-ttu-id="97e96-125">Description</span><span class="sxs-lookup"><span data-stu-id="97e96-125">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="97e96-126">data</span><span class="sxs-lookup"><span data-stu-id="97e96-126">Data</span></span>|<span data-ttu-id="97e96-127">指定如何提取将附加到 BAM 活动的最多为 128 个字符的字符串数据。</span><span class="sxs-lookup"><span data-stu-id="97e96-127">Specifies how to extract string data up to 128 characters that will be attached to the BAM activity.</span></span>|  
|<span data-ttu-id="97e96-128">LongData</span><span class="sxs-lookup"><span data-stu-id="97e96-128">LongData</span></span>|<span data-ttu-id="97e96-129">指定如何提取将附加到 BAM 活动的任意长度的字符串数据。</span><span class="sxs-lookup"><span data-stu-id="97e96-129">Specifies how to extract arbitrarily long string data that will be attached to the BAM activity.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="97e96-130">A`Reference`元素可以合并一个或多**数据**和**LongData**根据需要的子元素。</span><span class="sxs-lookup"><span data-stu-id="97e96-130">A `Reference` element can combine one or more **Data** and **LongData** child elements as needed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97e96-131">注释</span><span class="sxs-lookup"><span data-stu-id="97e96-131">Remarks</span></span>  
 <span data-ttu-id="97e96-132">Reference 表达式中不允许使用以下常见运算：</span><span class="sxs-lookup"><span data-stu-id="97e96-132">The following common operations are not allowed in Reference expressions:</span></span>  
  
-   <span data-ttu-id="97e96-133">And</span><span class="sxs-lookup"><span data-stu-id="97e96-133">And</span></span>  
  
-   <span data-ttu-id="97e96-134">等于</span><span class="sxs-lookup"><span data-stu-id="97e96-134">Equals</span></span>  
  
## <a name="example"></a><span data-ttu-id="97e96-135">示例</span><span class="sxs-lookup"><span data-stu-id="97e96-135">Example</span></span>  
 <span data-ttu-id="97e96-136">在下面的示例中，使用 `GetUserData` 为工作流创建了一个类型为“DocumentUrl”、名为“Related Document”的引用。</span><span class="sxs-lookup"><span data-stu-id="97e96-136">In the following sample, a reference named "Related Document" of type "DocumentUrl" is created using `GetUserData` for a workflow.</span></span> <span data-ttu-id="97e96-137">需要用户数据必须少于 1024年个字符的长度，因为`Data`元素用来包含`Expression`元素。</span><span class="sxs-lookup"><span data-stu-id="97e96-137">Because the user data is expected to be fewer than 1024 characters in length, the `Data` element is used to contain the `Expression` element.</span></span>  
  
```  
<ic:Reference Name="Related Document" Type="DocumentUrl">  
  <ic:Data>  
    <ic:Expression>  
      <wf:Operation Name="GetUserData" />  
    </ic:Expression>  
  </ic:Data>  
</ic:Reference>  
```  
  
 <span data-ttu-id="97e96-138">**引用**元素支持多种`Data`和`LongData`元素。</span><span class="sxs-lookup"><span data-stu-id="97e96-138">The **Reference** element supports a mix of `Data` and `LongData` elements.</span></span> <span data-ttu-id="97e96-139">在下面的示例中，从 WCF 服务检索采购订单中的国家/地区名称和备注字段，并将它们写入“MyType”类型的关系“Long and Short Data”中。</span><span class="sxs-lookup"><span data-stu-id="97e96-139">In the following sample, the country name and note fields from a purchase order are retrieved from a WCF service and written to the relationship "Long and Short Data" as type "MyType".</span></span> <span data-ttu-id="97e96-140">由于注释字段支持超过 1024年个字符，因此表达式括在`LongData`元素。</span><span class="sxs-lookup"><span data-stu-id="97e96-140">Because the note field supports more than 1024 characters, the expression is enclosed in a `LongData` element.</span></span>  
  
```  
<ic:Reference Name="Long and Short Data" Type="MyType">  
  <ic:Data>  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Country: </ic:Argument>  
      </ic:Operation>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body//po:Country</wcf:Argument>  
      </wcf:Operation>  
       <ic:Operation Name="Concatenate" />  
    </ic:Expression>  
  </ic:Data>  
  <ic:LongData>  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Note: </ic:Argument>  
      </ic:Operation>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body//po:Note</wcf:Argument>  
      </wcf:Operation>  
      <ic:Operation Name="Concatenate" />  
    </ic:Expression>  
  </ic:LongData>  
</ic:Reference>  
```  
  
## <a name="see-also"></a><span data-ttu-id="97e96-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97e96-141">See Also</span></span>  
 <span data-ttu-id="97e96-142">[拦截器 OnEvent 元素](../core/interceptor-onevent-element.md) </span><span class="sxs-lookup"><span data-stu-id="97e96-142">[Interceptor OnEvent Element](../core/interceptor-onevent-element.md) </span></span>  
 [<span data-ttu-id="97e96-143">EventStream.AddRelatedActivity 方法</span><span class="sxs-lookup"><span data-stu-id="97e96-143">EventStream.AddRelatedActivity Method</span></span>](http://go.microsoft.com/fwlink/?LinkId=119602)