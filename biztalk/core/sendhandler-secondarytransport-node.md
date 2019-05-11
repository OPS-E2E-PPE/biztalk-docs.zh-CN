---
title: 发送处理程序 （secondarytransport 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendHandler node [binding file]
ms.assetid: 32eb3e87-25ac-461e-9c09-3d6d9bcba3b2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58ab2b9f2ed41bd3fa132a73e28e38866ef18b53
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254402"
---
# <a name="sendhandler-secondarytransport-node"></a>发送处理程序 （secondarytransport 节点）
绑定文件的 SecondaryTransport 节点的 SendHandler 节点包含有关与绑定文件一起导出的传输相关联的发送处理程序的特定信息。  
  
## <a name="nodes-in-the-sendhandler-node"></a>中的 SendHandler 节点的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|“属性”|特性|xs:string|指定与此传输关联的发送处理程序的名称。|可选|默认值：空|  
|HostTrusted|特性|xs:boolean|指定与发送处理程序关联的主机是否受信任。|Required|默认值：无<br /><br /> 设置为 **，则返回 true**如果受信任主机，否则设置为**false**。|  
|[TransportType（“SendHandler”节点）](../core/transporttype-sendhandler-node.md)|录制|ProtocolType (ComplexType)|指定传输类型，也是与此发送处理程序所用的适配器的名称。|Required|默认值：无|