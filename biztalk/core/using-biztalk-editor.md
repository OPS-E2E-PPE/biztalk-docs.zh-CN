---
title: 使用 BizTalk 编辑器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22021272-f028-4db3-ad8a-fb89a5340910
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f1f85fa69e07f252aa732d868353609ed065fbf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007158"
---
# <a name="using-biztalk-editor"></a>使用 BizTalk 编辑器

## <a name="overview"></a>概述
BizTalk 编辑器驻留在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 外壳程序中。 某些功能在 BizTalk 编辑器中依赖于中的现有用户界面元素[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]shell。 例如，使用**文件**，**编辑**，并**视图**菜单正如您将在执行其他开发[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 提供了有关此通用功能的信息**帮助**菜单。  
  
 在 BizTalk 项目中，打开现有的架构 （.xsd 文件） 时向 BizTalk 项目，添加新架构时，或通过单击主其选项卡重新激活架构时，BizTalk 编辑器变为活动状态[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口。  
  
> [!NOTE]
>  BizTalk 编辑器使用 utf-16 字符编码保存架构文件。  

## <a name="views"></a>视图  
 下图显示了在 Microsoft 的各种视图[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]外壳程序是在 BizTalk 编辑器的一部分。  
  
 ![BizTalk 项目的不同部分](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")  
  
 BizTalk 编辑器包含 Microsoft 中的以下视图[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]shell 和其关联的对话框：  
  
- **架构树。** 此视图位于主左侧[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口。 通过建立可描述架构所定义消息的结构的树结构，目前可以使用此视图构造架构。 有关 BizTalk 架构在架构树视图中的表示方式的详细信息，请参阅[BizTalk 架构表示法](../core/biztalk-representation-of-schemas.md)。  
  
- **XSD 视图。** 此视图位于主右侧[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口。 它显示了表示架构树视图中要构造的架构的 XML 架构定义 (XSD) 语言结构。 此视图是只读的，其用途是帮助您习惯要创建的架构的 XSD 语法。 根据需要，您可以调整视图拆分器，以便恰好只有 XSD 视图可见。  
  
- **解决方案资源管理器。** 此视图位于右侧的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]shell。 它显示 BizTalk 项目及其包含的各项。 使用解决方案资源管理器可以向项目添加新架构和现有架构，并且可以打开已属于该项目的架构。 例如，若要创建新的架构，右键单击 BizTalk 项目在解决方案资源管理器窗口中的，单击**外**，单击**新项**，然后使用**添加新项**对话框框进行命名和创建新的架构。  
  
- [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]  **属性窗口。** 使用此视图可以检查和设置大多数架构和节点属性。 在架构树视图中选择节点时，或在“解决方案资源管理器”窗口中选择架构时，该节点或架构的相应属性将使用标准的 Visual Studio 范例显示在“属性”窗口中。 例如，属性将分组为不同的类别，您可以按这些类别或按字母顺序显示属性。 有关不同的不同类型的节点，则此架构中，选择时可用的属性集的详细信息，请参阅**Schema Property Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
  除了这些视图外，你还可以与几个对话框交互。 在编辑诸如集合等复杂属性时，通常会打开这些对话框。  
  
  本部分提供了有关 BizTalk 编辑器中可用的视图、命令和快捷键的信息。  
  
## <a name="next-steps"></a>后续步骤 
  
-   [如何管理架构树视图](../core/how-to-manage-the-schema-tree-view.md)  
  
-   [如何管理 XSD 视图](../core/how-to-manage-the-xsd-view.md)  
  
-   [如何管理属性窗口](../core/how-to-manage-the-properties-window.md)  
  
-   [如何管理其他 Visual Studio Windows](../core/how-to-manage-other-visual-studio-windows.md)  
  
-   [使用 BizTalk 编辑器命令](../core/using-biztalk-editor-commands.md)  
  
-   [处理大型架构](../core/working-with-large-schemas.md)