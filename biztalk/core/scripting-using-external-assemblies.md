---
title: 脚本使用外部程序集 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scripting functoids, warnings
- Scripting functoids, external assemblies
ms.assetid: 0bdf6adc-91b9-462e-8fd0-9cb48bfa7817
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 475a3b9781eecb0ccc79165bbe54e6dfd542ecfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269197"
---
# <a name="scripting-using-external-assemblies"></a>使用外部程序集编写脚本
使用外部程序集编写脚本是在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中使用脚本的首选方式。 外部程序集具有多项优点：  
  
-   便于代码共享  
  
-   维护更简单  
  
-   调试更方便  
  
> [!NOTE]
>  如果测试映射失败**脚本**functoid 使用一个外部的程序集，它不在 GAC 中注册。 它适用如果外部程序集 （放置在生成后） 的当前项目的程序集所在的 bin 文件夹中。  
  
 重新使用该脚本只需设置**脚本**属性**脚本**functoid。 由于脚本储存在映射之外，因此可以在不更改映射的情况下修改脚本。 并且你可以使用完整的数组的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]调试工具以确保你的脚本正确运行。  
  
> [!WARNING]
>  外部程序集中的代码必须为线程安全代码。 在任务繁忙时，可以同时运行多个映射实例。  
  
 有关示例函数存放在外部程序集，请参阅[（BizTalk Server 示例文件夹中） 的 XML 工具](../core/xml-tools-biztalk-server-samples-folder.md)。  
  
## <a name="see-also"></a>另请参阅  
 [脚本 Functoid](../core/scripting-functoid.md)   
 [脚本使用内联 C#、 JScript.NET 和 Visual Basic.NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)   
 [脚本使用内联 XSLT 和 XSLT 调用模板](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)   
 [如何在向地图添加脚本 Functoid](../core/how-to-add-scripting-functoids-to-a-map.md)   
 [如何配置脚本 Functoid](../core/how-to-configure-the-scripting-functoid.md)