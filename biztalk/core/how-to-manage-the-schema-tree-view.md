---
title: 如何管理架构树视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 97fb7a88-e38a-4abb-93bc-a5be1bd091e6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d41e2b61b4f0e1792a76b53ec1c9c070373850a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336706"
---
# <a name="how-to-manage-the-schema-tree-view"></a>如何管理架构树视图
对于架构树视图中的管理任务可以分为四个类别： 更改其大小、 更改其背景色和字体、 更改其使用的警告对话框，并展开和折叠其树状结构。 本主题提供有关以下各项任务的分步说明。  
  
### <a name="to-make-the-schema-tree-view-taller-or-shorter"></a>若要使架构树视图更高或更短  
  
1. 将鼠标指针移动到 Microsoft 的下边缘[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]主编辑窗口，其中显示架构树视图的并行与 XSD 视图中，直到光标更改为标准的窗口垂直调整图标。  
  
2. 单击并按住鼠标左键并向上或向下拖动窗口边缘。  
  
    通过垂直调整整个主编辑窗口，您已垂直调整架构树视图。  
  
### <a name="to-make-the-schema-tree-view-wider-or-more-narrow"></a>若要使架构树视图更宽或更窄  
  
1. 将鼠标指针移动到中的窗格分隔符[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]主编辑窗口，将架构树视图与 XSD 视图中，直到光标更改为标准的窗口水平调整图标。  
  
2. 单击并按住鼠标左键并拖动窗格边缘向左 （更窄） 或向右 （更宽）。  
  
    通过更改主编辑窗口的量为架构树视图中，相对于 XSD 视图，您已水平调整架构树视图。  
  
    此外可以通过水平调整整个主编辑窗口更宽或窄在架构树视图。  
  
### <a name="to-change-the-background-color-andor-font-used-by-the-schema-tree-view"></a>若要更改的背景色和/或使用架构树视图字体  
  
1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的 **“工具”** 菜单中，单击 **“选项”**。  
  
2. 在中**选项**对话框中，单击 BizTalk 编辑器文件夹，并如有必要，展开**架构显示**类别单击加号 （+） 图标。  
  
3. 通过使用下拉颜色选取器来更改背景色和/或字体和/或**字体**与关联的对话框中**架构树背景色**和**架构树字体**属性，分别。  
  
    访问**字体**对话框中，使用旁边的省略号 (**...**) 按钮位于右侧**架构树字体**属性值框。  
  
### <a name="to-change-the-warning-dialogs-used-when-working-in-the-schema-tree-view"></a>若要更改在架构树视图中工作时使用的警告对话框  
  
1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的 **“工具”** 菜单中，单击 **“选项”**。  
  
2. 在中**选项**对话框中，单击**BizTalk 编辑器**文件夹，如有必要，展开**编辑选项**部分，单击加号 （+） 图标。  
  
3. 设置为以下属性的任何 **，则返回 True**或**False**通过使用访问相应的属性值框右边缘的下拉列表。  
  
   > [!NOTE]
   >  该值 **，则返回 True**为默认值为所有三个警告对话框选项。  
  
   |属性|Description|  
   |--------------|-----------------|  
   |**显示损坏结构警告对话框**|如果设置为 **，则返回 True**，架构结构被破坏，并允许您取消破坏性操作之前将显示一个警告对话框。|  
   |**显示编码警告对话框**|如果设置为 **，则返回 True**，当你键入的节点名称不会在 XML 中有效编码，以允许您取消命名操作，或继续该名称进行编码时显示一个对话框。|  
   |**显示无效插入对话框**|如果设置为 **，则返回 True**，显示某些节点插入错误的警告对话框，并提供了有关如何继续的选项。 可能的节点插入错误包括：<br /><br /> -你已创建了重复**字段属性**具有相同名称和相同父节点的节点。<br />-你已创建了重复**记录**节点使用相同的名称和相同父节点，但使用不同的基础类型。|  
  
### <a name="to-completely-expand-all-or-part-of-the-schema-tree"></a>若要完全展开整个或部分架构树  
  
-   选择要在其下以完全展开架构树的节点。  
  
     所选的节点必须是节点带有加号 （+） 或减号 （-） 图标旁边。  
  
     上**BizTalk**菜单中，或在该节点的快捷菜单，单击**展开 Schema 节点**。 下面所选节点的所有节点均将完全都展开。 如果所选节点的下级架构树已经完全展开，**展开 Schema 节点**菜单项将呈灰色。  
  
    > [!NOTE]
    >  在大型和复杂架构中，单击时**展开 Schema 节点**上包含复杂类型的节点，该架构中的某些节点可能仍会保持折叠状态。 这是因为递归过程扩展仅一个给定复杂类型的第一个匹配项。 您必须手动展开之后出现相同的类型。 此行为用于大型和复杂的架构中展开节点时优化性能。  
  
### <a name="to-completely-collapse-all-or-part-of-the-schema-tree"></a>若要完全折叠整个或部分架构树  
  
1.  选择要在其下完全折叠架构树的节点。  
  
     所选的节点必须是节点带有加号 （+） 或减号 （-） 图标旁边。  
  
2.  上**BizTalk**菜单中，或在该节点的快捷菜单，单击**折叠 Schema 节点**。  
  
     下面所选节点的所有节点均将完全都折叠。  
  
    > [!NOTE]
    >  如果所选节点的下级架构树已经完全折叠，**折叠 Schema 节点**菜单项将呈灰色。  
  
    > [!NOTE]
    >  此操作不会记住单个展开和折叠所选节点的下级节点的设置。 换而言之，重新展开折叠的节点，以前的各个设置都将丢失，必须展开架构树时点节点的节点或其完全展开。  
  
### <a name="to-expand-a-node-of-the-schema-tree"></a>若要展开架构树的节点  
  
-   单击加号 （+） 您想要扩展的节点旁边的图标。  
  
    > [!NOTE]
    >  展开所选的节点。 及其子代节点是展开还是折叠取决于所选的节点的折叠方式以及其以前的展开和折叠设置。  
  
### <a name="to-collapse-a-node-of-the-schema-tree"></a>若要折叠架构树的节点  
  
-   单击减号 （-） 想要折叠的节点旁边的图标。  
  
    > [!NOTE]
    >  所选的节点处于折叠状态。  
  
    > [!NOTE]
    >  此操作将记住单个展开和折叠所选节点的下级节点的设置。 换而言之，当您重新展开折叠的节点通过使用加号 （+） 图标，以前的各个设置不会丢失和下级架构树将恢复为以前的展开/折叠状态。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 编辑器](../core/using-biztalk-editor.md)