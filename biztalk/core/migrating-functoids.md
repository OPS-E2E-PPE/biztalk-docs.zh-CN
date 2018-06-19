---
title: 迁移 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoids, migrating
- migrating, maps
- Migrating functoids, about Migrating functoids
- Migrating functoids
- Scripting functoids
- migrating, functoids
- migrating, Scripting functoids
ms.assetid: fc5b3ac9-28c6-41df-b779-15a8c3188528
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fac30a9b884bc769752623003d16e7089b140d4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009318"
---
# <a name="migrating-functoids"></a>迁移 Functoid
当你从以前版本的 BizTalk Server 中迁移地图给 BizTalk Server 时，包括在映射任何 functoid 也会被迁移。 如果不包括迁移 functoid**脚本**functoid，没有其他迁移所需的任务。 但是如果你的代码图包括**脚本**functoid 或者自定义 functoid，你可能必须执行其他步骤。  
  
 在以前版本的 BizTalk Server 中，所有自定义脚本附带**脚本**functoid 已以内联方式编写。 也就是说，在创建该 functoid 后，该 functoid 在运行时调用的所有脚本都与该 functoid 一起存储。 如果你想要使用不同 functoid 的同一个脚本，你可以复制并粘贴它从一个**脚本**functoid 到另一个字符串，或者让你重写从零开始的脚本。  
  
 在迁移映射时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将复制随所包含 functoid 一起提供的现有内联脚本。 但是，并非所有脚本可能正常工作。 BizTalk Server 使用 Visual Basic.NET 和 JScript.NET，而不是 VBScript 和 JScript 以前版本中使用。 这些语言的 .NET 版本在语法上有一些更改。  
  
> [!NOTE]
>  请务必测试你**脚本**functoid 迁移后的。  
  
 你将需要重写自定义 functoid。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]需要自定义 functoid 来使用.NET framework。 因为，在该版本中无法使用基于 COM 的早期版本自定义 functoid。 您可以重新编写自定义 functoid，以使用 .NET Framework。 有关自定义 functoid 的示例代码，请参阅[自定义 Functoid （BizTalk Server 示例）](../core/custom-functoid-biztalk-server-sample.md)。  
  
 一种替代方法是在外部程序集中包装的自定义 functoid 功能并调用通过此程序集**脚本**functoid。 以下部分将介绍此过程。  
  
### <a name="to-migrate-your-custom-functoids"></a>迁移自定义 functoid  
  
1.  使用 .NET 语言（如 Microsoft Visual Basic .NET、JScript .NET 或 Microsoft Visual C# .NET）重新创建该 functoid 的功能。  
  
2.  创建一个程序集以包含该新功能。  
  
3.  在全局程序集缓存 (GAC) 中注册该程序集。  
  
    > [!NOTE]
    >  若要在全局程序集缓存中注册程序集，程序集必须要具有强名称并且已签名。 有关注册程序集的详细信息，请参阅 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 合并集合中的“全局程序集缓存”。  
  
4.  创建的引用之间的映射中包含**脚本**functoid 和包含的重写的功能的程序集。  
  
5.  配置**脚本**属性**脚本**functoid。 此属性确定哪些脚本**脚本**functoid 调用在运行时。 此属性的值必须与自定义脚本的转换目标语言相匹配。 有关如何配置脚本属性的详细信息，请参阅[编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)。 另请参阅[脚本 Functoid](../core/scripting-functoid.md)。  
  
6.  生成 BizTalk 项目包含对地图**脚本**functoid。  
  
7.  验证和测试映射。  
  
## <a name="see-also"></a>另请参阅  
 [编辑 Functoid 属性和输入的参数](../core/editing-functoid-properties-and-input-parameters.md)   
 [“脚本编写”Functoid](../core/scripting-functoid.md)