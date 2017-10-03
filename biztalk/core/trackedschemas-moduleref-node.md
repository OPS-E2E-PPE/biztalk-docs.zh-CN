---
title: "TrackedSchemas （ModuleRef 节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TrackedSchemas node [binding file]
ms.assetid: a2b99fbf-df6b-4a94-97b8-ac5eb819604f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 303aeb1ed17b001583a596d5b550faf63ea1200b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="trackedschemas-moduleref-node"></a>TrackedSchemas (ModuleRef 节点)
绑定文件的“TrackedSchemas”节点是所有“架构”节点的父节点，“架构”节点描述了绑定到与绑定文件一起导出的服务的架构。  
  
## <a name="nodes-in-the-trackedschemas-node"></a>TrackedSchemas 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[架构](../core/schema-trackedschemas-node.md)|录制|ArrayOfSchema (ComplexType)|绑定到与绑定文件一起导出的服务的架构的容器节点。|可选|默认值：无|