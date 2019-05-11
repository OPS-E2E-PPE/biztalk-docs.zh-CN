---
title: 使用 XML 工具扩展 |Microsoft Docs
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
ms.openlocfilehash: fd45548534cc9cbd7968d39e810210acf472cf0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302684"
---
# <a name="using-the-xml-tool-extensions"></a>使用 XML 工具扩展
XML 工具扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使您能够执行的任务上架构、 映射和消息实例。 在设计时使用这些扩展[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。 你可以执行的任务包括：  
  
- **验证架构**。 此操作将验证 EDI 架构根据 EDI 规则。 有关详细信息，请参阅[验证架构 (EDI)](../core/validating-a-schema-edi.md)。  
  
- **验证消息实例**。 此操作将验证单个事务集 （没有交换和组标头） 或包含多个事务的完整批处理的交换设置 （带有交换和组标头）。 若要验证未批处理的交换，需要从实例中删除交换和组标头。 有关详细信息，请参阅[验证实例 (EDI)](../core/validating-an-instance-edi.md)。  
  
- **生成消息实例**。 此操作将生成完整的批的交换或事务集没有交换和组标头。 必须指定分隔符、 标识符和其他用于生成该实例的格式设置。 有关详细信息，请参阅[生成实例 (EDI)](../core/generating-an-instance-edi.md)。  
  
- **测试映射**。 此操作将生成输出文档 （具有虚构数据） 基于源文档和映射。 有关详细信息，请参阅[测试映射](../core/testing-a-map.md)。  
  
- **验证映射**。 此操作将生成包含基础映射和包含扩展对象的文件的 XSLT 的文件。 有关详细信息，请参阅[验证映射 (EDI)](../core/validating-a-map-edi.md)。  
  
  在 BizTalk Server 中，这些扩展处理 EDI 架构、 映射和消息实例。 这些扩展使您能够更有效地处理复杂的 EDI 架构、 映射和交换。  
  
  默认情况下将启用 XML 工具扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序。 如果您双击解决方案资源管理器的 Visual Studio 中，架构**架构编辑器扩展**架构的属性设置为**EDI 架构编辑器扩展**。 这是必需的 XML 工具扩展正常工作。 保持选中 EDI 扩展时，可以选择其他架构编辑器扩展。  
  
## <a name="see-also"></a>请参阅  
 [生成实例 (EDI)](../core/generating-an-instance-edi.md)   
 [验证实例 (EDI)](../core/validating-an-instance-edi.md)   
 [验证架构 (EDI)](../core/validating-a-schema-edi.md)   
 [测试映射](../core/testing-a-map.md)   
 [验证映射 (EDI)](../core/validating-a-map-edi.md)