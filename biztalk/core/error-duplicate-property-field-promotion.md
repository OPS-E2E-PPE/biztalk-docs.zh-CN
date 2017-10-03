---
title: "错误-重复的属性字段升级 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.dupPropFieldPromo
ms.assetid: 59ac55c3-7613-493c-85a3-3965c250a3bb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87d9f6ee346f5aae98ea69c2ce4e00c4fa1d6dbf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---duplicate-property-field-promotion"></a>错误-重复的属性字段升级
**错误代码**  
  
 BEC2016  
  
 **说明**  
  
 此架构中的多个节点将会提升属性字段到同一个**Field 元素**相同的属性架构中的节点。  
  
 **用户执行任何操作**  
  
 使用**属性字段**选项卡**升级属性**对话框中，通过访问**升级属性**属性**架构**节点，删除所有只保留一个具有相同关联的属性字段提升**Field 元素**属性架构中的节点。 你可能想要添加新**Field 元素**属性架构节点以便删除的提升可被重新提升到其自身**Field 元素**节点。