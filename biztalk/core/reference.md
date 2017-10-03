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
# <a name="reference"></a>参考
**引用**元素可以用来向 BAM 活动中添加一个或多个关系。 当要将诸如主键、ID 或 URL 之类的指针附加到相关消息时，这特别有用。 例如，可能要在“采购订单”活动中存储指向“发货批”的引用。  
  
## <a name="format"></a>格式  
 `Reference`元素同时支持**数据**和**LongData**包含一个表达式来指定要将附加到 BAM 活动的数据的子元素。 你可以使用的任意组合**数据**和**LongData**以满足你的跟踪要求。  
  
### <a name="attributes"></a>属性  
  
|属性名称|Description|  
|--------------------|-----------------|  
|Name|将附加到 BAM 活动的关系的名称。|  
|类型|任意字符串，用于指定将附加到 BAM 活动的关系的类型。 任意字符串和以下预定义 BAM 类型均受支持：<br /><br /> -BizTalkService<br />-MessageID<br />-活动<br />-DocumentUrl<br />-InstanceID<br /><br /> 有关预定义 BAM 引用类型的详细信息，请参阅[引用属性](http://go.microsoft.com/fwlink/?LinkId=119601)。|  
  
### <a name="child-elements"></a>子元素  
  
|执行状态|Description|  
|----------------------|-----------------|  
|data|指定如何提取将附加到 BAM 活动的最多为 128 个字符的字符串数据。|  
|LongData|指定如何提取将附加到 BAM 活动的任意长度的字符串数据。|  
  
> [!NOTE]
>  A`Reference`元素可以合并一个或多**数据**和**LongData**根据需要的子元素。  
  
## <a name="remarks"></a>注释  
 Reference 表达式中不允许使用以下常见运算：  
  
-   And  
  
-   等于  
  
## <a name="example"></a>示例  
 在下面的示例中，使用 `GetUserData` 为工作流创建了一个类型为“DocumentUrl”、名为“Related Document”的引用。 需要用户数据必须少于 1024年个字符的长度，因为`Data`元素用来包含`Expression`元素。  
  
```  
<ic:Reference Name="Related Document" Type="DocumentUrl">  
  <ic:Data>  
    <ic:Expression>  
      <wf:Operation Name="GetUserData" />  
    </ic:Expression>  
  </ic:Data>  
</ic:Reference>  
```  
  
 **引用**元素支持多种`Data`和`LongData`元素。 在下面的示例中，从 WCF 服务检索采购订单中的国家/地区名称和备注字段，并将它们写入“MyType”类型的关系“Long and Short Data”中。 由于注释字段支持超过 1024年个字符，因此表达式括在`LongData`元素。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [拦截器 OnEvent 元素](../core/interceptor-onevent-element.md)   
 [EventStream.AddRelatedActivity 方法](http://go.microsoft.com/fwlink/?LinkId=119602)