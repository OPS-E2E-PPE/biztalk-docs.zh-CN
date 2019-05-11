---
title: 错误-嵌套的类名冲突 |Microsoft Docs
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
ms.openlocfilehash: 37edc5012d2298e9516e766743b58f7d5448cf6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388622"
---
# <a name="error---nested-class-name-collision"></a><span data-ttu-id="4f266-102">错误-嵌套的类名冲突</span><span class="sxs-lookup"><span data-stu-id="4f266-102">Error - Nested Class Name Collision</span></span>
<span data-ttu-id="4f266-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="4f266-103">**Error Code**</span></span>  

 <span data-ttu-id="4f266-104">BEC2017</span><span class="sxs-lookup"><span data-stu-id="4f266-104">BEC2017</span></span>  

 <span data-ttu-id="4f266-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="4f266-105">**Explanation**</span></span>  

 <span data-ttu-id="4f266-106">**类型名称**找到此架构的属性是与相同**RootNode TypeName**的其中一个架构中根节点的属性。</span><span class="sxs-lookup"><span data-stu-id="4f266-106">The **Type Name** property of this schema was found to be the same as the **RootNode TypeName** property of one of the root nodes in the schema.</span></span> <span data-ttu-id="4f266-107">C#不允许嵌套的类具有相同的名称;因此这种情况将导致错误。</span><span class="sxs-lookup"><span data-stu-id="4f266-107">C# disallows nested classes with the same names; therefore this condition causes an error.</span></span>  

 <span data-ttu-id="4f266-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="4f266-108">**User Action**</span></span>  

 <span data-ttu-id="4f266-109">您必须更改一个或两个相关的属性值，以便避免名称冲突。</span><span class="sxs-lookup"><span data-stu-id="4f266-109">You must change one or both of the relevant property values so that you avoid the name collision.</span></span> <span data-ttu-id="4f266-110">请使用以下两种方法之一：</span><span class="sxs-lookup"><span data-stu-id="4f266-110">Either:</span></span>  

- <span data-ttu-id="4f266-111">在 Microsoft 中选择相关的架构文件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，然后在属性窗口中更改**类型名称**属性设置为唯一的有效值。</span><span class="sxs-lookup"><span data-stu-id="4f266-111">Select the relevant schema file in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, and then in the Properties window, change the **Type Name** property to a unique valid value.</span></span>  

   <span data-ttu-id="4f266-112">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="4f266-112">\- or -</span></span>  

- <span data-ttu-id="4f266-113">选择所指示的根节点，然后在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，更改**RootNode TypeName**属性设置为唯一的有效值。</span><span class="sxs-lookup"><span data-stu-id="4f266-113">Select the indicated root node, and then in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, change the **RootNode TypeName** property to a unique valid value.</span></span>
