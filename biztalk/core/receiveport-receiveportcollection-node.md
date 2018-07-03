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
ms.openlocfilehash: 6b8e30a789327f872e384152d64a2edbebb4b9dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023155"
---
# <a name="receiveport-receiveportcollection-node"></a>接收端口 （ReceivePortCollection 节点）
绑定文件的 ReceivePortCollection 节点的 ReceivePort 节点包含与该绑定文件一起导出的接收端口有关的信息。  

## <a name="nodes-in-the-receiveport-node"></a>ReceivePort 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  


|                                      **名称**                                       | **节点类型** |            **数据类型**             |                                               **Description**                                               | **限制** |                                                                                                 **注释**                                                                                                  |
|-------------------------------------------------------------------------------------|---------------|--------------------------------------|-------------------------------------------------------------------------------------------------------------|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                        “属性”                                         |   Attribute   |              xs:string               |                                   指定接收端口的名称。                                   |   可选   |                                                                                             默认值：空                                                                                              |
|                                      IsTwoWay                                       |   Attribute   |              xs:boolean              |               指定接收端口是单向的还是请求-响应的（双向）。               |     Required     |      默认值：无<br /><br /> 在可能的值为**MSBTS_SendPort.IsTwoWay 属性 (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]      |
|                                    BindingOption                                    |   Attribute   |                xs:int                |                          指定业务流程端口的绑定类型。                          |     Required     |                                             默认值：无<br /><br /> 可能的值位于**Microsoft.BizTalk.ExplorerOM.BindingType**枚举。                                              |
|                                     Description                                     |    元素    |              xs:string               |                                指定接收端口的说明。                                |     Required     |                                                                                             默认值：空                                                                                              |
|          [ReceiveLocations](../core/receivelocations-receiveport-node.md)           |    录制     | ArrayOfReceiveLocation (ComplexType) |                 与此接收端口关联的接收位置的容器节点。                 |  不是必需的。   |                                                                                              默认值：无                                                                                              |
| [TransmitPipeline（“ReceivePort”节点）](../core/transmitpipeline-receiveport-node.md) |    录制     |      PipelineRef (ComplexType)       | 指定在接收端口为双向接收端口时与接收端口关联的发送管道。 |   可选   |                                                                                              默认值：无                                                                                              |
|                                  SendPipelineData                                   |    元素    |              xs:string               |         指定特定于此管道使用实例的自定义配置。          |   可选   |                                                                                             默认值： 空。                                                                                             |
|                                   身份验证                                    |    元素    |                xs:int                |      指定一个枚举值，该值指示在此接收端口是否需要身份验证。       |     Required     |                                          默认值：无<br /><br /> 可能的值位于**Microsoft.BizTalk.ExplorerOM.AuthenticationType**枚举。                                          |
|                                      跟踪                                       |    元素    |                xs:int                |                        指定接收端口的文档跟踪级别。                        |     Required     |                                            默认值：无<br /><br /> 可能的值位于**Microsoft.BizTalk.ExplorerOM.TrackingTypes**枚举。                                             |
|       [Transforms（“ReceivePort”节点）](../core/transforms-receiveport-node.md)       |    录制     |    ArrayOfTransform (ComplexType)    |                  指定单向接收端口的入站转换的集合。                  |   可选   |                                                                                              默认值：无                                                                                              |
|        [OutboundTransforms](../core/outboundtransforms-receiveport-node.md)         |    录制     |    ArrayOfTransform (ComplexType)    |       指定要应用于双向接收端口上的文档的出站转换的集合       |   可选   |                                                                                              默认值：无                                                                                              |
|                                 RouteFailedMessage                                  |    元素    |              xs:boolean              |             指定是否将失败的消息路由到失败消息订户。              |     Required     | 默认值：无<br /><br /> 在可能的值为**MSBTS_SendPort.RouteFailedMessage 属性 (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] |
|                                   ApplicationName                                   |    元素    |              xs:string               |                   指定与接收端口关联的应用程序的名称。                   |     Required     |           默认值：空<br /><br /> 在可能的值为**ISSOMapping 接口 (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]           |

