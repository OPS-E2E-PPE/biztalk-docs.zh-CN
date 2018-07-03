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
ms.openlocfilehash: c948ab5d288a714e790b22d7e79e5256094f08f9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008542"
---
# <a name="sendport-sendportcollection-node"></a>发送端口 （SendPortCollection 节点）
绑定文件的“发送端口”节点包含有关通过绑定文件导出的发送端口的特定信息。  

## <a name="nodes-in-the-sendport-node"></a>“发送端口”节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  


|                                   **名称**                                    | **节点类型** |         **数据类型**          |                                       **Description**                                        | **限制** |                                                                                            **注释**                                                                                             |
|-------------------------------------------------------------------------------|---------------|--------------------------------|----------------------------------------------------------------------------------------------|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                     “属性”                                      |   Attribute   |           xs:string            |                             指定发送端口的名称。                             |   可选   |                                                                                        默认值：空                                                                                         |
|                                   IsStatic                                    |   Attribute   |           xs:boolean           |                    指定发送端口是静态的还是动态的。                     |     Required     |                                                                                         默认值：无                                                                                         |
|                                   IsTwoWay                                    |   Attribute   |           xs:boolean           |         指定发送端口是单向的还是要求-响应的（双向的）。         |     Required     |                                               默认值：无<br /><br /> 可能的值位于**MSBTS_SendPort.IsTwoWay 属性 (WMI)**。                                                |
|                                 BindingOption                                 |   Attribute   |             xs:int             |                  指定业务流程端口的绑定类型。                   |     Required     |                                        默认值：无<br /><br /> 可能的值位于**Microsoft.BizTalk.ExplorerOM.BindingType**枚举。                                        |
|                                  Description                                  |    元素    |           xs:string            |                          指定发送端口的说明。                          |     Required     |                                                                                        默认值：空                                                                                         |
| [TransmitPipeline（SendPort 节点）](../core/transmitpipeline-sendport-node.md) |    录制     |   PipelineRef (ComplexType)    |                  指定与发送端口关联的发送管道。                  |   可选   |                                                                                         默认值：无                                                                                         |
|                               SendPipelineData                                |    元素    |           xs:string            |  指定特定于此管道使用实例的自定义配置。  |   可选   |                                                                                        默认值： 空。                                                                                        |
|         [PrimaryTransport](../core/primarytransport-sendport-node.md)         |    录制     |  TransportInfo (ComplexType)   |  指定有关发送端口配置使用的主传输的信息。  |   可选   |                                                                                         默认值：无                                                                                         |
|       [SecondaryTransport](../core/secondarytransport-sendport-node.md)       |    录制     |  TransportInfo (ComplexType)   | 指定有关发送端口配置使用的辅助传输的信息。 |   可选   |                                                                                         默认值：无                                                                                         |
|           [EncryptionCert](../core/encryptioncert-sendport-node.md)           |    录制     | CertificateInfo (ComplexType)  |       指定有关用于发送端口的加密证书的信息。        |   可选   |                                                                                         默认值：无                                                                                         |
|          [ReceivePipeline](../core/receivepipeline-sendport-node.md)          |    录制     |   PipelineRef (ComplexType)    |          指定有关用于发送端口的所有接收管道的信息。          |   可选   |                                                                                         默认值：无                                                                                         |
|                              ReceivePipelineData                              |    元素    |           xs:string            |  指定特定于此管道使用实例的自定义配置。  |     Required     |                                                                                        默认值：空                                                                                         |
|                                   跟踪                                    |    元素    |             xs:int             |                  指定发送端口的文档跟踪级别。                  |     Required     |                                       默认值：无<br /><br /> 可能的值位于**Microsoft.BizTalk.ExplorerOM.TrackingTypes**枚举。                                       |
|                                    “筛选器”                                     |    元素    |           xs:string            |         指定此发送端口中使用的可选筛选器表达式的名称。         |     Required     |                                                默认值：空<br /><br /> 在可能的值为**MSBTS_SendPort.Filter 属性 (WMI)**                                                 |
|       [Transforms（SendPort 节点）](../core/transforms-sendport-node.md)       |    录制     | ArrayOfTransform (ComplexType) |           指定单向发送端口出站转换的集合。            |   可选   |                                                                                         默认值：无                                                                                         |
|        [InboundTransforms](../core/inboundtransforms-sendport-node.md)        |    录制     | ArrayOfTransform (ComplexType) |            指定双向发送端口入站转换的集合。            |   可选   |                                                                                         默认值：无                                                                                         |
|                                OrderedDelivery                                |    元素    |           xs:boolean           |           指定发送端口是否按序传送消息。            |     Required     |                                            默认值：无<br /><br /> 在可能的值为**MSBTS_SendPort.OrderedDelivery 属性 (WMI)**                                            |
|                                   Priority                                    |    元素    |             xs:int             |                           指定发送端口的优先级。                           |     Required     |                                                 默认值： 5<br /><br /> 在可能的值为**MSBTS_SendPort.Priority 属性 (WMI)**                                                  |
|                             StopSendingOnFailure                              |    元素    |           xs:boolean           |         指定发送端口在发送失败时是否停止发送消息。          |     Required     |                                          默认值：无<br /><br /> 在可能的值为**MSBTS_SendPort.StopSendingOnFailure 属性 (WMI)**                                          |
|                              RouteFailedMessage                               |    元素    |           xs:boolean           |      指定是否将失败的消息路由到失败消息订户。      |     Required     |                                           默认值：无<br /><br /> 在可能的值为**MSBTS_SendPort.RouteFailedMessage 属性 (WMI)**                                           |
|                                ApplicationName                                |    元素    |           xs:string            |             指定与发送端口关联的应用程序的名称。             |     Required     | 默认值：空<br /><br /> 可能的值位于**ISSOMapping.ApplicationName 属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 |

## <a name="see-also"></a>另请参阅
更多详细信息，这些属性[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。