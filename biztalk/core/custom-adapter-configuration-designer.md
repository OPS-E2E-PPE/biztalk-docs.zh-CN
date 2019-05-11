---
title: 自定义适配器配置设计器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9b231c3-3948-4db8-b4f0-d9c21c31b168
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d596d87e693dbcb0c8828087d4a3c56c00e104d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390095"
---
# <a name="custom-adapter-configuration-designer"></a>自定义适配器配置设计器
您需要自定义设计器生成到.NET 类库。 可以将其合并到适配器的 DLL 或生成单独的 DLL。 生成的设计器的程序集后，必须通过修饰，就像说明或类别一样来引用它。 该引用包括程序集和完全限定的类名，若要使用的规范。  
  
 这些修饰支持两种方法来引用特定的自定义设计器： 作为全局程序集缓存中的全局程序集或外部程序集位于磁盘上。  
  
> [!NOTE]
>  有两个可能的设计时程序集路径：可以指定的类型编辑器和转换器配置在 XSD 本身中 （不支持相对路径），XSD 中使用的绝对路径，也可以在全局程序集缓存中存储的类型编辑器和转换器并不需要绝对路径。  
  
## <a name="global-assembly-cache-designer-use"></a>全局程序集缓存设计器的使用  
 在全局程序集缓存存储程序集名称、 公钥、 版本和区域性的程序的集。 因此，建议您：  
  
1. 生成公钥文件，并将此文件添加到 AssemblyInfo.cs 文件。  
  
2. 在 AssemblyInfo.cs 文件中指定特定版本。  
  
   您可以将程序集拖放到全局程序集缓存，或使用 GACUTIL 将其添加到全局程序集缓存。  
  
   若要使用此设计器，指定完全限定的类名、 逗号和全局程序集缓存程序集项 （程序集名称、 版本、 区域性和公钥标记） 作为修饰的值。 使用\<编辑器\>修饰**UITypeEditor**实现并\<转换器\>修饰**TypeConverter**实现.  
  
   下面的代码演示如何初始化 XSD 文件中的自定义设计器：  
  
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
  
## <a name="external-assembly-installation-and-use"></a>外部程序集安装和使用  
 对于外部程序集，其修饰包含指定的完整路径和名称包含所需的设计器的程序集的可选属性程序集。  
  
 下面的代码演示如何初始化外部程序集中包含的自定义设计器：  
  
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
  
## <a name="see-also"></a>请参阅  
 [适配器配置的自定义下拉编辑器](../core/custom-drop-down-editor-for-adapter-configuration.md)   
 [适配器配置的的自定义模式对话框编辑器](../core/custom-modal-dialog-editor-for-adapter-configuration.md)   
 [适配器配置的自定义类型转换器](../core/custom-type-converter-for-adapter-configuration.md)   
 [适配器的高级配置组件](../core/advanced-configuration-components-for-adapters.md)