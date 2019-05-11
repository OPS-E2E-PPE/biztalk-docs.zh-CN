---
title: 使用 BizTalk 映射器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.grid
ms.assetid: 07c69603-ee79-44b2-80b1-6ae4e4c8fb4e
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bdefb8c35f817008d0727db82eaf0fe2b04b9fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401689"
---
# <a name="using-biztalk-mapper"></a>使用 BizTalk 映射器

## <a name="overview"></a>概述
BizTalk 映射器驻留在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]shell。 在 BizTalk 映射器功能的一些依赖的用户界面元素[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]shell。 例如，使用**文件**，**编辑**，并**视图**菜单正如您将在执行其他开发[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 提供了有关此通用功能的信息**帮助**菜单。  
  
 添加新映射到 BizTalk 项目中，打开现有的映射 （.btm 文件），或通过单击主其选项卡重新激活该映射，BizTalk 映射器将变为活动[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口。  
  
> [!NOTE]
>  BizTalk 映射器保存映射文件使用 utf-16 字符编码。  
>
>  生成操作时向 BizTalk 项目添加现有项目，请始终设置为**BtsCompile**。 即使在重命名现有项目，其生成操作设置为默认值**BtsCompile**。 因此，在添加或重命名现有项目时，你需要设置适当地根据是否想要或不生成该特殊项目的生成操作。  

## <a name="parts-of-the-biztalk-mapper"></a>BizTalk 映射器的各个部分  
 下图显示了 BizTalk 映射器中的各个部分[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
 ![BizTalk 映射器](../core/media/mapper-views.gif "Mapper_Views")  
  
 每个视图的功能如下所示：  
  
- **Visual Studio 映射器实用工具功能区。** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]映射器提供了显示映射器相关命令的实用工具功能区。 关联视图的源和目标架构，切换按钮来显示或隐藏所有作用域的链接，切换开关以启用自动滚动开还是关，若要进行平移映射器图面的按钮控件添加到功能区提供源架构信息、 切换按钮放大或缩小扩展，并在搜索文本框。 下图显示了您可以在网格页的顶部看到实用工具功能区。  
  
   ![映射器功能区](../core/media/mapper-ribbon.gif "Mapper_Ribbon")  
  
- **源架构树视图。** 此视图共享主[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑与目标架构树视图和网格视图窗口。  
  
   顾名思义，此视图将显示描述是映射的源实例消息的架构。 定义的映射的链接可引导的源架构树视图从网格视图，则从根本上讲，对目标架构树视图。  
  
   有关 BizTalk 架构在架构树视图中的表示方式的详细信息，请参阅[BizTalk 架构表示法](../core/biztalk-representation-of-schemas.md)。  
  
- **目标架构树视图。** 此视图共享主[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑与源架构树视图和网格视图窗口。  
  
   顾名思义，此视图将显示描述所映射的目标实例消息的架构。 定义的映射的链接可引导到目标架构树视图从网格视图中，并最终从源架构树视图中。  
  
   有关 BizTalk 架构在架构树视图中的表示方式的详细信息，请参阅[BizTalk 架构表示法](../core/biztalk-representation-of-schemas.md)。  
  
- **网格视图。** 此视图共享主[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑与源架构树视图和目标架构树视图中，使用左侧的源架构树视图和目标架构树视图右侧的窗口。  
  
   顾名思义，此视图播放的控制如何将源实例消息中的数据转换为符合目标架构的实例消息中的地图，其中包含的链接和 functoid 定义的关键角色。  
  
   网格视图中可以有多个层，我们称之为网格页面，从而允许您将复杂映射组织到映射的逻辑分支。 网格页通常使用比一次可显示更多的空间并且有多种有效方法在网格页内滚动。  
  
   目前您可使用此视图构建映射中。  
  
- **Visual Studio 工具箱窗口。** 此视图用于显示可供使用的 functoid，在 BizTalk 映射，并作为拖放操作以将 functoid 置于网格页的源。  
  
   显示在工具箱中的 functoid 根据类别进行组织。 有关可用的 functoid 的详细信息，请参阅[映射中的 Functoid](../core/functoids-in-maps.md)。 另请参阅**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 
  
- **Visual Studio 属性窗口。** 使用此视图中和其关联的对话框，可以查看和设置的链接和 functoid 创建为定义映射的属性。  
  
   在网格视图中的网格页中选择链接或 functoid，在源或目标架构树视图，选择 schema 节点或中选择映射**解决方案资源管理器**窗口; 该链接，functoid 的相应属性schema 节点或映射中出现**属性**窗口使用标准的 Visual Studio 约定。 例如，属性都分组到类别，并可以根据这些类别或按字母顺序显示。  
  
   有关不同的可用于链接、 functoid、 schema 节点或映射本身的属性集的详细信息，请参阅**映射属性参考**和**Schema Property Reference**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
- **Visual Studio 任务列表和输出窗口。** 使用这些视图以检查验证、 编译和测试 BizTalk 映射在很大程度相同的方式编译源代码时，使用这些视图和生成其他类型的项目的结果。  
  
  除了这些视图中，您可以交互与几个对话框。 在编辑诸如 functoid 的输入参数等复杂属性时，通常会打开这些对话框。  
  
  您通常使用 BizTalk 映射器结合使用解决方案资源管理器窗口。 例如，若要创建新的映射，请右键单击 BizTalk 项目中的**解决方案资源管理器**窗口中，单击**添加**，单击**添加新项**，然后使用**添加新项**对话框进行命名和创建新的映射。  
  
## <a name="next-steps"></a>后续步骤
  
-   [使用 BizTalk 映射器命令](../core/using-biztalk-mapper-commands.md)  
  
-   [使用网格页](../core/working-with-grid-pages.md)  
  
-   [如何管理视图](../core/how-to-manage-views.md)  
  
-   [如何自定义的颜色和字体在 BizTalk 映射器](../core/how-to-customize-colors-and-font-in-biztalk-mapper.md)  
  
-   [如何展开和折叠架构树](../core/how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees.md)  
  
-   [如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)  
  
-   [如何搜索映射项](../core/how-to-search-for-map-items.md)  
  
-   [使用 BizTalk 映射器中的增强功能](../core/using-enhanced-features-in-biztalk-mapper.md)  
  
-   [如何查看信息提示和工具提示](../core/how-to-view-infotip-and-tooltip.md)  
  
## <a name="see-also"></a>请参阅  
 [如何优化链接的显示](../core/how-to-optimize-the-display-of-links.md)