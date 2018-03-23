---
title: 使用 BizTalk 编辑器命令 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e216ae5d-5bad-48ef-87d1-8aa8ee20179b
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1ae30305f5e23e99b5a0bc76cba9bfc7f451b03
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="use-biztalk-editor-commands"></a>使用 BizTalk 编辑器命令

## <a name="overview"></a>概述
BizTalk 编辑器将变为活动状态，它会添加菜单调用**BizTalk**到[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]shell。 通过此菜单可以访问 BizTalk 编辑器命令及其功能。 当 BizTalk 编辑器为活动状态， **BizTalk** 菜单提供特定于编辑 BizTalk 架构的命令。  
  
 此外以及在何处适用，BizTalk 编辑器使用的现有[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]具有明显 parallels 标准应用程序功能的命令的菜单项。 例如，BizTalk 编辑器处于活动状态时， **保存** 命令 **文件** 菜单将更改保存到当前正在编辑的架构。  
  
## <a name="commands-list"></a>命令列表
 下表对 BizTalk 编辑器内可在建立架构的过程中使用的命令进行了说明：  
  
|Command<br /><br /> （菜单位置）|Description|  
|------------------------------------|-----------------|  
|**打开架构**<br /><br /> (文件 &#124;打开 &#124;文件...）|打开 BizTalk 架构以便在 BizTalk 编辑器中进行编辑。<br /><br /> 通过在解决方案资源管理器中选定架构时出现的快捷菜单，或通过在解决方案资源管理器中双击相应的架构，也可执行此命令。|  
|**关闭架构**<br /><br /> (文件 &#124;关闭）|对当前架构关闭 BizTalk 编辑器，并提示您保存所有尚未保存的更改。<br /><br /> 通过使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中主编辑窗口右上角的标准“关闭”按钮，也可执行此命令。|  
|**新架构**<br /><br /> (项目 &#124;添加新建项...&#124;架构）|创建新的 BizTalk 架构以进行编辑，并打开 BizTalk 编辑器。<br /><br /> 此外可在解决方案资源管理器中的 BizTalk 项目的快捷菜单上 (添加 &#124;新的项）。|  
|**保存架构**<br /><br /> (文件 &#124;保存 schema.xsd）<br /><br /> (文件 &#124;保存为 schema.xsd.)<br /><br /> (文件 &#124;保存所有）|分别表示以当前编辑的 BizTalk 架构自己的名称保存架构，以新名称保存架构，或作为保存所有未保存更改的操作的一部分进行保存。|  
|**剪切、 复制、 粘贴节点**<br /><br /> (编辑 &#124;剪切、 编辑 &#124;复制、 编辑 &#124;粘贴）|允许 **架构** 移动和复制在架构中的节点树视图。<br /><br /> 如果适用，这些命令在选定节点的快捷菜单上可用，通过使用标准剪切、复制和粘贴快捷键（Ctrl+X、Ctrl+C 和 Ctrl+V）也可以执行这些命令。|  
|**删除节点**<br /><br /> (编辑 &#124;删除）<br /><br /> (BizTalk &#124;删除）|在架构树视图中删除当前选定的节点，并提示您进行确认。<br /><br /> 如果适用，通过选定节点的快捷菜单也可执行此命令。|  
|**查找节点**<br /><br /> (编辑 &#124;查找和替换 &#124;快速查找）|提供对架构树视图中的节点名称的搜索功能，这对于大型架构十分有用。|  
|**属性**<br /><br /> (视图 &#124;属性窗口中）<br /><br /> (BizTalk &#124;属性）|使用此命令可访问架构树视图节点的属性，以及更高级的对象（例如架构本身）。<br /><br /> 通过所选节点的快捷菜单也可执行此命令。|  
|**插入架构节点**<br /><br /> (BizTalk &#124;插入架构节点 &#124;*)|提供将各种不同类型的节点插入架构树视图的方法。 有关可以添加的节点的类型的详细信息，请参阅[BizTalk 表示形式的架构](../core/biztalk-representation-of-schemas.md)。<br /><br /> 如果适用，通过选定节点的快捷菜单也可执行这些命令。|  
|**将提升**<br /><br /> (BizTalk &#124;将提升 &#124;*)|提供升级属性的不同方法。<br /><br /> 通过所选节点的快捷菜单也可执行此命令。|  
|**展开架构节点**<br /><br /> (BizTalk &#124;展开架构节点）|在架构树视图中完全展开当前选定（并且至少部分折叠）的节点。<br /><br /> 如果适用，通过选定节点的快捷菜单也可执行此命令。|  
|**折叠架构节点**<br /><br /> (BizTalk &#124;折叠架构节点）|在架构树视图中折叠当前选定（并且至少部分展开）的节点。<br /><br /> 如果适用，通过选定节点的快捷菜单也可执行此命令。|  
|**刷新 XSD**<br /><br /> (BizTalk &#124;刷新 XSD）|刷新 XSD 视图，它可能被设置为不会自动刷新通过选择 **打开关闭自动刷新** XSD 视图下的复选框。<br /><br /> 此命令，还可以在快捷菜单，对于所选的节点中，并通过单击 **刷新** XSD 视图下。|  
|**重命名**<br /><br /> (BizTalk &#124;重命名）|允许 **记录**, ，**字段特性**, ，和 **Field 元素** 要重命名，就地情况下，架构树视图中的节点。<br /><br /> 此命令是等效于更改 **节点名称** 所选节点的属性。<br /><br /> 如果适用，通过选定节点的快捷菜单也可执行此命令。|  
|**BizTalk 编辑器选项**<br /><br /> (工具 &#124;选项 &#124;BizTalk 编辑器）|允许对确认对话框（打开或关闭）进行配置，以及调整字体和背景色。|  
  
 下表对解决方案资源管理器中选定架构的快捷菜单上的其他可用架构命令进行了说明：  
  
|架构命令|Description|  
|--------------------|-----------------|  
|**打开**|在 BizTalk 编辑器中打开选定的架构。|  
|**使用打开**|允许通过不同的 XSD 编辑器（包括 BizTalk 编辑器）打开选定的架构。|  
|**验证架构**|验证选定的架构。|  
|**验证实例**|验证指定的实例 **输入实例 Filename** Visual Studio 中的属性 **属性** 针对所选的架构的窗口。|  
|**生成实例**|将生成一个实例使用指定的文件名称的所选架构 **输出实例文件名** Visual Studio 中的属性 **属性** 窗口。<br /><br /> 如果没有为生成的输出实例指定任何名称，则使用默认文件名。 默认文件名是字符串“_output.xml”（位于 Documents and Settings 文件夹中临时文件夹的 _SchemaData 文件夹中）之前的架构文件名。|  
|**查看代码**|显示基础 XSD。|  
|**视图设计器**|在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] XML 架构设计器中打开架构。|  
|**从项目中排除**|从当前的 BizTalk 项目中删除当前选定的架构。<br /><br /> 使用 **添加现有项** 命令以重新添加之前已从当前的 BizTalk 项目中排除的架构。|  
|**剪切、 复制粘贴**|使用这些命令来执行标准[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的剪切、 复制和粘贴在 BizTalk 项目中的整个架构的行为。|  
|**删除**|永久删除当前选定的架构，并提示您进行确认。|  
|**重命名**|允许就地重命名当前选定的架构。|  
|**属性**|打开 Visual Studio **属性**  窗口对于当前所选的架构，在其中的某些架构属性可以检查和设置。 <br/><br/>**注意：**架构的其他属性都检查并在中设置[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]时选择架构属性窗口。 在中设置属性 **属性** 窗口是为其不同的值可能时有意义的相同的架构使用多个 BizTalk 项目中的这些属性。 <br /><br /> 有关设置架构属性和架构的属性的详细信息，请参阅[设置架构文件和架构项属性](../core/how-to-set-schema-file-and-schema-item-properties.md)和**架构文件属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk 编辑器](../core/using-biztalk-editor.md)