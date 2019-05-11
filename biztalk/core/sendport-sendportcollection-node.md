---
title: 发送端口 （SendPortCollection 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf7a6f9-9240-48b9-b196-8838afd4f41e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3577aa70936a5a97bf91e70780911514e8b3e7b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380000"
---
# <a name="sendport-sendportcollection-node"></a>发送端口 （SendPortCollection 节点）
绑定文件的发送端口节点包含有关与绑定文件一起导出的发送端口的特定信息。  

## <a name="nodes-in-the-sendport-node"></a>节点中的发送端口节点  
 下表列出了可为绑定文件的此节点设置的属性：  


|                                   **名称**                                    | **节点类型** |         **数据类型**          |                                       **说明**                                        | **限制** |                                                                                            **注释**                                                                                             |
|-------------------------------------------------------------------------------|---------------|--------------------------------|----------------------------------------------------------------------------------------------|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                     “属性”                                      |   特性   |           xs:string            |                             指定发送端口的名称。                             |   可选   |                                                                                        默认值：空                                                                                         |
|                                   IsStatic                                    |   特性   |           xs:boolean           |                    指定发送端口是静态或动态。                     |     Required     |                                                                                         默认值：无                                                                                         |
|                                   IsTwoWay                                    |   特性   |           xs:boolean           |         指定发送端口是单向还是要求-响应 （双向）。         |     Required     |                                               默认值：无<br /><br /> 可能的值位于**MSBTS_SendPort.IsTwoWay 属性 (WMI)**。                                                |
|                                 BindingOption                                 |   特性   |             xs:int             |                  指定业务流程端口绑定的类型。                   |     Required     |                                        默认值：无<br /><br /> 可能的值位于**Microsoft.BizTalk.ExplorerOM.BindingType**枚举。                                        |
|                                  Description                                  |    元素    |           xs:string            |                          指定发送端口的说明。                          |     Required     |                                                                                        默认值：空                                                                                         |
| [TransmitPipeline（SendPort 节点）](../core/transmitpipeline-sendport-node.md) |    录制     |   PipelineRef (ComplexType)    |                  指定与发送端口关联的发送管道。                  |   可选   |                                                                                         默认值：无                                                                                         |
|                               SendPipelineData                                |    元素    |           xs:string            |  指定管道的特定于此实例的使用情况的自定义配置。  |   可选   |                                                                                        默认值： 空。                                                                                        |
|         [PrimaryTransport](../core/primarytransport-sendport-node.md)         |    录制     |  TransportInfo (ComplexType)   |  指定有关发送端口配置的主传输的信息使用。  |   可选   |                                                                                         默认值：无                                                                                         |
|       [SecondaryTransport](../core/secondarytransport-sendport-node.md)       |    录制     |  TransportInfo (ComplexType)   | 指定有关发送端口配置的辅助传输的信息使用。 |   可选   |                                                                                         默认值：无                                                                                         |
|           [EncryptionCert](../core/encryptioncert-sendport-node.md)           |    录制     | CertificateInfo (ComplexType)  |       指定与发送端口一起使用的加密证书有关的信息。        |   可选   |                                                                                         默认值：无                                                                                         |
|          [ReceivePipeline](../core/receivepipeline-sendport-node.md)          |    录制     |   PipelineRef (ComplexType)    |          指定有关与发送端口一起使用的任何接收管道的信息。          |   可选   |                                                                                         默认值：无                                                                                         |
|                              ReceivePipelineData                              |    元素    |           xs:string            |  指定管道的特定于此实例的使用情况的自定义配置。  |     Required     |                                                                                        默认值：空                                                                                         |
|                                   跟踪                                    |    元素    |             xs:int             |                  指定的文档跟踪级别为发送端口                  |     Required     |                                       默认值：无<br /><br /> 可能的值位于**Microsoft.BizTalk.ExplorerOM.TrackingTypes**枚举。                                       |
|                                    “筛选器”                                     |    元素    |           xs:string            |         指定此发送端口上使用的可选筛选器表达式的名称。         |     Required     |                                                默认值：空<br /><br /> 在可能的值为**MSBTS_SendPort.Filter 属性 (WMI)**                                                 |
|       [Transforms（SendPort 节点）](../core/transforms-sendport-node.md)       |    录制     | ArrayOfTransform (ComplexType) |           指定的一种方式的出站转换集合发送端口。            |   可选   |                                                                                         默认值：无                                                                                         |
|        [InboundTransforms](../core/inboundtransforms-sendport-node.md)        |    录制     | ArrayOfTransform (ComplexType) |            指定双向发送端口的入站转换集合。            |   可选   |                                                                                         默认值：无                                                                                         |
|                                OrderedDelivery                                |    元素    |           xs:boolean           |           指定发送端口按序的消息传送。            |     Required     |                                            默认值：无<br /><br /> 在可能的值为**MSBTS_SendPort.OrderedDelivery 属性 (WMI)**                                            |
|                                   Priority                                    |    元素    |             xs:int             |                           指定发送端口的优先级。                           |     Required     |                                                 默认值：5<br /><br /> 在可能的值为**MSBTS_SendPort.Priority 属性 (WMI)**                                                  |
|                             StopSendingOnFailure                              |    元素    |           xs:boolean           |         指定发送端口停止发送失败的消息。          |     Required     |                                          默认值：无<br /><br /> 在可能的值为**MSBTS_SendPort.StopSendingOnFailure 属性 (WMI)**                                          |
|                              RouteFailedMessage                               |    元素    |           xs:boolean           |      指定失败消息路由到失败的消息订户。      |     Required     |                                           默认值：无<br /><br /> 在可能的值为**MSBTS_SendPort.RouteFailedMessage 属性 (WMI)**                                           |
|                                ApplicationName                                |    元素    |           xs:string            |             指定与发送端口关联的应用程序的名称。             |     Required     | 默认值：空<br /><br /> 可能的值位于**ISSOMapping.ApplicationName 属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 |

## <a name="see-also"></a>另请参阅
更多详细信息，这些属性[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。