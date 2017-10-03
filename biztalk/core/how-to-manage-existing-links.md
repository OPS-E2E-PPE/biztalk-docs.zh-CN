---
title: "如何管理现有链接 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0db213b9-df84-4ebd-a59f-7691774d5031
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2e61bc8c7fbf015eba28666c63dbeabf57a39e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-existing-links"></a>如何管理现有链接
有时候您可能需要更改链接的源或目标，命名或重命名链接，或删除链接。 本主题为执行以上类型的链接操作提供了分步说明。  
  
### <a name="to-change-the-source-or-destination-of-a-link"></a>更改链接的源或目标  
  
1.  在 BizTalk 映射器的网格页上，单击某个链接以选择该链接。  
  
     网格页中所选链接的终结点将突出显示。  
  
2.  将该链接的终结点拖至要连接的新 schema 节点或 functoid。  
  
     拖动终结点时，光标将变为十字线。 如果指向无法接受链接的 schema 节点或 functoid（或其他对象），光标将变为带有贯穿线的圆形。  
  
    > [!IMPORTANT]
    >  如果具有两个或多个连接到某个 functoid 的输入链接，并将这些输入链接中的一个或多个重定向到源架构中的其他节点或其他 functoid，则可能不会保留原始 functoid 的输入参数顺序。　 使用**配置\<Functoid > Functoid**对话框查看生成的输入参数的顺序并对其重新排序，如有必要。 有关重新排序 functoid 的输入的参数的详细信息，请参阅[编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)。  
  
### <a name="to-setedit-the-label-of-a-link"></a>设置/编辑链接的标签的步骤  
  
1.  在 BizTalk 映射器的网格页上，单击某个链接以选择该链接。  
  
     网格页中所选链接的终结点将突出显示。  
  
2.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，提供链接时使用的 （新） 名称**标签**属性。  
  
### <a name="to-delete-a-link"></a>删除链接  
  
1.  在 BizTalk 映射器的网格页上，单击某个链接以选择该链接。  
  
     网格页中所选链接的终结点将突出显示。  
  
2.  上**编辑**菜单上，单击**删除**。  
  
     此外可以按 DELETE 键或右键单击该链接并单击**删除**快捷菜单上。  
  
    > [!NOTE]
    >  您可以批量选择多个链接和/或 functoid，然后一次性将其删除。 可以撤消或重做链接和/或 functoid 的批量删除。 有关撤消和重做操作的详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使用链接以指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)