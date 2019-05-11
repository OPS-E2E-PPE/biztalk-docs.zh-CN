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
ms.openlocfilehash: dc93b7bfd5e6bfb2097e3f190003b63e093b8e64
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394447"
---
# <a name="migrating-functoids"></a>迁移 Functoid
映射从以前版本的 BizTalk Server 迁移到 BizTalk Server 时，在映射中包含的所有 functoid 也会被都迁移。 如果不包括迁移的 functoid**脚本**functoid 所需任何其他迁移任务。 但是如果映射中包含**脚本**functoid 或自定义 functoid，您可能必须执行一些其他步骤。  
  
 在以前版本的 BizTalk Server 中，所有自定义脚本随附**脚本**functoid 编写内联。 也就是说时创建该 functoid 后，提取 functoid 在运行时调用的所有脚本与该 functoid 一起都存储。 如果你想要使用其他 functoid 使用的同一个脚本，您可以复制并粘贴它从一个**脚本**functoid 到另一个，也重写从零开始的脚本。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 迁移映射时，如果现有的 functoid 的内联脚本的副本。 但是，并非所有的脚本可能正常工作。 BizTalk Server 使用 Visual Basic.NET 和 JScript.NET，而不是 VBScript 和 JScript 早期版本中使用。 .NET 版本的语言在语法中包括一些更改。  
  
> [!NOTE]
>  确保测试你**脚本**迁移后的 functoid。  
  
 你将需要重写自定义 functoid。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 要求使用.NET framework 自定义 functoid。 它不能使用较旧的、 基于 COM 的自定义 functoid。 可以重写自定义 functoid 以使用.NET framework。 自定义 functoid 示例代码，请参阅[自定义 Functoid （BizTalk Server 示例）](../core/custom-functoid-biztalk-server-sample.md)。  
  
 一种替代方法是将自定义 functoid 的功能封装在外部程序集并调用通过此程序集**脚本**functoid。 以下部分介绍了此过程。  
  
### <a name="to-migrate-your-custom-functoids"></a>若要迁移自定义 functoid  
  
1. 重新创建该 functoid 的.NET 语言，如 Microsoft Visual Basic.NET、 JScript.NET 或 Microsoft Visual C#.NET 功能。  
  
2. 创建程序集以包含新功能。  
  
3. 在全局程序集缓存 (GAC) 中注册该程序集。  
  
   > [!NOTE]
   >  若要在全局程序集缓存中注册程序集，它们必须是强名称并且已签名。 有关注册程序集的详细信息，请参阅"全局程序集缓存"中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]组合集。  
  
4. 创建之间的映射中包含的引用**脚本**functoid 和包含重写的功能的程序集。  
  
5. 配置**脚本**属性**脚本**functoid。 此属性确定哪些脚本**脚本**functoid 在运行时调用。 必须匹配的转换自定义脚本的语言为此属性的值。 有关如何配置脚本属性的详细信息，请参阅[编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)。 另请参阅[脚本 Functoid](../core/scripting-functoid.md)。  
  
6. 生成 BizTalk 项目包含对地图**脚本**functoid。  
  
7. 验证和测试映射。  
  
## <a name="see-also"></a>请参阅  
 [编辑 Functoid 属性和输入的参数](../core/editing-functoid-properties-and-input-parameters.md)   
 [“脚本编写”Functoid](../core/scripting-functoid.md)