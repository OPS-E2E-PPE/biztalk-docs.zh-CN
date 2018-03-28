---
title: 如何保存，重命名，并关闭架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65e15d9e-40ae-4850-9c13-88033cb3b3bb
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a295bacf263e3ecad9a9aa081fb0d5d3be2f635
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-save-rename-and-close-schemas"></a>如何保存，重命名，并关闭架构
在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，架构是具有 .xsd 扩展名的 XML 架构定义 (XSD) 语言文件并驻留在文件系统中。 在使用 BizTalk 编辑器开发架构时，会经常需要保存和关闭架构文件，有时还可能需要重命名这些文件。 本主题将介绍执行这些基本操作所需的步骤。  
  
### <a name="to-save-a-schema"></a>若要将架构保存  
  
1.  如果需要，可以通过单击 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中主编辑窗口顶部相应的选项卡，为要保存的架构激活 BizTalk 编辑器。  
  
2.  上**文件**菜单上，单击 * * 保存 *\<名称的架构\>* * *。  
  
     如尚未保存对架构所做的更改，则显示在主编辑窗口顶部的选项卡上的该架构的名称将不再以星号 (*) 结尾，这表示更改未保存。  
  
> [!NOTE]
>  你可以通过单击保存以新名称的架构**保存*\<名称的架构\>*作为**上**文件**菜单。  
  
> [!NOTE]
>  你可以将架构保存作为一部分保存在项目中的所有更改的项，通过单击 **保存所有** 上 **文件** 菜单。  
  
#### <a name="to-rename-a-schema"></a>若要重命名架构  
  
1.  在解决方案资源管理器，右键单击你想要重命名，然后单击架构 **重命名**。  
  
2.  在解决方案资源管理器中显示在该架构位置的编辑框内，为该架构键入新名称，或更改其现有名称，然后按 Enter。  
  
> [!NOTE]
>  你可能还想要更改 **类型名称** 重命名时的架构。 你更改 **类型名称** 通过选择 **架构** 在解决方案资源管理器并输入中的新名称 **类型名称** 属性窗口中。  
  
> [!IMPORTANT]
>  不应对正在由其他架构使用的架构进行重命名。 其中包括已由其他架构包括、导入或重新定义的架构，以及已为其建立升级的属性架构。 如果进行了重命名，则正在使用的架构将无法找到另外一个架构，因为它所包含的名称已不准确。  
  
> [!NOTE]
>  对于诸如架构文件之类的项目成员文件，如果选择某些名称作为其名称，可能会由于与 C# 保留字、.NET Framework 类型和命名空间名称（例如“System”）之间的冲突而导致以后出现编译错误。 例如以下架构名称：schema.xsd、XmlContent 和 RootNodes。 这是因为 **类型名称** 属性默认为的基 （非扩展） 部分 **Filename** 属性。 可以通过显式更改的值来解决这种类型的编译错误 **类型名称** 某事不冲突的属性。  
  
#### <a name="to-close-a-schema"></a>若要关闭架构  
  
1.  如有必要，激活要关闭通过单击相应的选项卡在 Microsoft 中的主编辑窗口顶部的架构的 BizTalk 编辑器[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
2.  在 **“文件”** 菜单上，单击 **“关闭”**。  
  
     对于已关闭的架构，相应的 BizTalk 编辑器也将关闭。  
  
## <a name="see-also"></a>另请参阅  
 [管理项目中的架构](../core/managing-schemas-within-projects.md)