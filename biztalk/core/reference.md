---
title: 引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b916c55a-c84c-4008-8927-f8e584c36fe9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 820e4f77da27a1dd934c1a1b842615c9b60158ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398015"
---
# <a name="reference"></a><span data-ttu-id="250d7-102">参考</span><span class="sxs-lookup"><span data-stu-id="250d7-102">Reference</span></span>
<span data-ttu-id="250d7-103">**引用**元素可用于将一个或多个关系添加到 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="250d7-103">The **Reference** element can be used to add one or more relationships to a BAM activity.</span></span> <span data-ttu-id="250d7-104">当你想要将一个指针，如主键、 ID 或 URL 附加到相关的消息时，这很有用。</span><span class="sxs-lookup"><span data-stu-id="250d7-104">This is useful when you want to attach a pointer like a primary key, ID, or URL to a related message.</span></span> <span data-ttu-id="250d7-105">例如，你可能会采购订单活动中存储对发货批的引用。</span><span class="sxs-lookup"><span data-stu-id="250d7-105">For example, you might store a reference to a Shipment Batch in a Purchase Order activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="250d7-106">格式</span><span class="sxs-lookup"><span data-stu-id="250d7-106">Format</span></span>  
 <span data-ttu-id="250d7-107">`Reference`元素支持两者**数据**并**LongData**子元素包含一个表达式，指定要将附加到 BAM 活动的数据。</span><span class="sxs-lookup"><span data-stu-id="250d7-107">The `Reference` element supports both the **Data** and **LongData** child elements that contain an expression specifying the data to attach to the BAM activity.</span></span> <span data-ttu-id="250d7-108">可以使用的任意组合**数据**并**LongData**以满足您的跟踪要求。</span><span class="sxs-lookup"><span data-stu-id="250d7-108">You can use any combination of **Data** and **LongData** to meet your tracking requirements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="250d7-109">特性</span><span class="sxs-lookup"><span data-stu-id="250d7-109">Attributes</span></span>  
  
|<span data-ttu-id="250d7-110">属性名称</span><span class="sxs-lookup"><span data-stu-id="250d7-110">Attribute name</span></span>|<span data-ttu-id="250d7-111">Description</span><span class="sxs-lookup"><span data-stu-id="250d7-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="250d7-112">“属性”</span><span class="sxs-lookup"><span data-stu-id="250d7-112">Name</span></span>|<span data-ttu-id="250d7-113">将附加到 BAM 活动的关系的名称。</span><span class="sxs-lookup"><span data-stu-id="250d7-113">Name of the relationship that will be attached to the BAM activity.</span></span>|  
|<span data-ttu-id="250d7-114">类型</span><span class="sxs-lookup"><span data-stu-id="250d7-114">Type</span></span>|<span data-ttu-id="250d7-115">任意字符串，指定将附加到 BAM 活动的关系的类型。</span><span class="sxs-lookup"><span data-stu-id="250d7-115">Arbitrary string specifying the type of relationship that will be attached to the BAM activity.</span></span> <span data-ttu-id="250d7-116">支持的任意字符串和以下预定义的 BAM 类型：</span><span class="sxs-lookup"><span data-stu-id="250d7-116">Both arbitrary strings and the following predefined BAM types are supported:</span></span><br /><br /> <span data-ttu-id="250d7-117">-   BizTalkService</span><span class="sxs-lookup"><span data-stu-id="250d7-117">-   BizTalkService</span></span><br /><span data-ttu-id="250d7-118">-   MessageID</span><span class="sxs-lookup"><span data-stu-id="250d7-118">-   MessageID</span></span><br /><span data-ttu-id="250d7-119">-活动</span><span class="sxs-lookup"><span data-stu-id="250d7-119">-   Activity</span></span><br /><span data-ttu-id="250d7-120">-   DocumentUrl</span><span class="sxs-lookup"><span data-stu-id="250d7-120">-   DocumentUrl</span></span><br /><span data-ttu-id="250d7-121">-InstanceID</span><span class="sxs-lookup"><span data-stu-id="250d7-121">-   InstanceID</span></span><br /><br /> <span data-ttu-id="250d7-122">预定义的 BAM 引用类型的详细信息，请参阅[引用属性](http://go.microsoft.com/fwlink/?LinkId=119601)。</span><span class="sxs-lookup"><span data-stu-id="250d7-122">For more information on predefined BAM reference types, see [Reference Properties](http://go.microsoft.com/fwlink/?LinkId=119601).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="250d7-123">子元素</span><span class="sxs-lookup"><span data-stu-id="250d7-123">Child Elements</span></span>  
  
|<span data-ttu-id="250d7-124">执行状态</span><span class="sxs-lookup"><span data-stu-id="250d7-124">Execution status</span></span>|<span data-ttu-id="250d7-125">Description</span><span class="sxs-lookup"><span data-stu-id="250d7-125">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="250d7-126">数据</span><span class="sxs-lookup"><span data-stu-id="250d7-126">Data</span></span>|<span data-ttu-id="250d7-127">指定如何提取最多将附加到 BAM 活动的 128 个字符的字符串数据。</span><span class="sxs-lookup"><span data-stu-id="250d7-127">Specifies how to extract string data up to 128 characters that will be attached to the BAM activity.</span></span>|  
|<span data-ttu-id="250d7-128">LongData</span><span class="sxs-lookup"><span data-stu-id="250d7-128">LongData</span></span>|<span data-ttu-id="250d7-129">指定如何提取将附加到 BAM 活动的任意长度的字符串数据。</span><span class="sxs-lookup"><span data-stu-id="250d7-129">Specifies how to extract arbitrarily long string data that will be attached to the BAM activity.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="250d7-130">一个`Reference`元素可以组合一个或多个**数据**并**LongData**所需的子元素。</span><span class="sxs-lookup"><span data-stu-id="250d7-130">A `Reference` element can combine one or more **Data** and **LongData** child elements as needed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="250d7-131">备注</span><span class="sxs-lookup"><span data-stu-id="250d7-131">Remarks</span></span>  
 <span data-ttu-id="250d7-132">引用表达式中不允许以下常见运算：</span><span class="sxs-lookup"><span data-stu-id="250d7-132">The following common operations are not allowed in Reference expressions:</span></span>  
  
-   <span data-ttu-id="250d7-133">And</span><span class="sxs-lookup"><span data-stu-id="250d7-133">And</span></span>  
  
-   <span data-ttu-id="250d7-134">等于</span><span class="sxs-lookup"><span data-stu-id="250d7-134">Equals</span></span>  
  
## <a name="example"></a><span data-ttu-id="250d7-135">示例</span><span class="sxs-lookup"><span data-stu-id="250d7-135">Example</span></span>  
 <span data-ttu-id="250d7-136">在以下示例中，使用创建的类型为"DocumentUrl"名为"Related Document"的引用`GetUserData`工作流。</span><span class="sxs-lookup"><span data-stu-id="250d7-136">In the following sample, a reference named "Related Document" of type "DocumentUrl" is created using `GetUserData` for a workflow.</span></span> <span data-ttu-id="250d7-137">用户数据应为小于 1024年个字符的长度，因为`Data`元素用于包含`Expression`元素。</span><span class="sxs-lookup"><span data-stu-id="250d7-137">Because the user data is expected to be fewer than 1024 characters in length, the `Data` element is used to contain the `Expression` element.</span></span>  
  
```  
<ic:Reference Name="Related Document" Type="DocumentUrl">  
  <ic:Data>  
    <ic:Expression>  
      <wf:Operation Name="GetUserData" />  
    </ic:Expression>  
  </ic:Data>  
</ic:Reference>  
```  
  
 <span data-ttu-id="250d7-138">**引用**元素支持混用`Data`和`LongData`元素。</span><span class="sxs-lookup"><span data-stu-id="250d7-138">The **Reference** element supports a mix of `Data` and `LongData` elements.</span></span> <span data-ttu-id="250d7-139">在以下示例中，从 WCF 服务检索并写入"MyType"类型的关系"Long and Short Data"将从采购订单的国家/地区名称和备注字段。</span><span class="sxs-lookup"><span data-stu-id="250d7-139">In the following sample, the country name and note fields from a purchase order are retrieved from a WCF service and written to the relationship "Long and Short Data" as type "MyType".</span></span> <span data-ttu-id="250d7-140">由于备注字段支持超过 1024年个字符，该表达式括在`LongData`元素。</span><span class="sxs-lookup"><span data-stu-id="250d7-140">Because the note field supports more than 1024 characters, the expression is enclosed in a `LongData` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="250d7-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="250d7-141">See Also</span></span>  
 <span data-ttu-id="250d7-142">[侦听器 OnEvent 元素](../core/interceptor-onevent-element.md) </span><span class="sxs-lookup"><span data-stu-id="250d7-142">[Interceptor OnEvent Element](../core/interceptor-onevent-element.md) </span></span>  
 [<span data-ttu-id="250d7-143">EventStream.AddRelatedActivity 方法</span><span class="sxs-lookup"><span data-stu-id="250d7-143">EventStream.AddRelatedActivity Method</span></span>](http://go.microsoft.com/fwlink/?LinkId=119602)