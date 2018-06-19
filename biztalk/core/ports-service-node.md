---
title: 端口 （服务节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Ports node [binding file]
ms.assetid: 498d4310-4e9e-4e74-bc3d-5cbf1319c4ff
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31e09470b9f3287cce5ce15c2941d2165157ec48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263453"
---
# <a name="ports-service-node"></a>端口 （服务节点）
绑定文件的“Ports”节点是所有端口节点的父节点，端口节点包含与各个端口（这些端口绑定到与绑定文件一起导出的服务）有关的特定信息。  
  
## <a name="node-in-the-ports-node"></a>“Ports”节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[端口](../core/port-ports-node.md)|录制|ServicePortRef (ComplexType)|指定绑定到与绑定文件一起导出的服务的端口有关的信息。|可选|默认值：无|