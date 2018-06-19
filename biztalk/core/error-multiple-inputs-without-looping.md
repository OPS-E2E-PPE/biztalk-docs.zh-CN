---
title: 错误-但不存在循环的多个输入 |Microsoft 文档
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
ms.openlocfilehash: 93a8a11b25c3c1df52827bdbf4098f0cd37bdd8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240501"
---
# <a name="error---multiple-inputs-without-looping"></a>错误-但不存在循环的多个输入
**错误代码**  
  
 btm1004  
  
 **说明**  
  
 多个链接连接到指定的节点在目标架构中，当连接到指定的节点的祖先节点之一时才有效**循环**functoid。  
  
 **用户执行任何操作**  
  
 只保留指向目标架构中所指示节点的一个链接，删除其他链接，或者将所指示节点的一个祖先节点连接到“循环”functoid。