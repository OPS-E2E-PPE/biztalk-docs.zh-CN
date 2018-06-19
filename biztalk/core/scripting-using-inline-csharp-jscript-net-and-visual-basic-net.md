---
title: 脚本使用内联 C#、 JScript.NET 和 Visual Basic.NET |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scripting functoids, JScript
- Scripting functoids, warnings
- Scripting functoids, Visual Basic .NET
- Scripting functoids, inline C#
- Scripting functoids, .NET
ms.assetid: dda60024-58bd-483f-a750-31b21059eded
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe2002bd92342a953406a21e076b801d3e90b938
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974539"
---
# <a name="scripting-using-inline-c-jscript-net-and-visual-basic-net"></a>使用内联 C#、JScript .NET 和 Visual Basic .NET 编写脚本
对于在应用程序中其他地方不太可能使用的自定义代码，使用内联脚本非常方便。  
  
 BizTalk 将内联脚本保存在定义映射的可扩展样式表语言转换 (XSLT) 样式表中。 因此，内联脚本可以与其他任何 XSLT 样式表脚本使用相同的命名空间。 下表显示了可用的命名空间：  
  
|命名空间|Description|  
|---------------|-----------------|  
|系统|系统类。|  
|System.Collection|集合类。|  
|System.Text|文本类。|  
|System.Text.RegularExpressions|正则表达式类。|  
|System.Xml|核心 XML 类。|  
|System.Xml.Xsl|XSLT 类。|  
|System.Xml.Xpath|XPath 类。|  
|Microsoft.VisualBasic|Visual Basic 脚本类。|  
  
 有关命名空间和数据类型的详细信息，搜索"XSLT 样式表脚本使用\<msxsl: script\>"和"System.Xml.Xsl.XslCompiledTransform".NET Framework 集合中。  
  
> [!CAUTION]
>  应避免多次使用同一个方法签名。 如果多个“脚本”functoid 具有相同的方法签名，则 BizTalk 会选择实现的第一个方法签名，而忽略其他签名。  
  
 除对于一次性脚本很方便之外，内联脚本对于声明在多个脚本中使用的全局变量也很有用。 例如，在 C# 内联脚本中，可以将以下代码行放在任何类之外：  
  
```  
ArrayList statusList = new ArrayList();  
```  
  
 这将创建**ArrayList**， `statusList`，供在映射中的所有内联脚本。  
  
 一个内联脚本示例，请参阅[（BizTalk Server 示例文件夹中） 的 XML 工具](../core/xml-tools-biztalk-server-samples-folder.md)。  
  
## <a name="see-also"></a>另请参阅  
 [脚本 Functoid](../core/scripting-functoid.md)   
 [脚本使用外部程序集](../core/scripting-using-external-assemblies.md)   
 [脚本使用内联 XSLT 和 XSLT 调用模板](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)   
 [如何在向地图添加脚本 Functoid](../core/how-to-add-scripting-functoids-to-a-map.md)   
 [如何配置脚本 Functoid](../core/how-to-configure-the-scripting-functoid.md)