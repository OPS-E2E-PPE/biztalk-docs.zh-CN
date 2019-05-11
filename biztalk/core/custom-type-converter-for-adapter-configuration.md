---
title: 适配器配置的自定义类型转换器 |Microsoft Docs
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
ms.openlocfilehash: cc107422d7bb2033d68c96c27df4850acda74a09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390059"
---
# <a name="custom-type-converter-for-adapter-configuration"></a>适配器配置的自定义类型转换器
自定义编辑器，如自定义类型转换器可重写**System.ComponentModel.TypeConverter**类的一个子项。 在这里，转换器将格式添加到要保存的值但不会出现在属性页上。 **ConvertFrom**方法将添加的字符串值括在方括号和**ConvertTo**方法会将它们删除。  
  
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
  
## <a name="see-also"></a>请参阅  
 [自定义适配器配置设计器](../core/custom-adapter-configuration-designer.md)   
 [适配器配置的自定义下拉编辑器](../core/custom-drop-down-editor-for-adapter-configuration.md)   
 [适配器配置的的自定义模式对话框编辑器](../core/custom-modal-dialog-editor-for-adapter-configuration.md)   
 [适配器的高级配置组件](../core/advanced-configuration-components-for-adapters.md)