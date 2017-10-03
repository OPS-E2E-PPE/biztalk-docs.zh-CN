---
title: "更新 2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 770c9ebb-df3a-428f-be18-b36535352f8d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4376cae94e91f462974c626a57170b80b0117ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="update"></a>Update
`Update`元素用来从事件中提取数据并将其导入相关的 BAM 活动。  
  
## <a name="format"></a>格式  
 若要使用`Update`元素，你必须提供两个列名称和类型和**表达式**元素，其中包含一个或多个**操作**计算结果为单个字符串值的元素。  
  
```  
<ic:Update DataItemName="Name" Type="Type">  
  <ic:Expression>  
    <!-- one or more Operation elements -->  
  </ic:Expression>  
</ic:Update>  
```  
  
### <a name="attributes"></a>属性  
  
|属性名称|Description|  
|--------------------|-----------------|  
|ColumnName|BAM 活动检查点名称。 将使用提取的数据对该检查点进行更新。|  
|类型|检查点的 BAM 数据类型；它必须是以下类型之一：<br /><br /> -NVARCHAR<br />-DATETIME<br />INT<br />浮点型|  
  
## <a name="remarks"></a>注释  
 中不支持以下操作`Update`表达式：  
  
-   And  
  
-   等于  
  
## <a name="example"></a>示例  
 在下面的示例中， **GetContextProperty** WF 操作用于检索**EventTime**属性。 此值将存储为**DATETIME** BAM 活动的"StartOrderProcessing"数据项目类型。  
  
```  
<ic:Update DataItemName="StartOrderProcessing" Type="DATETIME">  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
## <a name="see-also"></a>另请参阅  
 [拦截器 OnEvent 元素](../core/interceptor-onevent-element.md)