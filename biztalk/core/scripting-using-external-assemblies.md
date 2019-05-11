---
title: 使用外部程序集编写脚本 |Microsoft Docs
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
ms.openlocfilehash: 4876d0b7c236be890649e5050b09e538b07742a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395527"
---
# <a name="scripting-using-external-assemblies"></a>使用外部程序集编写脚本
使用外部程序集编写脚本是使用 Microsoft 中的脚本的首选的方式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 外部程序集提供了几项优势：  
  
-   便于代码共享  
  
-   维护更简单  
  
-   更轻松地调试  
  
> [!NOTE]
>  如果将测试映射失败**脚本**functoid 使用未在 GAC 中注册的外部程序集。 如果外部程序集在当前项目的程序集 （生成后放置） 所在的 bin 文件夹中，它有效。  
  
 重新使用脚本，只需要设置**脚本**的属性**脚本**functoid。 由于该脚本存储在映射之外，您可以修改脚本，而无需更改代码图。 您可以使用的完整阵列[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]调试工具，以确保您的脚本能够正常运行。  
  
> [!WARNING]
>  在外部程序集中的代码必须是线程安全。 高负荷环境下可能会同时运行多个映射实例。  
  
 示例函数位于外部程序集，请参阅[XML 工具 （BizTalk Server 示例文件夹）](../core/xml-tools-biztalk-server-samples-folder.md)。  
  
## <a name="see-also"></a>请参阅  
 [脚本 Functoid](../core/scripting-functoid.md)   
 [使用内联 C#、 JScript.NET 和 Visual Basic.NET 编写脚本](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)   
 [使用内联 XSLT 和 XSLT 调用模板编写脚本](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)   
 [如何向映射添加脚本 Functoid](../core/how-to-add-scripting-functoids-to-a-map.md)   
 [如何配置脚本 Functoid](../core/how-to-configure-the-scripting-functoid.md)