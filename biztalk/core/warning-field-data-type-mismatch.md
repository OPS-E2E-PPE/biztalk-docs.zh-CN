---
title: 警告-字段数据类型不匹配 |Microsoft 文档
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
ms.openlocfilehash: af42f5c921333e34c9ee219020cdb0fba97a7b5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288165"
---
# <a name="warning---field-data-type-mismatch"></a>警告-字段数据类型不匹配
**错误代码**  
  
 BEC1002  
  
 **说明**  
  
 **数据类型**找到指定的节点的属性不同于**数据类型**属性**Field 元素**它将被提升到中的节点相应的属性架构。 架构中的节点的数据类型应与分配给数据类型匹配**Field 元素**节点用于其属性字段提升，或至少应分配的数据类型映射到相同的公共语言运行时 (CLR) 类型。  
  
 **用户执行任何操作**  
  
 更改**数据类型**指示节点的属性和**Field 元素**它将被提升到相同的数据的节点键入值，或至少为数据类型值映射到相同的 CLR 数据类型。