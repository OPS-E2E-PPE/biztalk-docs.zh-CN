---
title: 使用内联编写脚本C#，JScript.NET 和 Visual Basic.NET |Microsoft Docs
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
ms.openlocfilehash: 74eca3ecd01af709b6b8c7aefe250e02679445a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251228"
---
# <a name="scripting-using-inline-c-jscript-net-and-visual-basic-net"></a>使用内联 C#、 JScript.NET 和 Visual Basic.NET 编写脚本
内联脚本非常方便的应用程序中不太可能使用在其他位置的自定义代码。  
  
 BizTalk 将内联脚本保存在定义映射的可扩展样式表语言转换 (XSLT) 样式表中。 因此，内联脚本可能会作为任何其他 XSLT 样式表脚本使用相同的命名空间。 下表显示可用命名空间。  
  
|命名空间|Description|  
|---------------|-----------------|  
|系统|系统类。|  
|System.Collection|集合类。|  
|System.Text|文本类。|  
|System.Text.RegularExpressions|中的正则表达式类。|  
|System.Xml|核心 XML 类。|  
|System.Xml.Xsl|XSLT 类。|  
|System.Xml.Xpath|XPath 类。|  
|Microsoft.VisualBasic|Visual Basic 脚本类。|  
  
 有关命名空间和数据类型的详细信息，搜索"使用 XSLT 样式表脚本\<msxsl: script\>"和"system.xml.xsl.xslcompiledtransform".NET Framework 集合中。  
  
> [!CAUTION]
>  避免多次使用相同的方法签名。 当多个脚本 functoid 具有相同的方法签名时，BizTalk 选择第一个实现，并忽略其他。  
  
 除了便于一次性脚本之外，内联脚本还可以用于声明多个脚本中使用的全局变量。 例如，在C#内联脚本，则可以放入以下任何类之外的代码行。  
  
```  
ArrayList statusList = new ArrayList();  
```  
  
 这将创建**ArrayList**， `statusList`，供在映射中的所有内联脚本。  
  
 内联脚本的示例，请参阅[XML 工具 （BizTalk Server 示例文件夹）](../core/xml-tools-biztalk-server-samples-folder.md)。  
  
## <a name="see-also"></a>请参阅  
 [脚本 Functoid](../core/scripting-functoid.md)   
 [使用外部程序集编写脚本](../core/scripting-using-external-assemblies.md)   
 [使用内联 XSLT 和 XSLT 调用模板编写脚本](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)   
 [如何向映射添加脚本 Functoid](../core/how-to-add-scripting-functoids-to-a-map.md)   
 [如何配置脚本 Functoid](../core/how-to-configure-the-scripting-functoid.md)