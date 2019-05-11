---
title: 警告-字段数据类型不匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.fieldDataTypeMismatch
ms.assetid: 0c15d926-1d05-404b-bb16-a5fe8bc3575d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50d74dfb16dbd03eb92e6880681721608389840a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393679"
---
# <a name="warning---field-data-type-mismatch"></a>警告-字段数据类型不匹配
**错误代码**  
  
 BEC1002  
  
 **说明**  
  
 **数据类型**找到所指示的节点属性不同于**数据类型**属性**字段元素**它将被提升到中的节点相应属性架构。 在架构中节点的数据类型应与分配给数据类型匹配**Field 元素**节点用于其属性字段升级，或至少，应分配的数据类型映射到相同的公共语言运行时 (CLR) 类型。  
  
 **用户执行任何操作**  
  
 更改**数据类型**所指示的节点的属性和**Field 元素**它将被提升到相同的数据节点键入值，或至少对数据类型值映射到相同的 CLR 数据类型。