---
title: "适配器 Framework 配置架构修饰标记 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d5d7f6b-2273-45a6-ba9d-43201760cf22
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d49aac9f11ef48bd0a66dcc9bda3a769cd6c34f4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="adapter-framework-configuration-schema-decoration-tags"></a>适配器 Framework 配置架构修饰标记
您可以在配置架构文件中使用本主题所述的标记来显示和组织适配器属性页上的数据。  
  
 下图显示了 FTP 接收位置属性页如何实现其中的一些标记。  
  
 ![](../core/media/ebiz-prog-custad-tags.gif "ebiz_prog_custad_tags")  
\<说明\>， \<displayname\>，和\<类别\>FTP 适配器属性页中的标记  
  
## <a name="designer"></a>\<设计器\>  
 BizTalk 适配器 Framework 修饰之间出现\<baf:designer\>标记和\</baf:designer\>结束标记。 \<Baf:designer\>标记可帮助区分适配器 Framework \<appinfo\>和其他适配器提供\<appinfo\>信息。  
  
## <a name="category"></a>\<类别\>  
 \<类别\>修饰包含用来分隔为组在属性网格中的项的字符串。 该修饰将具有同一类别字符串的所有条目显示为该类别的从属条目。  
  
 可以本地化\<类别\>条目。  
  
## <a name="description"></a>\<description\>  
 \<说明\>修饰包含用于为在属性网格底部的条目中提供说明性文本的字符串。  
  
 可以本地化\<说明\>条目。  
  
## <a name="displayname"></a>\<displayname\>  
 \<Displayname\>修饰包含用于显示条目的名称的字符串。 这使你可以使用空格、 短语和等等，当它们将不允许用于\<元素\>或\<属性\>名称。  
  
 可以本地化\<displayname\>条目。  
  
## <a name="readonly"></a>\<readonly\>  
 \<Readonly 固定 =""\>修饰控制是否可编辑字段。 如果“fixed”属性值为 `true`（默认值），则字段为只读。  
  
 当实现外部编辑器，实现外部**TypeConverter**类并重写**GetStandardValuesExclusive(ITypeDescriptorContext)**方法相反。 返回`true`使字段成为只读的但会保留到自定义编辑器的访问。  
  
## <a name="browsable"></a>\<可浏览\>  
 \<可浏览显示 =""\>修饰控制字段是否显示在属性网格。 如果“show”属性值为 `True`（默认值），则字段将出现在网格中。  
  
## <a name="converter"></a>\<转换器\>  
 \<转换器程序集 =""\>修饰指定所需**TypeConverter**类名称\<元素\>或\<属性\>。 可选的"程序集"属性值指定包含所需的程序集的路径**TypeConverter**。 如果不指定“assembly”值，类名必须包括全局程序集缓存的程序集名称、密钥、区域性和版本值。  
  
## <a name="editor"></a>\<编辑器\>  
 \<编辑器程序集 =""\>修饰指定所需**UITypeEditor**类名称\<元素\>或\<属性\>。 可选的"程序集"属性值指定包含所需的程序集的路径**UITypeEditor**。 如果不指定“assembly”值，类名必须包括全局程序集缓存的程序集名称、密钥、区域性和版本值。  
  
## <a name="null-values-for-optional-enumerations"></a>可选枚举的空值  
 在使用可选的枚举，其中一个值应为\<无\>来表示 null 值。 这不是内置标记，但如果枚举是从 xsd:string 派生的，则可以通过提供视为空值的枚举值来生成此标记。 从 xsd:int 派生的枚举无法生成此标记，因为整数必须包含值。  
  
## <a name="see-also"></a>另请参阅  
 [适配器框架配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)