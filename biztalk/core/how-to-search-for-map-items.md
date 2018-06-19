---
title: 如何搜索映射项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.search
ms.assetid: 3dbb089a-6aa8-4921-a82d-81d3a193e933
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee61bccfae53a79d8fba6bd0aa5af2c537d98270
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255533"
---
# <a name="how-to-search-for-map-items"></a>如何搜索映射项
使用 BizTalk 映射器，可以搜索源架构、目标架构和网格图面中的项目。 本主题提供有关如何执行此操作的信息。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
## <a name="to-search-for-items"></a>若要搜索的项  
 选择要进行搜索的架构。 如果选择源架构，则 BizTalk 映射器将只在源架构中搜索和查找匹配项。 但是，可以同时选择源架构和目标架构。  
  
> [!NOTE]
>  若要确认所选内容，请查看架构或架构项目之前的标记。  
  
 ![搜索映射项](../core/media/searching-map-items.gif "Searching_map_items")  
  
 在**搜索**映射器实用程序功能区上的框中，键入你想要搜索的项的名称。 您可以搜索源架构或目标架构中节点名称中的字符串，以及名称、标签、注释、输入或 functoid 脚本中的字符串。  
  
 输入搜索字符串时，将突出显示符合搜索条件的对象。 你可以然后遍历搜索结果使用箭头键在键盘上或![在列表中向上移动](../core/media/move-up-button.gif "Move_up_button")和![列表中向下移动](../core/media/move-down-button.gif "Move_down_button")实用程序功能区上的图标。 如果搜索结果散布在所有三个视图中，则可以按照源架构、关系视图和目标架构的顺序遍历搜索结果。 后经过的搜索结果，你可以关闭搜索通过删除搜索字符串或通过单击 (![清除映射器搜索](../core/media/mapper-search-cancel.gif "Mapper_Search_Cancel")) 搜索字符串旁边的图标。  
  
> [!NOTE]
>  还可以按 Ctrl+M、Ctrl+J 或 Ctrl+M、Ctrl+K 分别向上或向下遍历搜索结果。 映射器的键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
> [!IMPORTANT]
>  如果关系视图的搜索结果未显示在单个映射视图中，则 BizTalk 映射器会在存在其他命中项的方向显示闪烁的箭头。 例如，顶部的箭头图标 (![其他搜索结果的方向](../core/media/mapper-search-direction.gif "Mapper_Search_Direction")) 表示没有其他搜索结果，可通过向上滚动查看。 同样，如果不同的映射页上都有搜索结果，则这些页的页选项卡将以黄色突出显示。 当将鼠标移动到突出显示的页上时，工具提示会显示该页上的搜索匹配项数。 状态栏会显示搜索结果。  
  
 ![状态栏显示搜索结果](../core/media/searching-map-items-statusbar.jpg "Searching_map_items_statusbar")  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk 映射程序](../core/using-biztalk-mapper.md)