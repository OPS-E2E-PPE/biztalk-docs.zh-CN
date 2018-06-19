---
title: OutboundTransforms （接收端口节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- OutboundTransforms node [binding file]
ms.assetid: 6deea062-4eb0-47ed-869c-ed6ec9290ea7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc6fa0bc804fad0d0ddea79614c392769452f1c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263861"
---
# <a name="outboundtransforms-receiveport-node"></a>OutboundTransforms （接收端口节点）
绑定文件的 ReceivePort 节点的 OutboundTransforms 节点包含与绑定文件一起导出的双向接收端口的出站转换集合。  
  
## <a name="nodes-in-the-outboundtransforms-node"></a>OutboundTransforms 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[转换 （OutboundTransforms 节点）](../core/transform-outboundtransforms-node.md)|录制|转换 (ComplexType)|指定 BizTalk Server 映射或转换，这是一个表示源架构和目标架构之间的映射项。|可选|默认值：无|