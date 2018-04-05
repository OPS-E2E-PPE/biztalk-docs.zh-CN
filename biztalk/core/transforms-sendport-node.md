---
title: 转换 （发送端口节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transforms node [binding file]
ms.assetid: b405397b-e394-44fa-b507-93896f800f66
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1571a38841f6567279a27c58770f4198ba3eb56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transforms-sendport-node"></a>Transforms（“发送端口”节点）
绑定文件的“发送端口”节点的 Transforms 节点包含随该绑定文件一起导出的单向发送端口的出站转换集合。  
  
## <a name="nodes-in-the-transforms-node"></a>Transforms 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[转换 （发送端口转换节点）](../core/transform-sendport-transforms-node.md)|录制|转换 (ComplexType)|指定 BizTalk Server 映射或转换，这是一个表示源架构和目标架构之间的映射项。|可选|默认值：无|