---
title: 拦截器 OnEvent 元素 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d684ac8e-61bc-410b-97a2-6fd3549e0d97
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6fb70b2536dbf5db5b0abc03bc194de154b4317
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257605"
---
# <a name="interceptor-onevent-element"></a><span data-ttu-id="4a363-102">侦听器 OnEvent 元素</span><span class="sxs-lookup"><span data-stu-id="4a363-102">Interceptor OnEvent Element</span></span>
<span data-ttu-id="4a363-103">**OnEvent**元素描述一个映射到封闭的 BAM 活动的实际事件。</span><span class="sxs-lookup"><span data-stu-id="4a363-103">The **OnEvent** element describes one real event that is mapped to the enclosing BAM activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="4a363-104">格式</span><span class="sxs-lookup"><span data-stu-id="4a363-104">Format</span></span>  
 <span data-ttu-id="4a363-105">`OnEvent` 元素包含子元素，这些子元素指定了事件筛选器、关联 ID 以及要更新的数据、引用数据和继续符（后三者是可选的）。</span><span class="sxs-lookup"><span data-stu-id="4a363-105">The `OnEvent` element contains child elements that specify an event filter, the correlation ID and optionally which data to update, reference data, and a continuation token.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a363-106">属性</span><span class="sxs-lookup"><span data-stu-id="4a363-106">Attributes</span></span>  
  
|<span data-ttu-id="4a363-107">属性名称</span><span class="sxs-lookup"><span data-stu-id="4a363-107">Attribute name</span></span>|<span data-ttu-id="4a363-108">Description</span><span class="sxs-lookup"><span data-stu-id="4a363-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="4a363-109">Name</span><span class="sxs-lookup"><span data-stu-id="4a363-109">Name</span></span>|<span data-ttu-id="4a363-110">此事件的用户定义名称。</span><span class="sxs-lookup"><span data-stu-id="4a363-110">User-defined name for this event.</span></span>|  
|<span data-ttu-id="4a363-111">数据源</span><span class="sxs-lookup"><span data-stu-id="4a363-111">Source</span></span>|<span data-ttu-id="4a363-112">事件名称源中出现**EventSource**元素。</span><span class="sxs-lookup"><span data-stu-id="4a363-112">Name of the event source as it appears in an **EventSource** element.</span></span>|  
|<span data-ttu-id="4a363-113">IsBegin</span><span class="sxs-lookup"><span data-stu-id="4a363-113">IsBegin</span></span>|<span data-ttu-id="4a363-114">布尔值，指出该事件是一个新的 BAM 活动的开始 (`true`) 还是不是一个新的 BAM 活动的开始 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="4a363-114">Boolean value indicating whether the event is the beginning of a new BAM activity (`true`) or not (`false`).</span></span>|  
|<span data-ttu-id="4a363-115">IsEnd</span><span class="sxs-lookup"><span data-stu-id="4a363-115">IsEnd</span></span>|<span data-ttu-id="4a363-116">布尔值，指出该事件是一个 BAM 活动的结束 (`true`) 还是不是一个 BAM 活动的结束 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="4a363-116">Boolean value indicating whether the event is the end of a BAM activity (`true`) or not (`false`).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a363-117">子元素</span><span class="sxs-lookup"><span data-stu-id="4a363-117">Child Elements</span></span>  
  
|<span data-ttu-id="4a363-118">执行状态</span><span class="sxs-lookup"><span data-stu-id="4a363-118">Execution status</span></span>|<span data-ttu-id="4a363-119">Description</span><span class="sxs-lookup"><span data-stu-id="4a363-119">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="4a363-120">“筛选器”</span><span class="sxs-lookup"><span data-stu-id="4a363-120">Filter</span></span>|<span data-ttu-id="4a363-121">提供了一种为事件添加特定限制条件的方法。</span><span class="sxs-lookup"><span data-stu-id="4a363-121">Provides a way to limit the event to specific criteria.</span></span>|  
|<span data-ttu-id="4a363-122">CorrelationID</span><span class="sxs-lookup"><span data-stu-id="4a363-122">CorrelationID</span></span>|<span data-ttu-id="4a363-123">指定关联 ID（活动实例 ID）。</span><span class="sxs-lookup"><span data-stu-id="4a363-123">Specifies the correlation ID (the activity instance ID).</span></span>|  
|<span data-ttu-id="4a363-124">ContinuationToken</span><span class="sxs-lookup"><span data-stu-id="4a363-124">ContinuationToken</span></span>|<span data-ttu-id="4a363-125">指定继续符，它是将为同一活动实例做出贡献的未来事件使用的一个关联 ID。</span><span class="sxs-lookup"><span data-stu-id="4a363-125">Specifies the continuation token, a correlation ID that is used by future events that will contribute to the same activity instance.</span></span>|  
|<span data-ttu-id="4a363-126">Update</span><span class="sxs-lookup"><span data-stu-id="4a363-126">Update</span></span>|<span data-ttu-id="4a363-127">指定要从事件中提取并导入到 BAM 活动的数据。</span><span class="sxs-lookup"><span data-stu-id="4a363-127">Specifies the data to extract from the event and import into the BAM activity.</span></span>|  
|<span data-ttu-id="4a363-128">参考</span><span class="sxs-lookup"><span data-stu-id="4a363-128">Reference</span></span>|<span data-ttu-id="4a363-129">添加与 BAM 活动的关系。</span><span class="sxs-lookup"><span data-stu-id="4a363-129">Adds a relationship to a BAM activity.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a363-130">注释</span><span class="sxs-lookup"><span data-stu-id="4a363-130">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a363-131">示例</span><span class="sxs-lookup"><span data-stu-id="4a363-131">Example</span></span>  
 <span data-ttu-id="4a363-132">以下示例演示一个典型**OnEvent** WF 的块：</span><span class="sxs-lookup"><span data-stu-id="4a363-132">The following example shows a typical **OnEvent** block for WF:</span></span>  
  
```  
<ic:OnEvent Name="BeginAct" IsBegin="true" Source="ResWF">  
  <ic:Filter>  
    <ic:Expression>  
      <wf:Operation Name="GetActivityName"/>  
      <ic:Operation Name="Constant">  
        <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name="Equals"/>  
      <wf:Operation Name="GetActivityEvent"/>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Closed</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name="Equals"/>  
      <ic:Operation Name="And"/>  
    </ic:Expression>  
  </ic:Filter>  
  <ic:CorrelationID>  
    <ic:Expression>  
      <wf:Operation Name="GetContextProperty">  
        <wf:Argument>InstanceId</wf:Argument>  
      </wf:Operation>  
    </ic:Expression>  
  </ic:CorrelationID>  
  <ic:Update DataItemName="StartOrderProcessing" Type="DATETIME">  
    <ic:Expression>  
      <wf:Operation Name="GetContextProperty">  
        <wf:Argument>EventTime</wf:Argument>  
      </wf:Operation>  
    </ic:Expression>  
  </ic:Update>  
  <ic:Update DataItemName="FoodItem" Type="NVARCHAR">  
    <ic:Expression>  
      <wf:Operation Name="GetWorkflowProperty">  
        <wf:Argument>foodItem</wf:Argument>  
      </wf:Operation>  
    </ic:Expression>  
  </ic:Update>  
</ic:OnEvent>  
```  
  
 <span data-ttu-id="4a363-133">此示例演示一个典型**OnEvent** WCF 服务的块：</span><span class="sxs-lookup"><span data-stu-id="4a363-133">This example shows a typical **OnEvent** block for WCF service:</span></span>  
  
```  
<ic:OnEvent IsBegin="true" IsEnd ="false" Name ="AuthorizationRequestService" Source="ESCreditCardService">  
  <ic:Filter>  
    <ic:Expression>  
      <wcf:Operation Name="GetServiceContractCallPoint"/>  
      <ic:Operation Name ="Constant">  
        <ic:Argument>ServiceRequest</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name ="Equals"/>  
      <wcf:Operation Name="GetOperationName" />  
      <ic:Operation Name="Constant">  
        <ic:Argument>AuthorizeWithDataContract</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name ="Equals" />  
      <ic:Operation Name ="And" />  
    </ic:Expression>  
  </ic:Filter>  
  <ic:CorrelationID>  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>ServiceRequest</ic:Argument>  
      </ic:Operation>  
    </ic:Expression>  
  </ic:CorrelationID>  
  <ic:Update DataItemName="Name" Type="NVARCHAR">  
    <ic:Expression>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body/ccservice:*/ccservice:creditCard/creditcard:FirstName</wcf:Argument>  
      </wcf:Operation>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body/ccservice:*/ccservice:creditCard/creditcard:LastName</wcf:Argument>  
      </wcf:Operation>  
      <ic:Operation Name ="Concatenate"/>  
    </ic:Expression>  
  </ic:Update>  
</ic:OnEvent>  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="4a363-134">本节内容</span><span class="sxs-lookup"><span data-stu-id="4a363-134">In This Section</span></span>  
  
-   [<span data-ttu-id="4a363-135">Filter</span><span class="sxs-lookup"><span data-stu-id="4a363-135">Filter</span></span>](../core/filter.md)  
  
-   [<span data-ttu-id="4a363-136">CorrelationID</span><span class="sxs-lookup"><span data-stu-id="4a363-136">CorrelationID</span></span>](../core/correlationid.md)  
  
-   [<span data-ttu-id="4a363-137">ContinuationToken</span><span class="sxs-lookup"><span data-stu-id="4a363-137">ContinuationToken</span></span>](../core/continuationtoken.md)  
  
-   [<span data-ttu-id="4a363-138">参考</span><span class="sxs-lookup"><span data-stu-id="4a363-138">Reference</span></span>](../core/reference.md)  
  
-   [<span data-ttu-id="4a363-139">Update</span><span class="sxs-lookup"><span data-stu-id="4a363-139">Update</span></span>](../core/update2.md)  
  
## <a name="see-also"></a><span data-ttu-id="4a363-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a363-140">See Also</span></span>  
 [<span data-ttu-id="4a363-141">拦截器配置文件的结构</span><span class="sxs-lookup"><span data-stu-id="4a363-141">Structure of an Interceptor Configuration File</span></span>](../core/structure-of-an-interceptor-configuration-file.md)