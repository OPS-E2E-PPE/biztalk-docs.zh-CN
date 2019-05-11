---
title: 服务 (服务 Node) |Microsoft Docs
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
ms.openlocfilehash: 03a61ea635d6d781c4bf31a0e598c5d302311db6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393314"
---
# <a name="service-services-node"></a>服务 （服务节点）
绑定文件的服务节点包含有关与绑定文件一起导出的服务的信息。 服务节点还包含描述的端口和与该服务并描述了与服务相关联的主机的节点关联的角色。  
  
## <a name="nodes-in-the-service-node"></a>节点中的服务节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|“属性”|特性|xs:string|指定的服务的名称。|Required|默认值：空|  
|State|特性|ServiceRefState (SimpleType)|指定服务的状态。|Required|默认值：默认<br /><br /> 可能的值包括：<br /><br /> -Default<br />-已取消登记<br />登记<br />-启动|  
|TrackingOption|特性|OrchestrationTrackingTypes (SimpleType)|指定的消息跟踪服务的选项。|Required|默认值：无<br /><br /> 可能的值包括可[Microsoft.BizTalk.ExplorerOM.OrchestrationTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.orchestrationtrackingtypes.aspx)枚举。|  
|Description|特性|xs:string|指定服务的说明。|可选|默认值：空|  
|[端口](../core/ports-service-node.md)|录制|ArrayOfServicePortRef (ComplexType)|绑定到的服务的端口的容器节点。|可选|默认值：无|  
|[Roles](../core/roles-service-node.md)|录制|ArrayOfRoleRef (ComplexType)|绑定到的服务的角色的容器节点。|可选|默认值：无|  
|[主机](../core/host-service-node.md)|录制|HostRef (ComplexType)|绑定到的服务主机的容器节点。|Required|默认值：无|