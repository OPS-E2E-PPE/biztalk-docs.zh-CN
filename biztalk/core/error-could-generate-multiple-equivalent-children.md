---
title: 错误-可能会生成多个等价子节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.couldGenMultipleEquivChildren
ms.assetid: ef3ea6db-6759-4f38-804c-e32a1f24d758
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bfce7d5a5d4db35ae6677d3b45bad4df7842fbf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389216"
---
# <a name="error---could-generate-multiple-equivalent-children"></a>错误-可能会生成多个等价子节点
**错误代码**  
  
 btm1026  
  
 **说明**  
  
 指向目标架构不正确，导致在多个节点**等效**要生成的组节点。  
  
 **用户执行任何操作**  
  
 重新链接到目标架构，可能会使用判断 functoid，因此，只有单个节点内的**等效**组节点可以在映射过程中生成。