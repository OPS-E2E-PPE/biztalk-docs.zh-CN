---
title: 如何管理现有链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0db213b9-df84-4ebd-a59f-7691774d5031
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab9cba5b07cbb0b3a101a3abea92b5aed8b00039
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336762"
---
# <a name="how-to-manage-existing-links"></a>如何管理现有链接
有时您可能需要更改的源或目标的链接，命名或重命名链接，或删除的链接。 本主题提供执行这些类型的链接操作的分步说明。  
  
### <a name="to-change-the-source-or-destination-of-a-link"></a>若要更改的源或目标的链接  
  
1.  在 BizTalk 映射器网格页上，单击链接以选择它。  
  
     突出显示的网格页中所选链接的终结点。  
  
2.  将链接的终结点拖到新的 schema 节点或想要连接的 functoid。  
  
     拖动终结点时，光标将变为十字线。 如果您指向 schema 节点或 functoid （或其他对象） 无法接受链接，光标将变为带有贯穿线的圆形。  
  
    > [!IMPORTANT]
    >  如果有两个或更多输入的链接连接到 functoid 并将其中一个重定向或其中的多个输入源架构中的其他节点或其他 functoid 的链接，可能不会保留原始 functoid 的输入参数的顺序。 使用**配置\<Functoid\> Functoid**对话框以查看输入参数的生成顺序以及其重新排序，如有必要。 有关对 functoid 的输入的参数重新排序的详细信息，请参阅[编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)。  
  
### <a name="to-setedit-the-label-of-a-link"></a>设置/编辑链接的标签  
  
1. 在 BizTalk 映射器网格页上，单击链接以选择它。  
  
    突出显示的网格页中所选链接的终结点。  
  
2. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，提供链接时使用的 （新） 名称**标签**属性。  
  
### <a name="to-delete-a-link"></a>若要删除的链接  
  
1.  在 BizTalk 映射器网格页上，单击链接以选择它。  
  
     突出显示的网格页中所选链接的终结点。  
  
2.  上**编辑**菜单上，单击**删除**。  
  
     此外可以按 DELETE 键或右键单击该链接，单击**删除**快捷菜单上。  
  
    > [!NOTE]
    >  您可以批量选择多个链接和/或 functoid，然后在一个操作中将其删除。 您可以撤消或重做链接和/或 functoid 的批量删除。 有关撤消和重做操作有关的详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用链接指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)