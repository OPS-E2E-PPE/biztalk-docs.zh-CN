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
# <a name="custom-type-converter-for-adapter-configuration"></a><span data-ttu-id="73495-102">适配器配置的自定义类型转换器</span><span class="sxs-lookup"><span data-stu-id="73495-102">Custom Type Converter for Adapter Configuration</span></span>
<span data-ttu-id="73495-103">自定义编辑器，如自定义类型转换器可重写**System.ComponentModel.TypeConverter**类的一个子项。</span><span class="sxs-lookup"><span data-stu-id="73495-103">Like the custom editor, the custom type converter overrides the **System.ComponentModel.TypeConverter** class of one of its children.</span></span> <span data-ttu-id="73495-104">在这里，转换器将格式添加到要保存的值但不会出现在属性页上。</span><span class="sxs-lookup"><span data-stu-id="73495-104">Here, the converter adds formatting to the value to be persisted but does not appear on the property page.</span></span> <span data-ttu-id="73495-105">**ConvertFrom**方法将添加的字符串值括在方括号和**ConvertTo**方法会将它们删除。</span><span class="sxs-lookup"><span data-stu-id="73495-105">The **ConvertFrom** method adds square brackets around the string value and the **ConvertTo** method removes them.</span></span>  
  
 <span data-ttu-id="73495-106">以下代码是自定义类型转换器的类定义：</span><span class="sxs-lookup"><span data-stu-id="73495-106">The following code is the class definition for the custom type converter:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73495-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="73495-107">See Also</span></span>  
 <span data-ttu-id="73495-108">[自定义适配器配置设计器](../core/custom-adapter-configuration-designer.md) </span><span class="sxs-lookup"><span data-stu-id="73495-108">[Custom Adapter Configuration Designer](../core/custom-adapter-configuration-designer.md) </span></span>  
 <span data-ttu-id="73495-109">[适配器配置的自定义下拉编辑器](../core/custom-drop-down-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="73495-109">[Custom Drop-Down Editor for Adapter Configuration](../core/custom-drop-down-editor-for-adapter-configuration.md) </span></span>  
 <span data-ttu-id="73495-110">[适配器配置的的自定义模式对话框编辑器](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="73495-110">[Custom Modal Dialog Editor for Adapter Configuration](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span></span>  
 [<span data-ttu-id="73495-111">适配器的高级配置组件</span><span class="sxs-lookup"><span data-stu-id="73495-111">Advanced Configuration Components for Adapters</span></span>](../core/advanced-configuration-components-for-adapters.md)