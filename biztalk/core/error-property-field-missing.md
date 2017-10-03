---
title: "错误-缺少属性字段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.propFieldMissing
ms.assetid: 8d07e72b-f876-4a37-8c95-ec7aa0033983
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d77311e4c8585cfb7f6108364e6a5085619595a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---property-field-missing"></a>错误-缺少属性字段
**错误代码**  
  
 BEC2008  
  
 **说明**  
  
 此架构中的指定的节点提升为**Field 元素**不存在的属性对应的架构中的节点。 可能会发生此问题时**Field 元素**节点被删除，或重命名，属性架构作为属性提升的目标用完之后。  
  
 **用户执行任何操作**  
  
 请修改属性架构，以使其包含缺少**Field 元素**节点或使用**升级属性**对话框中删除，或者修改相关属性提升。