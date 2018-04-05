---
title: ModuleRef （ModuleRefCollection 节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ModuleRef node [binding file]
ms.assetid: 61787779-33bd-499a-a5c1-c1e0bd306b48
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ed580b022e9896ade824c8cf8eccc2458c7ddce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="moduleref-modulerefcollection-node"></a>ModuleRef （ModuleRefCollection 节点）
绑定文件的 ModuleRef 节点包含有关与该绑定文件一起导出的 .NET 程序集的特定信息。 ModuleRef 节点可以包含但不限于程序集的说明，这些说明包括自定义代码、架构和业务流程。  
  
## <a name="nodes-in-the-moduleref-node"></a>ModuleRef 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[服务](../core/services-moduleref-node.md)|录制|ArrayOfServiceRef (ComplexType)|与此 .NET 程序集关联的服务的容器节点。|可选|默认值：无|  
|[TrackedSchemas （ModuleRef 节点）](../core/trackedschemas-moduleref-node.md)|录制|ArrayOfSchema (ComplexType)|与此 .NET 程序集关联的架构的容器节点。|可选|默认值：无|