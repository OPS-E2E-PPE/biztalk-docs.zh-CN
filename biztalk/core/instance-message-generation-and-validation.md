---
title: 实例消息生成和验证 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a306846-3942-4ba1-a74e-6ead8deb0322
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 964f9bd2ee2b8bb20872bc593723cea778b5ed81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257981"
---
# <a name="instance-message-generation-and-validation"></a>实例消息的生成和验证
在验证架构之后，可以使用该架构来生成示例实例消息。 生成的示例实例消息包含该架构指定的元素和属性结构，并生成必需的虚设数据。  
  
> [!NOTE]
>  生成实例消息所使用的数据生成机制还不太完善，不能根据为多个属性指定的值来生成数据。 例如，如果架构包含的任何值**模式**属性，它是位于**限制**类别**Field 元素**节点和**字段特性**节点时其**派生源**属性设置为**限制**，生成的实例消息不能用作是作为输入**验证实例**操作。  
  
 若要从架构生成的示例实例消息，请使用**生成实例**命令在解决方案资源管理器中的架构与关联的快捷菜单上。 实例消息生成操作的结果将在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“输出”窗口中报告。  
  
> [!NOTE]
>  **生成实例**操作包括**验证架构**操作。 如果验证失败，将不会生成示例实例消息。  
  
 有关详细的分步说明，有关如何从架构，包括如何配置输出文件包含生成的实例消息中，生成实例消息，请参阅[生成实例消息](../core/how-to-generate-instance-messages.md)。  
  
> [!NOTE]
>  如果未指定的值**根引用**属性**架构**BizTalk 编辑器节点在架构中生成的第一个根节点实例消息。 如果指定的值**根引用**属性，BizTalk 编辑器生成指定的根实例消息。  
  
 如果已对架构进行了验证，即可使用 BizTalk 编辑器来确定实例消息是否符合该架构。  
  
 若要验证针对架构的实例消息，使用**验证实例**命令在解决方案资源管理器中的架构与关联的快捷菜单上。 验证的结果将在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“输出”窗口中报告。  
  
> [!NOTE]
>  有时，生成的实例消息将不能通过根据生成该实例消息的同一架构所执行的验证。 例如，如果你尝试验证实例消息生成了使用**生成实例**BizTalk 编辑器和相关的架构中的命令包含任何**Field 元素**节点或**字段特性**节点具有其**派生源**属性设置为**限制**和使用**模式**属性来指定相应的数据必须符合的模式，则验证将会失败。 这是因为生成实例消息时使用的数据生成机制不足够复杂以生成数据为指定的值根据**模式**属性。 此外，还存在其他情况。  
  
 有关详细的分步说明，有关如何验证消息实例，包括如何指定要验证的实例消息，请参阅[验证架构](../core/how-to-validate-schemas-in-visual-studio.md)。  
  
## <a name="see-also"></a>另请参阅  
 [有关架构](../core/about-schemas.md)   
 [测试架构](../core/testing-schemas.md)