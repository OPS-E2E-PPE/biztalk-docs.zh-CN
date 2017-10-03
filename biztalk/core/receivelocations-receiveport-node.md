---
title: "接收位置 （接收端口节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ReceiveLocations node [binding file]
ms.assetid: c12acc1b-f8fe-4a27-8386-d9f4f4455e3f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c9fb5b64466e32ae27d53852b3383eb79531d60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receivelocations-receiveport-node"></a>ReceiveLocations（ReceivePort 节点）
绑定文件的 ReceivePort 节点的 ReceiveLocations 节点是所有 ReceiveLocation 节点的父节点，ReceiveLocation 节点包含有关与此绑定文件一起导出的接收位置的特定信息。  
  
## <a name="nodes-in-the-receivelocations-node"></a>ReceiveLocations 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[接收位置](../core/receivelocation-receivelocations-node.md)|录制|ReceiveLocation (ComplexType)|指定与绑定文件一起导出的接收位置有关的信息。|可选|默认值：无|