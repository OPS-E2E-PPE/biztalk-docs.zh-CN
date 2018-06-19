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
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd819850f62d47c640753e843325c9851da177b5
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22268381"
---
# <a name="requirements-and-limitations-for-expressions"></a><span data-ttu-id="8799f-102">对表达式的要求和限制</span><span class="sxs-lookup"><span data-stu-id="8799f-102">Requirements and Limitations for Expressions</span></span>
<span data-ttu-id="8799f-103">业务流程设计器中的 BizTalk 表达式编辑器是标准的 Visual Studio 文本编辑器，这意味着它提供 IntelliSense 功能。</span><span class="sxs-lookup"><span data-stu-id="8799f-103">BizTalk Expression Editor in Orchestration Designer is a standard Visual Studio text editor, which means it offers IntelliSense.</span></span> <span data-ttu-id="8799f-104">使用 BizTalk 表达式编辑器可通过文本形式输入表达式。</span><span class="sxs-lookup"><span data-stu-id="8799f-104">You use BizTalk Expression Editor to enter an expression in textual form.</span></span>  
  
 <span data-ttu-id="8799f-105">使用文本框可通过文本形式输入单个表达式。</span><span class="sxs-lookup"><span data-stu-id="8799f-105">Use the text box to enter a single expression in textual form.</span></span> <span data-ttu-id="8799f-106">表达式可以跨多行，但必须以单个分号结束。</span><span class="sxs-lookup"><span data-stu-id="8799f-106">The expression can span multiple lines, but must end with single semicolon.</span></span>  
  
 <span data-ttu-id="8799f-107">下面列出了在 BizTalk 表达式编辑器中使用表达式时需遵守的一组限制：</span><span class="sxs-lookup"><span data-stu-id="8799f-107">The following is a list of limitations when using expressions in the BizTalk Expression Editor:</span></span>  
  
-   <span data-ttu-id="8799f-108">不支持复合赋值，例如“+=”、“-=”或“\*=”。</span><span class="sxs-lookup"><span data-stu-id="8799f-108">Compound assignment such as "+=", "-=", or "\*=" is not supported.</span></span>  
  
-   <span data-ttu-id="8799f-109">不支持在一个语句中使用多个赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="8799f-109">More than one assignment operator in a statement is not supported.</span></span>  
  
-   <span data-ttu-id="8799f-110">不支持在“if”或“while”谓词内赋值。</span><span class="sxs-lookup"><span data-stu-id="8799f-110">Assignment within an “if” or “while” predicate is not supported.</span></span>  
  
-   <span data-ttu-id="8799f-111">不支持递增和递减。</span><span class="sxs-lookup"><span data-stu-id="8799f-111">Increment and decrement are not supported.</span></span> <span data-ttu-id="8799f-112">例如“++”和“--”。</span><span class="sxs-lookup"><span data-stu-id="8799f-112">For example, "++" and "--".</span></span>  
  
-   <span data-ttu-id="8799f-113">对于消息部分，在使用 Microsoft.XLANGs.BaseTypes.DistinguishedFieldAttribute、所有公共数据字段和非只读 .NET 属性加批注时，允许对公共方法、嵌套类型、静态数据字段、只读 .NET 属性进行成员访问。</span><span class="sxs-lookup"><span data-stu-id="8799f-113">For message parts, member access is allowed on public methods, nested types, static data fields, read-only .NET properties when annotated with Microsoft.XLANGs.BaseTypes.DistinguishedFieldAttribute, all public data fields, and non-read-only .NET properties.</span></span>  
  
-   <span data-ttu-id="8799f-114">不支持索引器或参数化 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="8799f-114">Indexers or parameterized .NET properties are not supported.</span></span>  
  
-   <span data-ttu-id="8799f-115">不支持委托和事件。</span><span class="sxs-lookup"><span data-stu-id="8799f-115">Delegates and events are not supported.</span></span>  
  
-   <span data-ttu-id="8799f-116">不支持泛型。</span><span class="sxs-lookup"><span data-stu-id="8799f-116">Generics are not supported.</span></span>  
  
-   <span data-ttu-id="8799f-117">不支持流控制语法，例如“foreach”、“for”、“do-while”、“break”和“continue”。</span><span class="sxs-lookup"><span data-stu-id="8799f-117">Flow control syntax such as "foreach", "for", "do-while", "break", and "continue" are not supported.</span></span>  
  
-   <span data-ttu-id="8799f-118">不支持三元运算。</span><span class="sxs-lookup"><span data-stu-id="8799f-118">Ternary operations are not supported.</span></span> <span data-ttu-id="8799f-119">例如，“?:”。</span><span class="sxs-lookup"><span data-stu-id="8799f-119">For example, "?:".</span></span>  
  
-   <span data-ttu-id="8799f-120">您可以在表达式形状中添加注释，但表达式形状必须包含至少一个语句。</span><span class="sxs-lookup"><span data-stu-id="8799f-120">You can add comments in the Expression shape, but the Expression shape must contain at least one statement.</span></span>  
  
-   <span data-ttu-id="8799f-121">不支持数组。</span><span class="sxs-lookup"><span data-stu-id="8799f-121">Arrays are not supported.</span></span>  
  
-   <span data-ttu-id="8799f-122">在将表达式形状放置于构造消息形状中时，您不能执行任何控制流。</span><span class="sxs-lookup"><span data-stu-id="8799f-122">When the Expression shape is placed in a Construct Message shape, you cannot do any control flow.</span></span> <span data-ttu-id="8799f-123">例如，“if-then-else”或“while”。</span><span class="sxs-lookup"><span data-stu-id="8799f-123">For example, "if-then-else" or "while".</span></span>  
  
-   <span data-ttu-id="8799f-124">所有有效的表达式语句均为以下形式：</span><span class="sxs-lookup"><span data-stu-id="8799f-124">All valid expression statements are of the form:</span></span>  
  
    -   <span data-ttu-id="8799f-125">Dotted-name = expression;</span><span class="sxs-lookup"><span data-stu-id="8799f-125">Dotted-name = expression;</span></span>  
  
    -   <span data-ttu-id="8799f-126">Dotted-name = expression;</span><span class="sxs-lookup"><span data-stu-id="8799f-126">Dotted-name = expression;</span></span>  
  
 <span data-ttu-id="8799f-127">尽管您可以使用 BizTalk 表达式编辑器轻松快捷地输入复杂表达式，但不能使用它来输入任意数量的代码。</span><span class="sxs-lookup"><span data-stu-id="8799f-127">Though you can use BizTalk Expression Editor to enter complex expressions easily and quickly, you cannot use it to enter an arbitrary amount of code.</span></span> <span data-ttu-id="8799f-128">这是为了使业务流程的代码有别于其实现代码。</span><span class="sxs-lookup"><span data-stu-id="8799f-128">The reason for this is to keep code for the business process separate from its implementation code.</span></span>