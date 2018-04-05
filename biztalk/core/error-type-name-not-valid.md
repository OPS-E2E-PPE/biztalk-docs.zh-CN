---
title: 错误-不是有效的类型名称 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.typeNameNotValid
ms.assetid: 4c9bceeb-b009-4279-ad16-19af09e6b091
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dac6d85d3b16ec691a4cc73b179515b70686791
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---type-name-not-valid"></a>错误-不是有效的类型名称
**错误代码**  
  
 BEC2011  
  
 **说明**  
  
 **类型名称**此架构文件的属性无效。 因为的值**类型名称**属性将用作自动生成的 C# 类名称的名称，它必须是有效的 C# 标识符，并且不能是保留的 BizTalk 关键字。  
  
 **用户执行任何操作**  
  
 在 Microsoft® 中选择相关的架构文件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，然后在属性窗口中，更改**类型名称**属性的值是有效的 C# 标识符而不是保留的 BizTalk 关键字。