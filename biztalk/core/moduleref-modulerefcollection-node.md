---
title: ModuleRef （ModuleRefCollection 节点） |Microsoft Docs
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
ms.openlocfilehash: 604efe0b0d5d93c6d545b7725d2a0f85609fc32a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394418"
---
# <a name="moduleref-modulerefcollection-node"></a>ModuleRef （ModuleRefCollection 节点）
绑定文件的 ModuleRef 节点包含有关与绑定文件一起导出的.NET 程序集的特定信息。 ModuleRef 节点可以包括但不限于包含自定义代码、 架构和业务流程的程序集的说明。  
  
## <a name="nodes-in-the-moduleref-node"></a>ModuleRef 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[服务](../core/services-moduleref-node.md)|录制|ArrayOfServiceRef (ComplexType)|与此.NET 程序集关联的服务的容器节点。|可选|默认值：无|  
|[TrackedSchemas（ModuleRef 节点）](../core/trackedschemas-moduleref-node.md)|录制|ArrayOfSchema (ComplexType)|与此.NET 程序集相关联的架构的容器节点|可选|默认值：无|