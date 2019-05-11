---
title: 错误-所需的目标具有选择源节点 |Microsoft Docs
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
ms.openlocfilehash: a33a5fc9bbcfe44e71b0caab6569279aeb9c32f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388472"
---
# <a name="error---required-target-has-choice-node-source"></a>错误-必需的目标具有选择源节点
**错误代码**  
  
 btm1029  
  
 **说明**  
  
 指定目标架构中所指示的节点为必需，但链接到位于源架构中的节点**选择**节点。 由于源架构中所指示的节点可能会出现在输入的实例消息中，不可能从其在目标架构中创建所需的节点的源。  
  
 **用户执行任何操作**  
  
 根据需要，将目标架构中所指示的节点更改为可选的或者必须在所有有效的输入的实例消息中的目标架构中所指示的节点提供不同的源。