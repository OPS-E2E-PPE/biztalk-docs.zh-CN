---
title: Mapping （Mappings 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Mapping node [binding file]
ms.assetid: bc54c476-505c-4020-b7df-1d19f86329aa
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e227dd0c22734e0d448aebc0bbf4a8960575a5e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325669"
---
# <a name="mapping-mappings-node"></a>Mapping （Mappings 节点）
绑定文件的 Mapping 节点描述了参与方端口和角色端口类型操作登记的参与方之间的映射。  
  
## <a name="nodes-in-the-mapping-node"></a>在映射节点的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|PortTypeName|特性|xs:string|指定端口类型的名称。|可选|默认值：空|  
|OperationName|特性|xs:string|指定属于此端口类型操作。|可选|默认值：空|  
|[SendPortRef](../core/sendportref-mapping-node.md)|录制|SendPortRef (ComplexType)|与映射关联的发送端口的列表的容器节点。|可选|默认值：无|