---
title: 接收处理程序 （ReceiveLocation 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceiveHandler node [binding file]
ms.assetid: dd105052-ec71-4762-aa74-e8cdb806a6bf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e04d45b94641703b045a3d3d8d571d7586424c57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398163"
---
# <a name="receivehandler-receivelocation-node"></a>接收处理程序 （ReceiveLocation 节点）
绑定文件的 ReceiveLocation 节点的 ReceiveHandler 节点包含有关与绑定文件一起导出的传输相关联的接收处理程序的特定信息。  
  
## <a name="nodes-in-the-receivehandler-node"></a>节点中的 ReceiveHandler 节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|“属性”|特性|xs:string|指定与此传输关联的接收处理程序的名称。|可选|默认值：空|  
|HostTrusted|特性|xs:boolean|指定与接收处理程序相关联的主机是否受信任。|Required|默认值：无<br /><br /> 设置为 **，则返回 true**如果受信任主机，否则设置为**false**。|  
|[TransportType（“ReceiveHandler”节点）](../core/transporttype-receivehandler-node.md)|录制|ProtocolType (ComplexType)|指定传输类型，同时也是使用与此适配器的名称的接收处理程序。|Required|默认值：无|