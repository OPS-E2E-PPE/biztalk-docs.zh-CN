---
title: "接收处理程序 （接收位置节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ReceiveHandler node [binding file]
ms.assetid: dd105052-ec71-4762-aa74-e8cdb806a6bf
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e865886624731414f979c77f3f2e898e417c8b11
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receivehandler-receivelocation-node"></a>接收处理程序 （接收位置节点）
绑定文件的 ReceiveLocation 节点的 ReceiveHandler 节点包含有关接收处理程序的特定信息，该接收处理程序与随同该绑定文件一起导出的传输相关联。  
  
## <a name="nodes-in-the-receivehandler-node"></a>ReceiveHandler 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定与传输关联的接收处理程序的名称。|可选|默认值：空|  
|HostTrusted|Attribute|xs:boolean|指定与此接收处理程序关联的主机是否可信任。|必需|默认值：无<br /><br /> 设置为**true**如果主机是受信任，否则设置为**false**。|  
|[TransportType （接收处理程序节点）](../core/transporttype-receivehandler-node.md)|录制|ProtocolType (ComplexType)|指定传输类型，同时也是与此接收处理程序一同使用的适配器的名称。|必需|默认值：无|