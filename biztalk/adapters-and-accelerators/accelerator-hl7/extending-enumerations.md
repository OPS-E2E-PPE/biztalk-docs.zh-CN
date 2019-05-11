---
title: 扩展枚举 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enumeration values
- 2.X schemas, enumeration values
ms.assetid: 043def35-b644-4502-a2e2-cc1a5fc0328a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60e8e5ab2b5072679e9d29f1c13f58c554e41c93
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268057"
---
# <a name="extending-enumerations"></a>扩展枚举
可以将值添加到 HL7 消息正文、 确认和消息正文架构中建立的许多字段，段和数据类型可接受的值的枚举。 这涉及到更改您正在工作的 HL7 版本的公共表值架构文件中的特定表中的值集 ( **Tablevalues_\<**<em>版本</em> **\>.xsd**架构文件)。  
  
 您将添加到枚举为消息标头架构以不同方式比您在其他架构中，如消息正文架构。 为消息标头架构，则必须更改 MSH_25_GLO_DEF.xsd 文件中的表。 对于其他架构更改的表中的表值架构文件 (tablevalues_\<版本\>.xsd)。  
  
### <a name="to-add-an-enumeration-value-to-the-table-values-common-schema-file"></a>若要将一个枚举值添加到表值通用架构文件  
  
1. 首先需要确定包含你想要添加到枚举的表。 在解决方案资源管理器的 Visual Studio 中，打开包含你想要更改的元素的架构文件。 在 BizTalk 浏览器中，单击你想要添加的值的字段元素。  
  
   > [!NOTE]
   >  表值通用架构文件中的枚举更改时，会影响引用该枚举的所有对象。  
  
2. 在中**属性**窗格中，记下的表中的名称**Base Data Type**字段。  
  
   > [!NOTE]
   >  如果没有任何表中列出**Base Data Type**字段中，并**Derived By**属性未设置为**Restricted**，那么该字段没有与之关联的枚举.  
  
3. 在解决方案资源管理器中打开**Tablevalues_\<**<em>版本</em>**\>.xsd**，然后单击**打开**。  
  
   > [!NOTE]
   >  为你想要更改的 HL7 架构的每个版本，必须单独执行此过程。  
  
4. 在 BizTalk 编辑器中，浏览到你想要更改，然后单击该节点将表的表。  
  
5. 在属性窗口中**限制**部分中，单击**枚举**，然后单击省略号 （...） 按钮以打开枚举编辑器中。  
  
6. 在枚举编辑器中，将新值添加到现有值的列表，然后依次**确定**。  
  
### <a name="to-add-an-enumeration-value-to-a-message-header-schema"></a>若要将一个枚举值添加到消息标头架构  
  
1. 在解决方案资源管理器，打开 MSH_25_GLO_DEF 架构，然后单击**打开**。  
  
2. 右键单击**MSH**节点，指向**插入 Schema 节点**，然后单击**子字段元素**。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 添加到 MSH，名为字段节点**字段**。 单击**ENTER**。  
  
3. 在中**属性**窗口中，单击**数据类型**节点，然后从下拉列表中，选择你想要添加的枚举值的表。  
  
4. 在中**属性**窗口，请在**限制**部分中，单击**枚举**，然后单击省略号 （...） 按钮以打开枚举编辑器中。  
  
5. 在枚举编辑器中，将新值添加到现有值的列表，然后依次**确定**。  
  
    当您值向枚举添加的任何节点，如**字段**节点中，您可以添加针对使用该表的所有对象的全局值。 因此，现在可以删除**字段**节点，然后值仍将存在的表。 可以通过滚动到表中，在右窗格的 BizTalk 编辑器中验证你添加的值存在对此进行验证。  
  
6. 右键单击**字段**节点在 BizTalk 编辑器中，单击**删除**，然后单击**是**。  
  
## <a name="see-also"></a>请参阅  
 [表值通用架构](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)   
 [使用 Z 对象扩展 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [创建声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [在架构中创建自定义数据类型](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [在架构中创建自定义表](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)   
 [处理未声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)