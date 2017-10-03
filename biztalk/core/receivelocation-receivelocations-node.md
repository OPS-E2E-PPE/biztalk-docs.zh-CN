---
title: "接收位置 （接收位置节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ReceiveLocation node [binding file]
ms.assetid: 706ec5b2-c26f-428a-ad56-1c01b34aa8f8
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f959dfc9aadfbf317d3843fb0ed174a2a0f22ea3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receivelocation-receivelocations-node"></a>ReceiveLocation（ReceiveLocations 节点）
绑定文件的 ReceiveLocations 节点的 ReceiveLocation 节点包含与绑定文件一起导出的接收位置有关的信息。  
  
## <a name="nodes-in-the-receivelocation-node"></a>ReceiveLocation 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定接收位置的名称。|可选|默认值：空|  
|Description|元素|xs:string|指定接收位置的说明。|必需|默认值：空|  
|Address|元素|xs:string|指定接收位置的地址。|必需|默认值：空|  
|PublicAddress|元素|xs:string|指定接收位置的公用地址。|可选|默认值：空|  
|主|元素|xs:boolean|指定接收位置是否为主接收位置。|必需|默认值：无|  
|ReceiveLocationServiceWindowEnabled|元素|xs:boolean|指定是否启用服务时段。|必需|默认值：无<br /><br /> 指定**true**如果启用了服务窗口; 否则，指定**false。**|  
|ReceiveLocationFromTime|元素|xs:dateTime|指定服务时段的开始的时间。|必需|默认值：无|  
|ReceiveLocationToTime|元素|xs:dateTime|指定服务时段的结束时间。|必需|默认值：无|  
|ReceiveLocationStartDateEnabled|元素|xs:boolean|指定是否启用服务时段的开始日期。|必需|默认值：无|  
|ReceiveLocationStartDate|元素|xs:dateTime|指定服务时段的开始日期。|必需|默认值：无|  
|ReceiveLocationEndDateEnabled|元素|xs:boolean|指定是否启用服务时段的结束日期。|必需|默认值：无|  
|ReceiveLocationEndDate|元素|xs:dateTime|指定服务时段的结束日期。|必需|默认值：无|  
|[ReceiveLocationTransportType](../core/receivelocationtransporttype-receivelocation-node.md)|录制|ProtocolType (ComplexType)|指定此接收位置的传输类型。|必需|默认值：无|  
|ReceiveLocationTransportTypeData|元素|xs:string|指定此接收位置的传输类型属性。|可选|默认值：空<br /><br /> 请参阅[集成 BizTalk 适配器的配置属性](../core/configuration-properties-for-integrated-biztalk-adapters.md)适配器可以存储在此字符串的属性有关的特定信息。|  
|[ReceivePipeline](../core/receivepipeline-receivelocation-node.md)|录制|PipelineRef (ComplexType)|指定此接收位置的接收管道。|必需|默认值：无|  
|ReceivePipelineData|元素|xs:string|指定特定于用于此接收位置的接收管道的自定义配置。|必需|默认值：空|  
|[发送管道](../core/sendpipeline-receivelocation-node.md)|录制|PipelineRef (ComplexType)|指定双向接收位置的发送管道。 **注意：**中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送在接收位置而不接收端口指定管道的双向接收。 除非在绑定文件中具体指定，否则，接收位置将自动继承它所属于的接收端口的发送管道。|必需|默认值：无|  
|SendPipelineData|元素|xs:string|指定特定于用于此接收位置的发送管道的自定义配置。|必需|默认值：空|  
|[EncryptionCert](../core/encryptioncert-receivelocation-node.md)|录制|CertificateInfo (ComplexType)|指定与接收端口位置的加密证书。|可选|默认值：无|  
|启用|元素|xs:boolean|指定是否启用接收位置。|必需|默认值：无|  
|[接收处理程序](../core/receivehandler-receivelocation-node.md)|录制|ReceiveHandlerRef (ComplexType)|指定要用于此接收位置的接收处理程序。|可选|默认值：无|