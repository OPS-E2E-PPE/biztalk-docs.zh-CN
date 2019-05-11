---
title: 如何复制、 剪切和粘贴 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 825847e4-87db-4b40-8e5d-5b5b1c79c6de
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53fbd0d8c5a4a72263b6abf0eb3918d130cf53fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340139"
---
# <a name="how-to-copy-cut-and-paste-a-functoid"></a>如何复制、 剪切和粘贴 Functoid
在 BizTalk 映射器中的复制/剪切/粘贴功能使 functoid 可重复使用。 在映射中，可以复制、 剪切和粘贴一个或多个 functoid 从一个网格页到另一个。 本主题提供执行这些操作的分步说明。  
  
 当你想要重复使用 functoid 时，可以使用复制/粘贴功能。 并且，当你想要从现有位置删除 functoid 并将其移到新位置，可以使用剪切/粘贴功能。  
  
> [!IMPORTANT]
>  如果您选择复制 functoid、 functoid、 其标签、 注释和输入的常数，以及占位符索引会复制。 同样，当您选择剪切 functoid、 functoid、 其标签、 注释，常量输入，以及占位符索引都会被剪切。 但是，当您粘贴 （在选择剪切） 之后所选内容，只有该 functoid 保留和删除孤立的链接。 标签、 注释、 输入的常数和占位符索引不会保留。  
  
 如果您只选择 functoid，或者链接到另一个 functoid 或架构节点，只有该 functoid 将剪切或复制，不包括这些链接。 如果剪切 functoid 链接到其他映射中 functoid 或架构节点，会删除指向这个剪切的 functoid。  
  
 您可以复制/剪切 functoid 从：  
  
- 映射的同一网格页中  
  
- 到相同的映射中另一个网格页  
  
- 到另一个 Visual Studio 的一个实例  
  
  可以撤消或重做剪切和粘贴操作。 有关详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-copy-and-paste-a-functoid"></a>若要复制和粘贴 functoid  
  
1.  在解决方案资源管理器，打开 BizTalk 项目中，，然后双击要打开 BizTalk 映射器中的映射。  
  
2.  选择你想要复制的 functoid。 若要选择多个 functoid，单击一个 functoid，按住 CTRL 键，再单击其他 functoid。  
  
    > [!NOTE]
    >  "功能区选择"操作可用于选择多个链接和/或 functoid。 有关详细信息，请参阅[如何选择多个链接和 Functoid](../core/how-to-select-multiple-links-and-functoids.md)。  
  
3.  右键单击所选内容，然后依次**复制**。 或者，您可以单击**副本**从 Visual Studio**编辑**菜单或键盘上的按 CTRL + C。  
  
    > [!NOTE]
    >  键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
4.  将光标置于想要粘贴 functoid。  
  
5.  在网格页上，右键单击，然后单击**粘贴**。 或者，您可以单击**粘贴**从 Visual Studio**编辑**菜单或键盘上的按 CTRL + V。 所选的 functoid 或 functoid 组的副本会显示在新位置。  
  
### <a name="to-cut-and-paste-a-functoid"></a>若要剪切和粘贴 functoid  
  
1.  在解决方案资源管理器，打开 BizTalk 项目中，，然后双击要打开 BizTalk 映射器中的映射。  
  
2.  选择你想要剪切的 functoid。 若要选择多个 functoid，单击一个 functoid，按住 CTRL 键，再单击其他 functoid。  
  
3.  右键单击所选内容，然后依次**剪切**。 或者，您可以单击**剪切**从 Visual Studio**编辑**菜单或键盘上的按 CTRL + X。  
  
    > [!NOTE]
    >  键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
4.  将光标置于想要粘贴 functoid。  
  
5.  在网格页上，右键单击，然后单击**粘贴**。 或者，您可以单击**粘贴**从 Visual Studio**编辑**菜单或键盘上的按 CTRL + V。 所选的 functoid 组从现有位置删除，并出现在新位置。  
  
## <a name="see-also"></a>请参阅  
 [使用 Functoid 创建更复杂的映射](../core/using-functoids-to-create-more-complex-mappings.md)