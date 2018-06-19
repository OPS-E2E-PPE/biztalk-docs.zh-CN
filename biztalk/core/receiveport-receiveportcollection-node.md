---
title: 接收端口 （ReceivePortCollection 节点） |Microsoft 文档
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
ms.openlocfilehash: da486df8bf406ca61f0b06d2cbc6f9b3f16539cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269029"
---
# <a name="receiveport-receiveportcollection-node"></a>接收端口 （ReceivePortCollection 节点）
绑定文件的 ReceivePortCollection 节点的 ReceivePort 节点包含与该绑定文件一起导出的接收端口有关的信息。  
  
## <a name="nodes-in-the-receiveport-node"></a>ReceivePort 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定接收端口的名称。|可选|默认值：空|  
|IsTwoWay|Attribute|xs:boolean|指定接收端口是单向的还是请求-响应的（双向）。|必需|默认值：无<br /><br /> 可能的值位于**MSBTS_SendPort.IsTwoWay 属性 (WMI)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]|  
|BindingOption|Attribute|xs:int|指定业务流程端口的绑定类型。|必需|默认值：无<br /><br /> 可能的值位于**Microsoft.BizTalk.ExplorerOM.BindingType**枚举。|  
|Description|元素|xs:string|指定接收端口的说明。|必需|默认值：空|  
|[接收位置](../core/receivelocations-receiveport-node.md)|录制|ArrayOfReceiveLocation (ComplexType)|与此接收端口关联的接收位置的容器节点。|不是必需的。|默认值：无|  
|[TransmitPipeline （接收端口节点）](../core/transmitpipeline-receiveport-node.md)|录制|PipelineRef (ComplexType)|指定在接收端口为双向接收端口时与接收端口关联的发送管道。|可选|默认值：无|  
|SendPipelineData|元素|xs:string|指定特定于此管道使用实例的自定义配置。|可选|默认值： 空。|  
|身份验证|元素|xs:int|指定一个枚举值，该值指示在此接收端口是否需要身份验证。|必需|默认值：无<br /><br /> 可能的值位于**Microsoft.BizTalk.ExplorerOM.AuthenticationType**枚举。|  
|跟踪|元素|xs:int|指定接收端口的文档跟踪级别。|必需|默认值：无<br /><br /> 可能的值位于**Microsoft.BizTalk.ExplorerOM.TrackingTypes**枚举。|  
|[转换 （接收端口节点）](../core/transforms-receiveport-node.md)|录制|ArrayOfTransform (ComplexType)|指定单向接收端口的入站转换的集合。|可选|默认值：无|  
|[OutboundTransforms](../core/outboundtransforms-receiveport-node.md)|录制|ArrayOfTransform (ComplexType)|指定要应用于双向接收端口上的文档的出站转换的集合|可选|默认值：无|  
|RouteFailedMessage|元素|xs:boolean|指定是否将失败的消息路由到失败消息订户。|必需|默认值：无<br /><br /> 可能的值位于**MSBTS_SendPort.RouteFailedMessage 属性 (WMI)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]|  
|ApplicationName|元素|xs:string|指定与接收端口关联的应用程序的名称。|必需|默认值：空<br /><br /> 可能的值位于**ISSOMapping 接口 (COM)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]|