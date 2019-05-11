---
title: 错误-多个等价节点相同的目标 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.multipleEquivNodeSameTarget
ms.assetid: d8ca9f94-1d87-41bb-9479-6a01a5b6702d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c4cf66fe587f483385c4729e4c34b0179c1710e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388646"
---
# <a name="error---multiple-equivalent-node-same-target"></a>错误-多个等价节点相同的目标
**错误代码**  
  
 btm1025  
  
 **说明**  
  
 在指定的节点在源架构中，这是冲突子节点的**等效**组节点，都链接到目标架构中所指示的节点。 仅有一个源架构中节点可以出现在给定的实例消息中。  
  
 **用户执行任何操作**  
  
 确保只有一个子节点**等效**组节点连接到目标架构中的给定节点。