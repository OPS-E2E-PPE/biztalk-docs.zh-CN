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
# <a name="reference"></a>参考
**引用**元素可用于将一个或多个关系添加到 BAM 活动。 当你想要将一个指针，如主键、 ID 或 URL 附加到相关的消息时，这很有用。 例如，你可能会采购订单活动中存储对发货批的引用。  
  
## <a name="format"></a>格式  
 `Reference`元素支持两者**数据**并**LongData**子元素包含一个表达式，指定要将附加到 BAM 活动的数据。 可以使用的任意组合**数据**并**LongData**以满足您的跟踪要求。  
  
### <a name="attributes"></a>特性  
  
|属性名称|Description|  
|--------------------|-----------------|  
|“属性”|将附加到 BAM 活动的关系的名称。|  
|类型|任意字符串，指定将附加到 BAM 活动的关系的类型。 支持的任意字符串和以下预定义的 BAM 类型：<br /><br /> -   BizTalkService<br />-   MessageID<br />-活动<br />-   DocumentUrl<br />-InstanceID<br /><br /> 预定义的 BAM 引用类型的详细信息，请参阅[引用属性](http://go.microsoft.com/fwlink/?LinkId=119601)。|  
  
### <a name="child-elements"></a>子元素  
  
|执行状态|Description|  
|----------------------|-----------------|  
|数据|指定如何提取最多将附加到 BAM 活动的 128 个字符的字符串数据。|  
|LongData|指定如何提取将附加到 BAM 活动的任意长度的字符串数据。|  
  
> [!NOTE]
>  一个`Reference`元素可以组合一个或多个**数据**并**LongData**所需的子元素。  
  
## <a name="remarks"></a>备注  
 引用表达式中不允许以下常见运算：  
  
-   And  
  
-   等于  
  
## <a name="example"></a>示例  
 在以下示例中，使用创建的类型为"DocumentUrl"名为"Related Document"的引用`GetUserData`工作流。 用户数据应为小于 1024年个字符的长度，因为`Data`元素用于包含`Expression`元素。  
  
```  
<ic:Reference Name="Related Document" Type="DocumentUrl">  
  <ic:Data>  
    <ic:Expression>  
      <wf:Operation Name="GetUserData" />  
    </ic:Expression>  
  </ic:Data>  
</ic:Reference>  
```  
  
 **引用**元素支持混用`Data`和`LongData`元素。 在以下示例中，从 WCF 服务检索并写入"MyType"类型的关系"Long and Short Data"将从采购订单的国家/地区名称和备注字段。 由于备注字段支持超过 1024年个字符，该表达式括在`LongData`元素。  
  
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
  
## <a name="see-also"></a>请参阅  
 [侦听器 OnEvent 元素](../core/interceptor-onevent-element.md)   
 [EventStream.AddRelatedActivity 方法](http://go.microsoft.com/fwlink/?LinkId=119602)