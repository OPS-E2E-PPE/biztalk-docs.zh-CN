---
title: 错误-必填字段都没有输入 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.reqdFieldHasNoInput
ms.assetid: 2454baf8-aa28-4b7b-93cd-aab9afc63823
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f7443efd49c5d5375b025fd4fcf93f60d253d4b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346980"
---
# <a name="error---required-field-has-no-input"></a>错误-必填的字段具有任何输入
**错误代码**  
  
 btm1028  
  
 **说明**  
  
 目标架构中所指示的节点被指定为必需节点，但当前未提供任何传入链接、常数值或默认值，因此此映射生成的输出实例消息中将不包含该节点。  
  
 **用户执行任何操作**  
  
 根据需要，将目标架构中所指示的节点更改为可选节点，或为该节点提供传入链接、常数值或默认值。