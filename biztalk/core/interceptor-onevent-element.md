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
# <a name="interceptor-onevent-element"></a>侦听器 OnEvent 元素
**OnEvent**元素描述一个映射到封闭的 BAM 活动的实际事件。  
  
## <a name="format"></a>格式  
 `OnEvent` 元素包含子元素，这些子元素指定了事件筛选器、关联 ID 以及要更新的数据、引用数据和继续符（后三者是可选的）。  
  
### <a name="attributes"></a>属性  
  
|属性名称|Description|  
|--------------------|-----------------|  
|Name|此事件的用户定义名称。|  
|数据源|事件名称源中出现**EventSource**元素。|  
|IsBegin|布尔值，指出该事件是一个新的 BAM 活动的开始 (`true`) 还是不是一个新的 BAM 活动的开始 (`false`)。|  
|IsEnd|布尔值，指出该事件是一个 BAM 活动的结束 (`true`) 还是不是一个 BAM 活动的结束 (`false`)。|  
  
### <a name="child-elements"></a>子元素  
  
|执行状态|Description|  
|----------------------|-----------------|  
|“筛选器”|提供了一种为事件添加特定限制条件的方法。|  
|CorrelationID|指定关联 ID（活动实例 ID）。|  
|ContinuationToken|指定继续符，它是将为同一活动实例做出贡献的未来事件使用的一个关联 ID。|  
|Update|指定要从事件中提取并导入到 BAM 活动的数据。|  
|参考|添加与 BAM 活动的关系。|  
  
## <a name="remarks"></a>注释  
  
## <a name="example"></a>示例  
 以下示例演示一个典型**OnEvent** WF 的块：  
  
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
  
 此示例演示一个典型**OnEvent** WCF 服务的块：  
  
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
  
## <a name="in-this-section"></a>本节内容  
  
-   [Filter](../core/filter.md)  
  
-   [CorrelationID](../core/correlationid.md)  
  
-   [ContinuationToken](../core/continuationtoken.md)  
  
-   [参考](../core/reference.md)  
  
-   [Update](../core/update2.md)  
  
## <a name="see-also"></a>另请参阅  
 [拦截器配置文件的结构](../core/structure-of-an-interceptor-configuration-file.md)