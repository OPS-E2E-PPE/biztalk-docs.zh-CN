---
title: 发送处理程序 （PrimaryTransport 节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendHandler node [binding file]
ms.assetid: c0b200ee-ecbc-4708-a2c8-c37cd6cd0060
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 029285e9b56aeb91bbca7a7c9eacf6abedc7ebbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270525"
---
# <a name="sendhandler-primarytransport-node"></a>SendHandler（PrimaryTransport 节点）
绑定文件的“PrimaryTransport”节点的“SendHandler”节点包含有关发送处理程序的特定信息，该处理程序与随同绑定文件一起导出的传输相关联。  
  
## <a name="nodes-in-the-sendhandler-node"></a>发送处理程序节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定发送处理程序与传输相关联的名称。|可选|默认值：空|  
|HostTrusted|Attribute|xs:boolean|指定与发送处理程序关联的主机是否为受信任。|必需|默认值：无<br /><br /> 设置为**true**如果主机是受信任，否则设置为**false**。|  
|[TransportType](../core/transporttype.md)|录制|ProtocolType (ComplexType)|指定的传输类型，它也是用于此发送处理程序适配器的名称。|必需|默认值：无|