---
title: EDI 批处理架构 |Microsoft Docs
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
ms.openlocfilehash: 90c03f9a6136a925419166fa4db8b919b9ec8eb3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389246"
---
# <a name="edi-batch-schemas"></a>EDI 批处理架构
当 BizTalk Server 处理保留的交换时，它使用至少三个架构：  

- 要验证的根节点的保留的批架构 （交换 XML 架构） 的批处理交换 （X12_BatchSchema 或 Edifact_BatchSchema 部署在 BaseArtifacts.dll 中）  

- 信封服务架构来验证交换、 组、 和事务集标头和尾部 （X12ServiceSchema 或 EdifactServiceSchema 部署在 BaseArtifacts.dll 中）。 有关详细信息，请参阅[EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)。  

- 批处理交换 （部署在你的项目） 中每个文档类型的文档架构。 有关详细信息，请参阅[EDI 文档架构](../core/edi-document-schemas.md)。  

  批处理架构在运行时用于验证保留的入站和出站批处理的交换。 批处理架构也用于在设计时验证和生成消息实例。  

## <a name="batch-schemas-used-at-runtime"></a>在运行时使用的批处理架构  
 存在两个批处理架构规范版本：对于 X12 X12_BatchSchema.xsd 编码和用于 EDIFACT 编码的 EDIFACT_BatchSchema.xsd。 这些架构是包括控制段的模板。 这些架构必须具有以下根名称和命名空间：  


|       架构        |       根节点       |                    命名空间                     |
|---------------------|-----------------------|--------------------------------------------------|
|   X12_BatchSchema   |   X12InterchangeXML   | http://schemas.microsoft.com/Edi/X12_BatchSchema |
| Edifact_BatchSchema | EdifactInterchangeXML |     http://schemas.microsoft.com/Edi/Edifact     |

 由接收管道生成的 XML 实例上的文档类型将是一个常量 (\<编码\>_BatchSchema.xml) 并将引用此规范架构。 你可以在业务流程; 中映射中使用此实例但是，因此需要更改映射到实际的架构的文档类型和命名空间执行操作之前需要。  

 您不需要指定批处理架构在设计时在项目中，因为它部署在 BaseArtifacts.dll 中。  

## <a name="batch-schemas-in-the-schema-store"></a>架构存储中的批处理架构  
 BizTalk Server 使用在运行时用于处理保留批处理的批处理架构部署在 BaseArtifacts.dll 程序集。 这些是自动可供运行时处理。 Edifact_BatchSchema 和 X12_BatchSchema 也是可用的 BizTalk 架构存储中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI。 每个架构仅用于在设计时验证或生成交换。 既不是所必需的接收管道中的验证架构，或发送管道在运行时。  

## <a name="see-also"></a>请参阅  
 [EDI 架构](../core/edi-schemas.md)   
 [处理传入批](../core/processing-incoming-batches.md)