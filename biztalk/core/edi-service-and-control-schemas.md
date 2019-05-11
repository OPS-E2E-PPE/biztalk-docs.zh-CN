---
title: EDI 服务和控制架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4866571b-b12d-446c-8d27-a72fe7e479ef
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b12bdee5fd1e29e1f65fa709612cceb729e2cd7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389595"
---
# <a name="edi-service-and-control-schemas"></a>EDI 服务和控制架构
处理消息信封 （标头控制架构） 和确认所需控制架构。 这些架构由安装程序部署在 Microsoft.BizTalk.Edi.BaseArtifacts.dll 中。 这些架构无需添加到 BizTalk 项目，因为它们部署在 BaseArtifacts.dll 中。 需要将对 BaseArtifacts.dll 程序集的引用添加到包含您要使用这些架构的架构的项目。  

## <a name="envelope-service-schemas"></a>信封服务架构  
 服务架构 X12ServiceSchema 和 EdifactServiceSchema 用于验证交换、 组和事务集标头和尾部中的 EDI 交换的信封。 这适用于所有 EDI 交换： 未批处理的交换、 要拆分的批处理的交换或要保留的批处理的交换。 这些架构的命名空间 http://schemas.microsoft.com/Edi/X12ServiceSchema 和 http://schemas.microsoft.com/Edi/EdifactServiceSchema 。  

 如果 EDI 交换为保留的批交换，则除使用服务架构之外，BizTalk 运行时还使用批架构 X12_BatchSchema 和 Edifact_BatchSchema。 有关详细信息，请参阅[EDI 批架构](../core/edi-batch-schemas.md)。  

 您可以自定义这些架构中的 ID 字段枚举。 不允许使用任何其他修改。 有关详细信息，请参阅[信封架构中自定义枚举](../core/customizing-enumerations-in-the-envelope-schema.md)。  

## <a name="acknowledgment-control-schemas"></a>确认控制架构  
 EDI 接收管道使用确认架构生成要发送的确认和 EDI 发送管道使用处理收到的确认。 这些架构包括下表中所示的 997 功能确认架构和 TA1 交换确认架构用于 X12 编码和用于 EDIFACT 编码的 CONTRL 架构。 不能修改这些架构。  


|      确认       |     架构名称      |             目标 Namespace             |                               Root                                |
|----------------|----------------------|------------------------------------------|-------------------------------------------------------------------|
|    X12 TA1     |    X12_TA1Schema     |   http://schemas.microsoft.com/Edi/X12   |                   TA1<br /><br /> X12_TA1_Root                    |
|    X12 997     |    X12_997Schema     |   http://schemas.microsoft.com/Edi/X12   |            ST<br /><br /> SE<br /><br /> X12_997_Root             |
| EDIFACT CONTRL | Edifact_ContrlSchema | http://schemas.microsoft.com/Edi/Edifact | Efact_Contrl_Root<br /><br /> UCD<br /><br /> UCM<br /><br /> UCS |

 对于 X12 编码，997 功能确认架构定义交换、 组和事务集/消息标头和尾部中信封的消息时，使用和 AK1、 AK2、 AK3、 AK4、 AK5 和 AK9 段该报表的正文验证结果. TA1 技术确认架构定义交换标头和尾部以及报告标头验证结果的 TA1 确认段。 这些架构的命名约定是 X12_\<版本号\>*997.xsd 和 X12\\*\<版本号\>_TA1.xsd。 这些架构的目标命名空间是 http://schemas.microsoft.com/BizTalk/EDI/X12/2006 。  

 EDIFACT 支持两段式确认范例。 第一个确认是使用 CONTRL 架构中的三个段构造的交换回执。 此技术确认报告标头验证的结果。 第二个确认使用 CONTRL 架构的其余段。 此架构的命名约定是 EFACT_\<版本号\>_CONTRL.xsd。 此架构的目标命名空间是 http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006 。  

## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何接收 EDI 消息](../core/how-biztalk-server-receives-edi-messages.md)   
 [BizTalk Server 如何发送 EDI 消息](../core/how-biztalk-server-sends-edi-messages.md)