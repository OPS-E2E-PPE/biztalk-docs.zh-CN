---
title: 为适配器配置的自定义类型转换器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60e94dde-d29d-43ff-84b0-b2ba86851151
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f6285cd61fd0738fb97c6192cd52b812d96ede7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238709"
---
# <a name="custom-type-converter-for-adapter-configuration"></a>适配器配置的的自定义类型转换器
自定义编辑器，如自定义类型转换器可重写**System.ComponentModel.TypeConverter**类之一的子级。 转换器在此将格式添加到要保留但不会显示在属性页中的值。 **ConvertFrom**方法将添加的字符串值括在方括号和**ConvertTo**方法中删除它们。  
  
 以下代码是自定义类型转换器的类定义：  
  
```  
using System;  
using System.ComponentModel;  
  
namespace AdapterManagement.ComponentModel {  
  
   public class DesignerTypeConverter : StringConverter {  
  
      public override bool CanConvertTo(ITypeDescriptorContext context, Type destinationType) {  
         return (typeof(String) == destinationType) || base.CanConvertTo (context, destinationType);  
      }  
  
      public override object ConvertTo(ITypeDescriptorContext context, System.Globalization.CultureInfo culture, object value, Type destinationType) {  
         if (typeof(String) == destinationType && value is String) {  
            return ((String)value).TrimStart('[').TrimEnd(']');  
         }  
         return base.ConvertTo (context, culture, value, destinationType);  
      }  
  
      public override bool CanConvertFrom(ITypeDescriptorContext context, Type sourceType) {  
         return (typeof(String) == sourceType) || base.CanConvertFrom (context, sourceType);  
      }  
  
      public override object ConvertFrom(ITypeDescriptorContext context, System.Globalization.CultureInfo culture, object value) {  
         if (value is String) {  
            return "["+(String)value+"]";  
         }  
         return base.ConvertFrom (context, culture, value);  
      }  
   }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [自定义适配器配置设计器](../core/custom-adapter-configuration-designer.md)   
 [适配器配置的的自定义下拉列表编辑器](../core/custom-drop-down-editor-for-adapter-configuration.md)   
 [适配器配置的的自定义模式对话框编辑器](../core/custom-modal-dialog-editor-for-adapter-configuration.md)   
 [适配器的高级的配置组件](../core/advanced-configuration-components-for-adapters.md)