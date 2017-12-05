---
title: "EDI 服务和控制架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4866571b-b12d-446c-8d27-a72fe7e479ef
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25e4ee4eb51d56aaeb4f433fa523e416a8c908e0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="edi-service-and-control-schemas"></a>EDI 服务和控制架构
控制架构对处理消息信封（标头控制架构）和确认来说是必要的。 这些架构由安装程序部署在 Microsoft.BizTalk.Edi.BaseArtifacts.dll 中。 因为这些架构部署在 BaseArtifacts.dll 中，因此不必将它们添加到 BizTalk 项目中。 如果要使用项目中包含的架构，则需要将对 BaseArtifacts.dll 程序集的引用添加到包含这些架构的项目中。  
  
## <a name="envelope-service-schemas"></a>信封服务架构  
 服务架构 X12ServiceSchema 和 EdifactServiceSchema 用于验证 EDI 交换的信封中使用的交换、组和事务集标头及尾部。 这适用于所有的 EDI 交换： unbatched 的交换、 批处理的交换进行拆分或批处理的交换，将保留。 这些架构的命名空间为 http://schemas.microsoft.com/Edi/X12ServiceSchema 和 http://schemas.microsoft.com/Edi/EdifactServiceSchema。  
  
 如果 EDI 交换为保留的批交换，则除使用服务架构之外，BizTalk 运行时还使用批架构 X12_BatchSchema 和 Edifact_BatchSchema。 有关详细信息，请参阅[批处理的 EDI 架构](../core/edi-batch-schemas.md)。  
  
 您可以在这些架构中自定义 ID 字段枚举。 不允许进行其他修改。 有关详细信息，请参阅[信封架构中的自定义枚举](../core/customizing-enumerations-in-the-envelope-schema.md)。  
  
## <a name="acknowledgment-control-schemas"></a>确认控件架构  
 EDI 接收管道使用确认架构生成要发送的确认，并且 EDI 发送管道使用确认架构处理收到的确认。 这些架构包括用于 X12 编码的 997 功能确认架构和 TA1 交换确认架构，以及用于 EDIFACT 编码的 CONTRL 架构，如下表所示。 不能修改这些架构。  
  
|ACK|架构名|目标命名空间|Root|  
|---------|-----------------|----------------------|----------|  
|X12 TA1|X12_TA1Schema|http://schemas.microsoft.com/Edi/X12|TA1<br /><br /> X12_TA1_Root|  
|X12 997|X12_997Schema|http://schemas.microsoft.com/Edi/X12|ST<br /><br /> SE<br /><br /> X12_997_Root|  
|EDIFACT CONTRL|Edifact_ContrlSchema|http://schemas.microsoft.com/Edi/Edifact|Efact_Contrl_Root<br /><br /> UCD<br /><br /> UCM<br /><br /> UCS|  
  
 对于 X12 编码，997 功能确认架构定义了消息信封中使用的交换、组和事务集/消息的标头和尾部以及用于报告正文验证结果的 AK1、AK2、AK3、AK4、AK5 和 AK9 段。 TA1 技术确认架构定义了交换的标头和尾部以及用于报告标头验证结果的 TA1 确认段。 这些架构的命名约定是 X12_\<版本号\>_997.xsd 和 X12\_\<版本号\>_TA1.xsd。 这些架构的目标命名空间为 http://schemas.microsoft.com/BizTalk/EDI/X12/2006。  
  
 EDIFACT 支持两段式确认范例。 第一个确认是使用 CONTRL 架构中的三个段构造的交换回执。 此技术确认报告了标头验证的结果。 第二个确认使用 CONTRL 架构中所剩余的段。 此架构的命名约定是 EFACT_\<版本号\>_CONTRL.xsd。 此架构的目标命名空间为 http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 接收 EDI 消息的方式](../core/how-biztalk-server-receives-edi-messages.md)   
 [BizTalk Server 如何发送 EDI 消息](../core/how-biztalk-server-sends-edi-messages.md)