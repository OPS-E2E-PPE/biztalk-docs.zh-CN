---
title: 表达式的要求和限制 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Expression Editor, about Expression Editor
- Expression Editor, requirements
- Orchestration Designer, Expression Editor
- Expression Editor, limitations
- Expression Editor
- Expression Editor, Orchestration Designer
ms.assetid: 1e0353d3-c2f3-4c10-86e3-8620e62dd0d5
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd819850f62d47c640753e843325c9851da177b5
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="requirements-and-limitations-for-expressions"></a>对表达式的要求和限制
业务流程设计器中的 BizTalk 表达式编辑器是标准的 Visual Studio 文本编辑器，这意味着它提供 IntelliSense 功能。 使用 BizTalk 表达式编辑器可通过文本形式输入表达式。  
  
 使用文本框可通过文本形式输入单个表达式。 表达式可以跨多行，但必须以单个分号结束。  
  
 下面列出了在 BizTalk 表达式编辑器中使用表达式时需遵守的一组限制：  
  
-   不支持复合赋值，例如“+=”、“-=”或“*=”。  
  
-   不支持在一个语句中使用多个赋值运算符。  
  
-   不支持在“if”或“while”谓词内赋值。  
  
-   不支持递增和递减。 例如“++”和“--”。  
  
-   对于消息部分，在使用 Microsoft.XLANGs.BaseTypes.DistinguishedFieldAttribute、所有公共数据字段和非只读 .NET 属性加批注时，允许对公共方法、嵌套类型、静态数据字段、只读 .NET 属性进行成员访问。  
  
-   不支持索引器或参数化 .NET 属性。  
  
-   不支持委托和事件。  
  
-   不支持泛型。  
  
-   不支持流控制语法，例如“foreach”、“for”、“do-while”、“break”和“continue”。  
  
-   不支持三元运算。 例如，“?:”。  
  
-   您可以在表达式形状中添加注释，但表达式形状必须包含至少一个语句。  
  
-   不支持数组。  
  
-   在将表达式形状放置于构造消息形状中时，您不能执行任何控制流。 例如，“if-then-else”或“while”。  
  
-   所有有效的表达式语句均为以下形式：  
  
    -   Dotted-name = expression;  
  
    -   Dotted-name = expression;  
  
 尽管您可以使用 BizTalk 表达式编辑器轻松快捷地输入复杂表达式，但不能使用它来输入任意数量的代码。 这是为了使业务流程的代码有别于其实现代码。