---
title: 使用 XML 工具扩展 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5613bf15-6c0a-4a82-b200-24d0801d7ece
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 976082fc14eb37d550956ec447eb63938706daa3
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006310"
---
# <a name="using-the-xml-tool-extensions"></a>使用 XML 工具扩展
使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的 XML 工具扩展，您可以对架构、映射和消息实例执行任务。 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 环境中，您可以在设计时使用这些扩展。 您可以执行的任务有：  
  
-   **验证架构**。 此操作将根据 EDI 规则对 EDI 架构进行验证。 有关详细信息，请参阅[验证架构 (EDI)](../core/validating-a-schema-edi.md)。  
  
-   **验证消息实例**。 此操作将验证单个事务集（没有交换和组标头）或包含多个事务集的完整批处理交换（带有交换和组标头）。 若要验证未批处理的交换，需要从实例中删除交换和组标头。 有关详细信息，请参阅[验证实例 (EDI)](../core/validating-an-instance-edi.md)。  
  
-   **生成的消息实例**。 此操作可以生成完整的批处理交换或不带交换和组标头的事务集。 您必须指定分隔符、标识符以及要用于生成实例的其他格式设置。 有关详细信息，请参阅[生成实例 (EDI)](../core/generating-an-instance-edi.md)。  
  
-   **测试映射**。 此操作将根据源文档和映射生成输出文档（带有虚构数据）。 有关详细信息，请参阅[测试映射](../core/testing-a-map.md)。  
  
-   **验证地图**。 此操作将生成两个文件，一个包含映射的基础 XSLT，另一个包含扩展对象。 有关详细信息，请参阅[验证映射 (EDI)](../core/validating-a-map-edi.md)。  
  
 在 BizTalk Server 中，这些扩展处理 EDI 架构、 映射和消息实例。 使用这些扩展，您可以更有效地处理复杂的 EDI 架构、映射和交换。  
  
 默认情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装程序将启用 XML 工具扩展。 如果双击在解决方案资源管理器的 Visual Studio 中，架构**架构编辑器扩展**的架构的属性设置为**EDI 架构编辑器扩展**。 这样才能使 XML 工具扩展正常工作。 您可以选择其他架构编辑器扩展，同时保持选中 EDI 扩展。  
  
## <a name="see-also"></a>另请参阅  
 [生成实例 (EDI)](../core/generating-an-instance-edi.md)   
 [验证实例 (EDI)](../core/validating-an-instance-edi.md)   
 [验证架构 (EDI)](../core/validating-a-schema-edi.md)   
 [测试映射](../core/testing-a-map.md)   
 [验证映射 (EDI)](../core/validating-a-map-edi.md)