---
title: 解析模式 |Microsoft Docs
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
ms.openlocfilehash: 72955f1dd560a442e011e176007defa236d39386
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395043"
---
# <a name="parsing-modes"></a>解析模式
解析模式是具有两种模式的 schemaInfo 记录的属性： 速度和复杂度。 分析程序优化属性可以配置 BizTalk 架构编辑器中。  
  
## <a name="example"></a>示例  
  
```  
<b:schemaInfo count_positions_by_byte="false" standard="Flat File"   
root_reference="document" parser_optimization="complexity" />.  
```  
  
 在速度模式下，分析器会尝试以适应数据在流中的显示方式。 例如，给定以下架构。  
  
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
  
 并输入的消息。  
  
```  
,1,2,3,4  
```  
  
 使用速度模式下面的 XML 文档被获取。  
  
```  
<Root>  
   <Field1>1</Field1>  
   <Field2>2</Field2>  
   <Field3>3</Field3>  
   <Field4>4</Field4>  
</Root>  
```  
  
 复杂性模式下，相同的架构将生成以下输出。  
  
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
  
 在复杂性模式下，平面文件解析引擎使用自上而下和自下而上的分析，并会尝试以更准确地适应数据。 在速度模式下，分析器会尝试以适应数据在流中的显示方式。  
  
 如果你有具有所需元素的可选元素为例。  
  
```  
<schema>  
   Root  
      Record1 (required)  
  
      Record2 (optional)  
  
      Record3 (required)  
  
```  
  
 您必须使用复杂性模式可以正确地分析数据，因为分析器表示的架构在内部作为。  
  
```  
<schema>  
   Root  
      Record1 (required)  
      <sequence> (optional)  
         Record2 (required)  
         Record3 (required)  
```  
  
## <a name="see-also"></a>请参阅  
 [使用平面文件解析引擎](../core/using-the-flat-file-parsing-engine.md)