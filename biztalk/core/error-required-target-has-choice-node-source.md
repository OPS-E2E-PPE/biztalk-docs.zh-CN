---
title: 错误-所需的目标具有选择源节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.reqdTargetHasChoiceNodeSource
ms.assetid: 5b5af999-d100-4e5d-a959-c8b11d574d3b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91c9ad912b03bbb475efcc9eb8207a388400b43b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---required-target-has-choice-node-source"></a>错误-必需的目标具有选择源节点
**错误代码**  
  
 btm1029  
  
 **说明**  
  
 指定目标架构中指定的节点作为所需但链接到位于源架构中的节点**选择**节点。 由于源架构中指定的节点不应出现在输入的实例消息，不可能从其目标架构中创建所需的节点的源。  
  
 **用户执行任何操作**  
  
 根据需要，将目标架构中的指定的节点更改为可选的或者为必须出现在所有有效输入的实例消息的目标架构中的指定节点提供不同的源。