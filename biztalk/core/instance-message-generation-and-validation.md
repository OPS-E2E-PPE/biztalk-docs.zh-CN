---
title: 实例消息的生成和验证 |Microsoft Docs
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
ms.openlocfilehash: 7e9a79a589dcedd9169de8d753922632cff2acb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331915"
---
# <a name="instance-message-generation-and-validation"></a>实例消息的生成和验证
验证架构后，可用于生成示例实例消息。 生成的示例实例消息包含的元素和属性架构中，指定的结构并生成模拟数据需要。  
  
> [!NOTE]
>  使用生成实例消息不太完善，若要生成数据根据指定的多个属性值的数据生成机制。 例如，如果架构包含的任何值**模式**属性，现已推出**限制**类别**字段元素**节点和**字段属性**节点时其**Derived By**属性设置为**限制**，不能使用生成的实例消息，条件是，作为输入**验证实例**操作。  
  
 若要从架构生成实例消息示例，请使用**生成实例**命令在解决方案资源管理器中与该架构关联的快捷菜单上。 实例消息生成操作将结果报告在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]输出窗口。  
  
> [!NOTE]
>  **生成实例**操作包括**验证架构**操作。 如果验证失败，将不生成任何示例实例消息。  
  
 有关逐步说明如何从架构，包括如何配置要包含生成的实例消息的输出文件中生成的实例消息，请参阅[生成实例消息](../core/how-to-generate-instance-messages.md)。  
  
> [!NOTE]
>  如果未指定的值**根引用**的属性**架构**节点，BizTalk 编辑器生成实例消息的第一个根节点在架构中。 如果指定的值**根引用**属性，BizTalk 编辑器生成实例消息为指定的根。  
  
 如果验证了您的架构，可以使用 BizTalk 编辑器来确定实例消息是否符合该架构。  
  
 若要验证针对架构的实例消息，请使用**验证实例**命令在解决方案资源管理器中与该架构关联的快捷菜单上。 验证的结果中报告[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]输出窗口。  
  
> [!NOTE]
>  有些情况下在其中生成的实例消息将通过根据从其生成相同的架构验证。 例如，如果你尝试验证使用生成的实例消息**生成实例**BizTalk 编辑器和相关架构中的命令包含任何**Field 元素**节点或**字段属性**拥有的节点及其**Derived By**属性设置为**限制**和使用该技术**模式**属性来指定相应的数据必须符合的模式，则验证将失败。 这是因为生成实例消息时使用的数据生成机制不太完善，若要生成数据根据指定的值**模式**属性。 此外存在其他情况。  
  
 有关逐步说明如何验证实例消息，包括如何指定实例消息进行验证，请参阅[验证架构](../core/how-to-validate-schemas-in-visual-studio.md)。  
  
## <a name="see-also"></a>请参阅  
 [有关架构](../core/about-schemas.md)   
 [测试架构](../core/testing-schemas.md)