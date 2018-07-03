---
title: 迁移 Functoid |Microsoft Docs
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
ms.openlocfilehash: 3b01f37551b9d4c1aef13786be7094504f8cee08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020499"
---
# <a name="migrating-functoids"></a>迁移 Functoid
映射从以前版本的 BizTalk Server 迁移到 BizTalk Server 时，在映射中包含的所有 functoid 也会被都迁移。 如果不包括迁移的 functoid**脚本**functoid 所需任何其他迁移任务。 但是如果映射中包含**脚本**functoid 或自定义 functoid，您可能必须执行一些其他步骤。  
  
 在以前版本的 BizTalk Server 中，所有自定义脚本随附**脚本**functoid 编写内联。 也就是说，在创建该 functoid 后，该 functoid 在运行时调用的所有脚本都与该 functoid 一起存储。 如果你想要使用其他 functoid 使用的同一个脚本，您可以复制并粘贴它从一个**脚本**functoid 到另一个，也重写从零开始的脚本。  
  
 在迁移映射时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将复制随所包含 functoid 一起提供的现有内联脚本。 但是，并非所有的脚本可能正常工作。 BizTalk Server 使用 Visual Basic.NET 和 JScript.NET，而不是 VBScript 和 JScript 早期版本中使用。 这些语言的 .NET 版本在语法上有一些更改。  
  
> [!NOTE]
>  确保测试你**脚本**迁移后的 functoid。  
  
 你将需要重写自定义 functoid。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 要求使用.NET framework 自定义 functoid。 因为，在该版本中无法使用基于 COM 的早期版本自定义 functoid。 您可以重新编写自定义 functoid，以使用 .NET Framework。 自定义 functoid 示例代码，请参阅[自定义 Functoid （BizTalk Server 示例）](../core/custom-functoid-biztalk-server-sample.md)。  
  
 一种替代方法是将自定义 functoid 的功能封装在外部程序集并调用通过此程序集**脚本**functoid。 以下部分将介绍此过程。  
  
### <a name="to-migrate-your-custom-functoids"></a>迁移自定义 functoid  
  
1. 使用 .NET 语言（如 Microsoft Visual Basic .NET、JScript .NET 或 Microsoft Visual C# .NET）重新创建该 functoid 的功能。  
  
2. 创建一个程序集以包含该新功能。  
  
3. 在全局程序集缓存 (GAC) 中注册该程序集。  
  
   > [!NOTE]
   >  若要在全局程序集缓存中注册程序集，程序集必须要具有强名称并且已签名。 有关注册程序集的详细信息，请参阅 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 合并集合中的“全局程序集缓存”。  
  
4. 创建之间的映射中包含的引用**脚本**functoid 和包含重写的功能的程序集。  
  
5. 配置**脚本**属性**脚本**functoid。 此属性确定哪些脚本**脚本**functoid 在运行时调用。 此属性的值必须与自定义脚本的转换目标语言相匹配。 有关如何配置脚本属性的详细信息，请参阅[编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)。 另请参阅[脚本 Functoid](../core/scripting-functoid.md)。  
  
6. 生成 BizTalk 项目包含对地图**脚本**functoid。  
  
7. 验证和测试映射。  
  
## <a name="see-also"></a>请参阅  
 [编辑 Functoid 属性和输入的参数](../core/editing-functoid-properties-and-input-parameters.md)   
 [“脚本编写”Functoid](../core/scripting-functoid.md)