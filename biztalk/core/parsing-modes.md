---
title: 分析模式 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- pipeline components [custom], parsing
ms.assetid: b1188720-e5ae-47ae-ab8e-16d7ed08b778
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf8f9b2618b8cafd7813f08217457227a0f21809
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263301"
---
# <a name="parsing-modes"></a>分析模式
分析模式是一个属性的 schemaInfo 记录，两种模式： 速度和复杂性。 在 BizTalk 架构编辑器中，可以配置分析器优化属性。  
  
## <a name="example"></a>示例  
  
```  
<b:schemaInfo count_positions_by_byte="false" standard="Flat File"   
root_reference="document" parser_optimization="complexity" />.  
```  
  
 在速度模式下，分析器将尝试在流中显示适合数据。 例如，给定以下架构。  
  
```  
<schema>  
   Root ("," prefix)  
      Field1   opt  
      Field2   opt  
      Field3   opt  
      Field4   opt  
      Record ("," infix)  
            Field5  
            Field6  
</schema>  
```  
  
 和输入的消息。  
  
```  
,1,2,3,4  
```  
  
 速度模式下下面的 XML 文档被获得。  
  
```  
<Root>  
   <Field1>1</Field1>  
   <Field2>2</Field2>  
   <Field3>3</Field3>  
   <Field4>4</Field4>  
</Root>  
```  
  
 复杂性模式中，相同的架构生成以下输出。  
  
```  
<Root>  
   <Field1>1</Field1>  
   <Field2>2</Field2>  
      <Record>  
         <Field5>3</Field5>  
         <Field6>4</Field6>  
      </Record>  
</Root>  
```  
  
 在复杂性模式下，平面文件分析引擎使用自顶向下和自下而上的分析过程中，并尝试以更准确地适应数据。 在速度模式下，分析器将尝试在流中显示适合数据。  
  
 如果例如具有具有必需的元素的可选元素。  
  
```  
<schema>  
   Root  
      Record1 (required)  
  
      Record2 (optional)  
  
      Record3 (required)  
  
```  
  
 你必须使用复杂性模式来正确分析数据，因为分析器表示的架构内部作为。  
  
```  
<schema>  
   Root  
      Record1 (required)  
      <sequence> (optional)  
         Record2 (required)  
         Record3 (required)  
```  
  
## <a name="see-also"></a>另请参阅  
 [使用平面文件分析引擎](../core/using-the-flat-file-parsing-engine.md)