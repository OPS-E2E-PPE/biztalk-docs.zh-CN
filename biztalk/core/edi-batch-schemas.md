---
title: 批处理的 EDI 架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26da8036-8fe0-481e-b1e9-7f2e5b090768
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e159734c7d6028eb7f54354140c40757cb212b3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968699"
---
# <a name="edi-batch-schemas"></a>批处理的 EDI 架构
BizTalk Server 处理保留交换时，至少使用三个架构：  
  
-   批处理架构（交换 XML 架构）：用于验证保留的批处理交换（BaseArtifacts.dll 中部署的 X12_BatchSchema 或 Edifact_BatchSchema）的根节点。  
  
-   信封服务架构：用于验证交换、组、事务集标头和尾部（BaseArtifacts.dll 中部署的 X12ServiceSchema 或 EdifactServiceSchema）。 有关详细信息，请参阅[EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)。  
  
-   文档架构：用于批处理交换中的每个文档类型（部署在项目中）。 有关详细信息，请参阅[EDI 文档架构](../core/edi-document-schemas.md)。  
  
 批处理架构在运行时用于验证保留的入站和出站批处理交换。 批处理架构也用于在设计时验证和生成消息实例。  
  
## <a name="batch-schemas-used-at-runtime"></a>运行时使用的批处理架构  
 存在两个规范版本的批处理架构： X12_BatchSchema.xsd 的 X12 编码和 EDIFACT_BatchSchema.xsd EDIFACT 编码。 这些架构是包括控制段的模板。 这些架构具有以下根名称和命名空间：  
  
|架构|根节点|命名空间|  
|------------|---------------|---------------|  
|X12_BatchSchema|X12InterchangeXML|http://schemas.microsoft.com/Edi/X12_BatchSchema|  
|Edifact_BatchSchema|EdifactInterchangeXML|http://schemas.microsoft.com/Edi/Edifact|  
  
 在由接收管道生成的 XML 实例上的文档类型将是一个常量 (\<编码\>_BatchSchema.xml) 并将引用此规范的架构。 可以在业务流程的映射中使用该实例，但是，在进行此操作前，必须更改其文档类型和命名空间以映射到所需的实际架构。  
  
 在设计项目时不必指定批处理架构，因为该架构部署在 BaseArtifacts.dll 中。  
  
## <a name="batch-schemas-in-the-schema-store"></a>架构存储中的批处理架构  
 BizTalk Server 在运行时用于处理保留批处理的批处理架构部署在 BaseArtifacts.dll 程序集中。 这些架构可自动用于运行时处理。 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 上的 BizTalk 架构存储中也将提供 Edifact_BatchSchema 和 X12_BatchSchema。 这些架构中的每个架构仅在设计时用于验证或生成交换。 在接收管道或发动管道中，运行时进行验证不需要任何架构。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 架构](../core/edi-schemas.md)   
 [处理传入批](../core/processing-incoming-batches.md)