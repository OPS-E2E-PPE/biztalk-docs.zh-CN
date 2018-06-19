---
title: 错误-多个循环路径 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.multipleLoopPaths
ms.assetid: 3f7c0c1c-5aaa-4da9-99ab-78bac536b8dd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afdcb1a235c71163552fd5f6b255e572feef8dc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241085"
---
# <a name="error---multiple-loop-paths"></a>错误-多个循环路径
**错误代码**  
  
 btm1030  
  
 **说明**  
  
 目标架构中所指示的节点包含多个源循环路径。  
  
 **用户执行任何操作**  
  
 使用**循环**functoid 来显式指定源架构对其将执行循环中的节点。