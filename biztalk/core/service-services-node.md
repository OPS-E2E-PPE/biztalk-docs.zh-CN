---
title: 服务 （服务节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Service node [binding file]
ms.assetid: 19e977b4-55bd-453f-9053-5590b9553b07
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 834555f43620d428d18a04938e18612793b2ab51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="service-services-node"></a>服务（“服务”节点）
绑定文件的“服务”节点包含有关随绑定文件导出的服务的信息。 该“服务”节点还包含描述与该服务相关联的端口和角色的多个节点以及描述与该服务相关联的主机的一个节点。  
  
## <a name="nodes-in-the-service-node"></a>Service 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定服务的名称。|必需|默认值：空|  
|State|Attribute|ServiceRefState (SimpleType)|指定服务的状态。|必需|默认值： 默认<br /><br /> 可能的值包括：<br /><br /> 默认<br />-已取消登记<br />-登记<br />启动|  
|TrackingOption|Attribute|OrchestrationTrackingTypes (SimpleType)|指定服务的消息跟踪选项。|必需|默认值：无<br /><br /> 可能的值包括在提供的那些[Microsoft.BizTalk.ExplorerOM.OrchestrationTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.orchestrationtrackingtypes.aspx)枚举。|  
|Description|Attribute|xs:string|为服务指定描述。|可选|默认值：空|  
|[端口](../core/ports-service-node.md)|录制|ArrayOfServicePortRef (ComplexType)|绑定到服务的端口的容器节点。|可选|默认值：无|  
|[Roles](../core/roles-service-node.md)|录制|ArrayOfRoleRef (ComplexType)|绑定到服务的角色的容器节点。|可选|默认值：无|  
|[主机](../core/host-service-node.md)|录制|HostRef (ComplexType)|绑定到服务的主机的容器节点。|必需|默认值：无|