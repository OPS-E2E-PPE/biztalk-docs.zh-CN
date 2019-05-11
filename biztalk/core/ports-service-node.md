---
title: 端口 （服务节点） |Microsoft Docs
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
ms.openlocfilehash: e8c7c160529b23a66d2c7cb444908adbaff13184
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394814"
---
# <a name="ports-service-node"></a>端口 （服务节点）
绑定文件的端口节点是所有端口节点包含有关绑定到与绑定文件一起导出的服务的端口的特定信息的父节点。  
  
## <a name="node-in-the-ports-node"></a>在端口节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[端口](../core/port-ports-node.md)|录制|ServicePortRef (ComplexType)|指定有关绑定到与绑定文件一起导出的服务的端口信息。|可选|默认值：无|