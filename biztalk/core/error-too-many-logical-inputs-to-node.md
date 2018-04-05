---
title: 错误-节点的太多逻辑输入 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tooManyLogicalInputsToNode
ms.assetid: 9295d6a2-702d-4cf3-8f5d-26ba63b9fce0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e363d79a2b013b8e90533c4e6e36cff5b5798b77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---too-many-logical-inputs-to-node"></a>错误-节点的逻辑输入太多
**错误代码**  
  
 btm1006  
  
 **说明**  
  
 有更多的逻辑链接连接到比数输入指向目标架构中的指定节点**循环**functoid 连接到指定的节点的祖先节点。 前一类型和后一类型的链接数应该一致。  
  
 **用户执行任何操作**  
  
 链接数连接到指定的节点和返工**循环**functoid 连接到祖先节点以便将它们与匹配。