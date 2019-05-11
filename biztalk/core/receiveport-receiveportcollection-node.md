---
title: 接收端口 （ReceivePortCollection 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30ae9cef-4e0f-42ca-ac45-fe1fabdfc7c5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62a81974d083dc70201e566759f102b3151607de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398126"
---
# <a name="receiveport-receiveportcollection-node"></a>接收端口 （ReceivePortCollection 节点）
绑定文件的 ReceivePortCollection 节点的 ReceivePort 节点包含随绑定文件一起导出的接收端口有关的特定信息。  

## <a name="nodes-in-the-receiveport-node"></a>节点中的 ReceivePort 节点  
 下表列出了可为绑定文件的此节点设置的属性：  


|                                      **名称**                                       | **节点类型** |            **数据类型**             |                                               **说明**                                               | **限制** |                                                                                                 **注释**                                                                                                  |
|-------------------------------------------------------------------------------------|---------------|--------------------------------------|-------------------------------------------------------------------------------------------------------------|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                        “属性”                                         |   特性   |              xs:string               |                                   指定的接收端口的名称。                                   |   可选   |                                                                                             默认值：空                                                                                              |
|                                      IsTwoWay                                       |   特性   |              xs:boolean              |               指定接收端口是单向还是请求-响应 （双向）。               |     Required     |      默认值：无<br /><br /> 在可能的值为**MSBTS_SendPort.IsTwoWay 属性 (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]      |
|                                    BindingOption                                    |   特性   |                xs:int                |                          指定业务流程端口绑定的类型。                          |     Required     |                                             默认值：无<br /><br /> 可能的值位于**Microsoft.BizTalk.ExplorerOM.BindingType**枚举。                                              |
|                                     Description                                     |    元素    |              xs:string               |                                指定接收端口的说明。                                |     Required     |                                                                                             默认值：空                                                                                              |
|          [ReceiveLocations](../core/receivelocations-receiveport-node.md)           |    录制     | ArrayOfReceiveLocation (ComplexType) |                 与此接收端口关联的接收位置的容器节点。                 |  不是必需的。   |                                                                                              默认值：无                                                                                              |
| [TransmitPipeline（“ReceivePort”节点）](../core/transmitpipeline-receiveport-node.md) |    录制     |      PipelineRef (ComplexType)       | 指定双向接收端口的接收端口是否与接收端口相关联的发送管道。 |   可选   |                                                                                              默认值：无                                                                                              |
|                                  SendPipelineData                                   |    元素    |              xs:string               |         指定管道的特定于此实例的使用情况的自定义配置。          |   可选   |                                                                                             默认值： 空。                                                                                             |
|                                   身份验证                                    |    元素    |                xs:int                |      指定枚举值，该值指示是否需要身份验证在此接收端口。       |     Required     |                                          默认值：无<br /><br /> 可能的值位于**Microsoft.BizTalk.ExplorerOM.AuthenticationType**枚举。                                          |
|                                      跟踪                                       |    元素    |                xs:int                |                        指定文档的接收端口跟踪的级别。                        |     Required     |                                            默认值：无<br /><br /> 可能的值位于**Microsoft.BizTalk.ExplorerOM.TrackingTypes**枚举。                                             |
|       [Transforms（“ReceivePort”节点）](../core/transforms-receiveport-node.md)       |    录制     |    ArrayOfTransform (ComplexType)    |                  指定接收端口的一种方法的入站转换集合。                  |   可选   |                                                                                              默认值：无                                                                                              |
|        [OutboundTransforms](../core/outboundtransforms-receiveport-node.md)         |    录制     |    ArrayOfTransform (ComplexType)    |       指定要将应用于文档上的双向的出站转换集合接收端口       |   可选   |                                                                                              默认值：无                                                                                              |
|                                 RouteFailedMessage                                  |    元素    |              xs:boolean              |             指定失败消息路由到失败的消息订户。              |     Required     | 默认值：无<br /><br /> 在可能的值为**MSBTS_SendPort.RouteFailedMessage 属性 (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] |
|                                   ApplicationName                                   |    元素    |              xs:string               |                   指定与接收端口关联的应用程序的名称。                   |     Required     |           默认值：空<br /><br /> 在可能的值为**ISSOMapping 接口 (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]           |

