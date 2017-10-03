---
title: "自定义适配器配置设计器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9b231c3-3948-4db8-b4f0-d9c21c31b168
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e876892b3eef9e5dd47c51c64997d84a0f0dc98
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="custom-adapter-configuration-designer"></a>自定义适配器配置设计器
您需要在 .NET 类库中生成自定义设计器。 您既可将它们合并到适配器的 DLL，也可生成单独的 DLL。 生成设计器程序集后，您必须通过修饰来引用该程序集，如同引用说明或类别一样。 该引用包括一个程序集规范和一个要使用的完全限定类名。  
  
 这些修饰支持引用特定的自定义设计器的两种方式： 作为全局程序集缓存中的全局程序集或位于磁盘上的外部程序集。  
  
> [!NOTE]
>  有两个可能的设计时程序集路径： 你可以指定类型编辑器和 XSD XSD 本身 （不支持相对路径） 中的配置中使用的转换器的绝对路径，也可以在全局存储类型编辑器和转换器程序集缓存，并且不需要绝对路径。  
  
## <a name="global-assembly-cache-designer-use"></a>全局程序集缓存设计器的使用  
 全局程序集缓存按照程序集名称、公钥、版本和区域性来存储程序集。 因此，建议您：  
  
1.  生成公钥文件，并将其添加到 AssemblyInfo.cs 文件中。  
  
2.  在 AssemblyInfo.cs 文件中指定特定版本。  
  
 您既可将该程序集拖入全局程序集缓存，也可使用 GACUTIL 将其添加到全局程序集缓存。  
  
 若要使用此设计器，请指定完全限定类名、逗号和全局程序集缓存程序集项（程序集名称、版本、区域性和公钥标记）作为修饰的值。 使用\<编辑器 > 修饰**UITypeEditor**实现和\<转换器 > 修饰**TypeConverter**实现。  
  
 下面的代码演示如何在 XSD 文件中初始化自定义设计器：  
  
```  
<xs:element name="Global" type="xs:string">  
   <xs:annotation>  
      <xs:appinfo>  
         <baf:designer>  
            <baf:category>GAC Designer Component</baf:category>  
            <baf:editor>AdapterManagement.ComponentModel. PasswordUITypeEditor, AdapterManagement, Version=1.0.1.0, Culture=neutral, PublicKeyToken=f0db50abb0615c18</baf:editor>  
         </baf:designer>  
      </xs:appinfo>  
   </xs:annotation>  
</xs:element>  
      </xs:sequence>  
```  
  
## <a name="external-assembly-installation-and-use"></a>外部程序集的安装和使用  
 对于外部程序集，其修饰包含一个可选的属性程序集，该程序集指定包含目标设计器的程序集的完整路径和名称。  
  
 下面的代码演示如何初始化包含在外部程序集中的自定义设计器：  
  
```  
<xs:element name="External" type="xs:string">  
   <xs:annotation>  
      <xs:appinfo>  
         <baf:designer>  
            <baf:category>External Designer Component</baf:category>  
            <baf:converter assembly="C:\source\private\Adapter\Framework\Designer\bin\Debug\Designer.External.dll">Designer.External.DesignerTypeConverter</baf:converter>  
         </baf:designer>  
      </xs:appinfo>  
   </xs:annotation>  
</xs:element>  
```  
  
## <a name="see-also"></a>另请参阅  
 [适配器配置的的自定义下拉列表编辑器](../core/custom-drop-down-editor-for-adapter-configuration.md)   
 [适配器配置的的自定义模式对话框编辑器](../core/custom-modal-dialog-editor-for-adapter-configuration.md)   
 [适配器配置的的自定义类型转换器](../core/custom-type-converter-for-adapter-configuration.md)   
 [适配器的高级的配置组件](../core/advanced-configuration-components-for-adapters.md)