---
title: ModuleRefCollection 节点 |Microsoft Docs
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
ms.openlocfilehash: 2a8f756d15e7b4dd88029ad169d5aac66e894aff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324504"
---
# <a name="modulerefcollection-node"></a>ModuleRefCollection 节点
绑定文件的 ModuleRefCollection 节是所有 ModuleRef 节点包含有关与绑定文件一起导出的.NET 程序集的特定信息的父节点。  
  
## <a name="entries-in-the-modulerefcollection-section"></a>ModuleRefCollection 节中的项  
 下表列出了可以在此部分中的绑定文件中为节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[ModuleRef](../core/moduleref-modulerefcollection-node.md)|录制|ModuleRef (ComplexType)|与绑定文件一起导出的.NET 程序集模块的容器节点。|可选|默认值：None|