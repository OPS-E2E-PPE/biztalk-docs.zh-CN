---
title: 错误-多个输入但不存在循环 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.multipleInputsWithoutLooping
ms.assetid: 7e55ad22-06a8-4a56-839d-a30b82819a68
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ce2cdef2a80e6e58b635cf9fed0dbc52c817e0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347315"
---
# <a name="error---multiple-inputs-without-looping"></a>错误-多个输入但不存在循环
**错误代码**  
  
 btm1004  
  
 **说明**  
  
 多个链接连接到所指示的节点在目标架构中，当连接到所指示的节点的祖先节点之一时才有效**循环**functoid。  
  
 **用户执行任何操作**  
  
 一个指向目标架构中所指示的节点的删除，或者将所指示的节点的祖先节点之一连接到循环 functoid。