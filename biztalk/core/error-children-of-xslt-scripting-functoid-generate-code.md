---
title: 错误-的 XSLT 脚本 Functoid 子级生成代码 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.xsltScriptingChildrenGenCode
ms.assetid: 9cdac362-177f-445e-904b-aa6a9b1eb46f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 810fe9befecd9bbd1a15468ca714177900450cb7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239549"
---
# <a name="error---children-of-xslt-scripting-functoid-generate-code"></a>错误-的 XSLT 脚本 Functoid 子级生成代码
**错误代码**  
  
 btm1063  
  
 **说明**  
  
 这不符合的使用方案**脚本**配置为使用内联 XSLT 或 XSLT 调用模板的 functoid 找映射中。 在目标架构中，链接到此类的输出的节点的子代节点**脚本**functoid 尝试生成其自己的 XSLT 代码。  
  
 **用户执行任何操作**  
  
 通过更改相关的使用情况删除不兼容性**脚本**functoid 或更改的子节点，以便它们不会再生成它们自己的 XSLT 代码。