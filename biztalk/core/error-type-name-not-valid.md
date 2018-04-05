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
# <a name="error---type-name-not-valid"></a><span data-ttu-id="69fe9-102">错误-不是有效的类型名称</span><span class="sxs-lookup"><span data-stu-id="69fe9-102">Error - Type Name Not Valid</span></span>
<span data-ttu-id="69fe9-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="69fe9-103">**Error Code**</span></span>  
  
 <span data-ttu-id="69fe9-104">BEC2011</span><span class="sxs-lookup"><span data-stu-id="69fe9-104">BEC2011</span></span>  
  
 <span data-ttu-id="69fe9-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="69fe9-105">**Explanation**</span></span>  
  
 <span data-ttu-id="69fe9-106">**类型名称**此架构文件的属性无效。</span><span class="sxs-lookup"><span data-stu-id="69fe9-106">The **Type Name** property of this schema file is not valid.</span></span> <span data-ttu-id="69fe9-107">因为的值**类型名称**属性将用作自动生成的 C# 类名称的名称，它必须是有效的 C# 标识符，并且不能是保留的 BizTalk 关键字。</span><span class="sxs-lookup"><span data-stu-id="69fe9-107">Because the value of the **Type Name** property is used as the name of an automatically generated C# class name, it must be a valid C# identifier and cannot be a reserved BizTalk keyword.</span></span>  
  
 <span data-ttu-id="69fe9-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="69fe9-108">**User Action**</span></span>  
  
 <span data-ttu-id="69fe9-109">在 Microsoft® 中选择相关的架构文件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，然后在属性窗口中，更改**类型名称**属性的值是有效的 C# 标识符而不是保留的 BizTalk 关键字。</span><span class="sxs-lookup"><span data-stu-id="69fe9-109">Select the relevant schema file in Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, and then in the Properties window, change the **Type Name** property to a value that is a valid C# identifier and is not a reserved BizTalk keyword.</span></span>