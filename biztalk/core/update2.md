---
title: Update2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 770c9ebb-df3a-428f-be18-b36535352f8d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c090d11686babacfcb854782484b689dff2102e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398612"
---
# <a name="update"></a>Update
`Update`元素用于从事件中提取数据并将其导入在相关 BAM 活动。  
  
## <a name="format"></a>格式  
 若要使用`Update`元素，你必须提供列名称和类型和一个**表达式**包含一个或多个元素**操作**的计算结果为单个字符串值的元素。  
  
```  
<ic:Update DataItemName="Name" Type="Type">  
  <ic:Expression>  
    <!-- one or more Operation elements -->  
  </ic:Expression>  
</ic:Update>  
```  
  
### <a name="attributes"></a>特性  
  
|属性名称|Description|  
|--------------------|-----------------|  
|ColumnName|BAM 活动检查点的名称。 这是将更新与提取的数据的检查点。|  
|类型|BAM 数据类型的检查点;必须是以下值之一：<br /><br /> -   NVARCHAR<br />-   DATETIME<br />-   INT<br />-   FLOAT|  
  
## <a name="remarks"></a>备注  
 中不支持以下操作`Update`表达式：  
  
-   And  
  
-   等于  
  
## <a name="example"></a>示例  
 在以下示例中， **GetContextProperty** WF 操作用于检索**EventTime**属性。 此值将存储为**DATETIME** BAM 活动的"StartOrderProcessing"数据项的类型。  
  
```  
<ic:Update DataItemName="StartOrderProcessing" Type="DATETIME">  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
## <a name="see-also"></a>请参阅  
 [侦听器 OnEvent 元素](../core/interceptor-onevent-element.md)