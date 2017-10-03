---
title: "使用 BizTalk 映射程序命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 34fea0fb-0609-4571-be49-6ee3f03afe2a
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5fd32d865bd08fe1b8b8e7929f313626be3e662
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-mapper-commands"></a>使用 BizTalk 映射程序命令
当 BizTalkMapper 变为活动状态时，它将添加菜单调用**BizTalk**到 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell。 通过此菜单可以访问 BizTalk 映射器命令及其功能。 当 BizTalk 映射程序处于活动状态， **BizTalk**菜单提供特定于编辑 BizTalk 映射的命令。  
  
 BizTalk 映射程序 （如果适用），使用现有[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]具有明显 parallels 标准应用程序功能的命令的菜单项。 例如，BizTalk 映射程序处于活动状态时，**保存**命令**文件**菜单将更改保存到当前正在编辑的映射。  
  
 下表对 BizTalk 映射器内可在建立映射的过程中使用的命令进行了说明：  
  
|Command<br /><br /> （菜单位置，如果有的话）|Description|  
|--------------------------------------------|-----------------|  
|**打开映射**<br /><br /> (文件 &#124;打开 &#124;文件...）|打开 BizTalk 映射以便在 BizTalk 映射器中进行编辑。<br /><br /> 通过在解决方案资源管理器中选定映射时出现的快捷菜单，或通过在解决方案资源管理器中双击相应的映射，也可执行此命令。|  
|**关闭映射**<br /><br /> (文件 &#124;关闭）|对当前映射关闭 BizTalk 映射器，并提示您保存所有尚未保存的更改。<br /><br /> 也可通过使用标准关闭 ([**X**]) 中的主编辑窗口右上角按钮[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。|  
|**新的映射**<br /><br /> (项目 &#124;添加 &#124;新建项...&#124;Map)|创建新的 BizTalk 映射以进行编辑，并打开 BizTalk 映射器。<br /><br /> 选择中的映射模板**添加新项**对话框。<br /><br /> 此外可在解决方案资源管理器中的 BizTalk 项目的快捷菜单上 (添加 &#124;新项 &#124;映射）。|  
|**打开源架构**<br /><br /> (*源的新的映射架构树视图中*)|允许在使用新图中选择的源架构**BizTalk 类型选取器**对话框。|  
|**打开目标架构**<br /><br /> (*目标的新的映射架构树视图中*)|允许在使用新图中选择的目标架构**BizTalk 类型选取器**对话框。|  
|**保存代码图**<br /><br /> (文件 &#124;保存 map.btm）<br /><br /> (文件 &#124;保存为 map.btm。..)<br /><br /> (文件 &#124;保存所有）|分别表示以当前编辑的 BizTalk 映射自己的名称保存映射，以新名称保存映射，或作为保存所有未保存更改的操作的一部分进行保存。|  
|**创建链接**<br /><br /> *（拖放仅）*|在源架构和目标架构的树视图中的 schema 节点之间或网格页中的 functoid 之间创建链接。<br /><br /> 可以通过以下方法创建链接：<br /><br /> 拖动架构节点到另一个架构树中的另一个架构节点或 functoid。<br />拖动 functoid 到架构节点或移到另一个 functoid。<br /><br /> 通过沿任一方向进行拖动，均可创建链接；换而言之，可以从链接的源（左端）或目标（右端）开始。<br /><br /> 可通过将链接的一个终结点从一个节点或 functoid 拖动到另一个节点或 functoid 来替换链接。 有关详细信息，请参阅[如何创建链接](../core/how-to-create-links.md)。|  
|**添加 Functoid**<br /><br /> *（拖放仅）*|向显示的网格页添加 functoid。<br /><br /> 你可以通过从选项卡中拖动 functoid 添加到网格页 functoid[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]对应于 functoid 的类别的工具箱。|  
|**删除链接**和**删除 Functoid**<br /><br /> (编辑 &#124;删除）<br /><br /> (BizTalk &#124;删除）|在显示的网格页中删除当前选定的链接或 functoid，并提示您进行确认。<br /><br /> 如果适用，通过选定的链接或 functoid 的快捷菜单也可执行此命令。|  
|**查找架构节点**<br /><br /> (编辑 &#124;查找和替换 &#124;查找）|在架构树视图中，对于大型架构可能很有用的节点名称提供搜索功能。|  
|**属性**<br /><br /> (视图 &#124;属性窗口中）<br /><br /> (BizTalk &#124;属性）|使用此命令可访问链接、functoid、源架构和目标架构的树视图节点的属性，以及更高级的对象（例如映射本身）。<br /><br /> 通过选定的链接或 functoid 的快捷菜单也可执行此命令，但对于架构树中的节点不适用。 按 F4 也可以显示“属性”窗口。|  
|**添加页**<br /><br /> (BizTalk &#124;添加页）|向网格视图添加新的网格页（也称为层）。<br /><br /> 通过网格页选项卡的快捷菜单也可执行此命令。|  
|**删除页面**<br /><br /> (BizTalk &#124;删除页）|删除显示的网格页（也称为层），并提示您进行确认。<br /><br /> 通过网格页选项卡的快捷菜单也可执行此命令。|  
*对页重新排序**<br /><br /> (BizTalk &#124;对页重新排序）|允许重新排序的网格页面，也称为层，使用**重新排序页**对话框。<br /><br /> 通过网格页选项卡的快捷菜单也可执行此命令。|  
|**重命名页面**<br /><br /> (BizTalk &#124;重命名页）|允许重命名显示的网格页（也称为层）。<br /><br /> 通过网格页选项卡的快捷菜单也可执行此命令。|  
|**展开树节点**<br /><br /> (BizTalk &#124;展开树节点）|完全将展开的当前所选 （和至少部分折叠）**架构**，**组**，或**记录**源或目标架构树视图中的节点。<br /><br /> 如果适用，通过选定节点的快捷菜单也可执行此命令。 **注意：**在大型和复杂架构中，当你单击**展开树节点**包含复杂类型的节点，架构中的某些节点中可能会保留折叠状态。 其原因在于，递归进程只展开当前视图中出现的第一个给定复杂类型。 您必须手动展开之后出现的同一类型。 设计此行为是为了优化在复杂的大型架构中展开节点时的性能。|  
|**折叠树节点**<br /><br /> (BizTalk &#124;折叠树节点）|折叠当前所选 （及其中至少部分展开）**架构**，**组**，或**记录**源或目标架构树视图中的节点。<br /><br /> 如果适用，通过选定节点的快捷菜单也可执行此命令。|  
|**网格预览**<br /><br /> (BizTalk &#124;网格预览版）|允许快速而准确地在中显示的网格页使用滚动**网格预览**对话框。<br /><br /> 通过网格页的快捷菜单也可执行此命令。|  
|**将架构**<br /><br /> (BizTalk &#124;将架构）|允许的源或目标架构使用的替换**BizTalk 类型选取器**对话框。<br /><br /> 通过源架构和目标架构的树视图的快捷菜单也可执行此命令。|  
|**BizTalk 映射程序选项**<br /><br /> (工具 &#124;选项 &#124;BizTalk 映射程序）|允许对网格视图中的不同颜色（包括选定内容、链接、网格和背景的颜色）进行配置。 使用此命令也可以更改 schema 节点显示中使用的字体。|  
  
 下表对解决方案资源管理器中选定映射的快捷菜单上的其他可用映射命令进行了说明：  
  
|架构命令|Description|  
|--------------------|-----------------|  
|**打开**|在 BizTalk 映射器中打开选定的映射。<br /><br /> 双击某个映射也会在 BizTalk 映射器中将其打开。|  
|**使用打开**|允许通过不同的 XML 编辑器（包括 BizTalk 映射器）打开选定的映射。|  
|**测试映射**|测试选定的映射。|  
|**验证映射**|验证映射。|  
|**调试映射**|如果成功编译映射，则调试映射将启动 XSLT 调试程序。 它允许您逐步进行 XLST 的生成，与其他任何 Visual Studio 调试器类似。|  
|**从项目中排除**|从当前的 BizTalk 项目中删除当前选定的映射。<br /><br /> 使用**添加 &#124;现有项**命令来重新添加之前已从当前的 BizTalk 项目中排除的映射。|  
|**剪切、 复制粘贴**|使用这些命令来执行标准[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的剪切、 复制和粘贴在 BizTalk 项目中的整个地图的行为。<br /><br /> 您还可以剪切、复制、粘贴映射项目，如链接和/或 functoid。 有关详细信息，请参阅[如何复制、 剪切和粘贴 Functoid](../core/how-to-copy-cut-and-paste-a-functoid.md)和[如何复制、 剪切、 粘贴链接和 Functoid](../core/how-to-copy-cut-and-paste-links-and-functoids.md)。|  
|**删除**|永久删除当前选定的映射，并提示您进行确认。|  
|**重命名**|允许就地重命名当前选定的映射。|  
|**属性**|在“属性”窗口中显示当前所选映射的属性。|  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk 映射程序键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)