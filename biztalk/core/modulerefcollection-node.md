---
title: ModuleRefCollection 节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ModuleRefCollection node [binding file]
ms.assetid: fa8593bf-6548-4615-9f98-1e0eadde9aa4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 039cabd380195f840e9ffb99de5071026b3810c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="modulerefcollection-node"></a>ModuleRefCollection 节点
绑定文件的 ModuleRefCollection 节是所有 ModuleRef 节点的父节点，ModuleRef 节点包含有关与此绑定文件一起导出的 .NET 程序集的特定信息。  
  
## <a name="entries-in-the-modulerefcollection-section"></a>ModuleRefCollection 节中的项  
 下表列出了可为绑定文件的此节中的节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[ModuleRef](../core/moduleref-modulerefcollection-node.md)|录制|ModuleRef (ComplexType)|与绑定文件一起导出的 .NET 程序集模块的容器节点。|可选|默认值： 无|