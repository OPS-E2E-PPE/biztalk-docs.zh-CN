---
title: 错误-嵌套的类名冲突 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.nestedClassNameCollision
ms.assetid: dd636d25-d0c1-41be-a2ba-b38ea97b973d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4a9fa7a9f57088b3fb93e2eb6024e9b6aad49c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240941"
---
# <a name="error---nested-class-name-collision"></a><span data-ttu-id="aacd0-102">错误-嵌套的类名冲突</span><span class="sxs-lookup"><span data-stu-id="aacd0-102">Error - Nested Class Name Collision</span></span>
<span data-ttu-id="aacd0-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="aacd0-103">**Error Code**</span></span>  
  
 <span data-ttu-id="aacd0-104">BEC2017</span><span class="sxs-lookup"><span data-stu-id="aacd0-104">BEC2017</span></span>  
  
 <span data-ttu-id="aacd0-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="aacd0-105">**Explanation**</span></span>  
  
 <span data-ttu-id="aacd0-106">**类型名称**找到此架构的属性会作为相同**RootNode TypeName**之一的架构中的根节点的属性。</span><span class="sxs-lookup"><span data-stu-id="aacd0-106">The **Type Name** property of this schema was found to be the same as the **RootNode TypeName** property of one of the root nodes in the schema.</span></span> <span data-ttu-id="aacd0-107">C# 不允许嵌套类同名，因此这种情况会导致错误。</span><span class="sxs-lookup"><span data-stu-id="aacd0-107">C# disallows nested classes with the same names; therefore this condition causes an error.</span></span>  
  
 <span data-ttu-id="aacd0-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="aacd0-108">**User Action**</span></span>  
  
 <span data-ttu-id="aacd0-109">必须更改相关属性值中的一个或两个，以免名称冲突。</span><span class="sxs-lookup"><span data-stu-id="aacd0-109">You must change one or both of the relevant property values so that you avoid the name collision.</span></span> <span data-ttu-id="aacd0-110">请使用以下两种方法之一：</span><span class="sxs-lookup"><span data-stu-id="aacd0-110">Either:</span></span>  
  
-   <span data-ttu-id="aacd0-111">在 Microsoft 中选择相关的架构文件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，然后在属性窗口中，更改**类型名称**为唯一有效的值的属性。</span><span class="sxs-lookup"><span data-stu-id="aacd0-111">Select the relevant schema file in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, and then in the Properties window, change the **Type Name** property to a unique valid value.</span></span>  
  
     <span data-ttu-id="aacd0-112">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="aacd0-112">\- or -</span></span>  
  
-   <span data-ttu-id="aacd0-113">选择指定的根节点，然后在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，更改**RootNode TypeName**为唯一有效的值的属性。</span><span class="sxs-lookup"><span data-stu-id="aacd0-113">Select the indicated root node, and then in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, change the **RootNode TypeName** property to a unique valid value.</span></span>