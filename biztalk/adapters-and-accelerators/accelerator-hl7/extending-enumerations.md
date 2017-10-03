---
title: "扩展枚举 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enumeration values
- 2.X schemas, enumeration values
ms.assetid: 043def35-b644-4502-a2e2-cc1a5fc0328a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 527894b27c5720a1b006387f861922eb978069b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="extending-enumerations"></a>扩展枚举
可以将值添加到 HL7 消息正文、 确认和消息正文架构中建立的许多字段、 线段和数据类型可接受的值的枚举。 这涉及到的更改的值中的特定表中您正在工作的 HL7 版本的通用表值架构文件集 ( **Tablevalues_\<***版本***>.xsd**架构文件)。  
  
 你将添加到枚举为消息标头架构不同的方式比你在其他架构中，如消息正文架构。 对于消息标头架构，则必须更改 MSH_25_GLO_DEF.xsd 文件中的表。 对于其他架构中，更改表值架构文件中的表 (tablevalues_\<版本 >.xsd)。  
  
### <a name="to-add-an-enumeration-value-to-the-table-values-common-schema-file"></a>若要将一个枚举值添加到表值常见架构文件  
  
1.  你首先需要确定包含你想要添加到枚举的表。 在解决方案资源管理器的[!INCLUDE[vs2012](../../includes/vs2012-md.md)]，打开包含你想要更改的元素的架构文件。 在 BizTalk 资源管理器，单击你想要添加的值的字段元素。  
  
    > [!NOTE]
    >  当您更改表值常见架构文件中的一个枚举时，引用该枚举的所有对象会受到都影响。  
  
2.  在**属性**窗格中，记下的表中的名称**基数据类型**字段。  
  
    > [!NOTE]
    >  如果没有任何表中列出**基数据类型**字段中，和**派生源**属性未设置为**Restricted**，则该字段不具有与之关联的枚举.  
  
3.  在解决方案资源管理器，打开**Tablevalues_\<***版本***>.xsd**，然后单击**打开**。  
  
    > [!NOTE]
    >  你必须为你想要更改的 HL7 架构的每个版本单独执行此过程。  
  
4.  在 BizTalk 编辑器中，浏览到你想要更改，然后单击该节点将表的表。  
  
5.  在属性窗口中，在**限制**部分中，单击**枚举**，然后单击省略号 （…） 按钮以打开枚举编辑器。  
  
6.  在枚举编辑器中，添加到现有值列表的新值，然后单击**确定**。  
  
### <a name="to-add-an-enumeration-value-to-a-message-header-schema"></a>若要将一个枚举值添加到消息标头架构  
  
1.  在解决方案资源管理器，打开 MSH_25_GLO_DEF 架构，然后单击**打开**。  
  
2.  右键单击**MSH**节点，指向**插入架构节点**，然后单击**子字段元素**。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]将某一字段节点添加到 MSH，调用**字段**。 单击**ENTER**。  
  
3.  在**属性**窗口中，单击**数据类型**节点，然后从下拉列表中，选择你想要添加的枚举值的表。  
  
4.  在**属性**窗口，请在**限制**部分中，单击**枚举**，然后单击省略号 （…） 按钮以打开枚举编辑器。  
  
5.  在枚举编辑器中，添加到现有值列表的新值，然后单击**确定**。  
  
     当你将添加一个值到枚举为任何节点，比如**字段**节点，你将添加全局使用该表的所有对象的值。 因此，您现在可以删除**字段**节点和的值仍将存在的表。 可以通过在右窗格中的 BizTalk 编辑器，到表中，滚动，并验证你添加的值存在对此进行验证。  
  
6.  右键单击**字段**节点在 BizTalk 编辑器中，单击**删除**，然后单击**是**。  
  
## <a name="see-also"></a>另请参阅  
 [表值通用架构](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)   
 [扩展 HL7 2.X 架构具有 Z 对象](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [创建声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [在架构中创建自定义数据类型](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [在架构中创建自定义的表](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)   
 [处理未声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)