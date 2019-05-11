---
title: 错误-根节点类名无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.rootNodeClassNameNotValid
ms.assetid: 48b4f7e4-8c20-4e94-86be-1425ea62f8c5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dca403fe7b99bf42f326485e6bd1788911d0dc32
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388478"
---
# <a name="error---root-node-class-name-not-valid"></a><span data-ttu-id="0bd36-102">错误-根节点类名无效</span><span class="sxs-lookup"><span data-stu-id="0bd36-102">Error - Root Node Class Name Not Valid</span></span>
<span data-ttu-id="0bd36-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="0bd36-103">**Error Code**</span></span>  
  
 <span data-ttu-id="0bd36-104">BEC2012</span><span class="sxs-lookup"><span data-stu-id="0bd36-104">BEC2012</span></span>  
  
 <span data-ttu-id="0bd36-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="0bd36-105">**Explanation**</span></span>  
  
 <span data-ttu-id="0bd36-106">**RootNode TypeName**之一的此架构中的根节点的属性无效。</span><span class="sxs-lookup"><span data-stu-id="0bd36-106">The **RootNode TypeName** property of one of the root nodes in this schema is not valid.</span></span> <span data-ttu-id="0bd36-107">因为的值**RootNode TypeName**属性使用的自动生成名称为C#类名必须是有效C#标识符且不能为保留的 BizTalk 关键字。</span><span class="sxs-lookup"><span data-stu-id="0bd36-107">Because the value of the **RootNode TypeName** property is used as the name of an automatically generated C# class name, it must be a valid C# identifier and cannot be a reserved BizTalk keyword.</span></span>  
  
 <span data-ttu-id="0bd36-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="0bd36-108">**User Action**</span></span>  
  
 <span data-ttu-id="0bd36-109">选择所指示的根节点，然后在 Microsoft®[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，更改**RootNode TypeName**属性是一个有效的值C#标识符并不是保留的 BizTalk 关键字。</span><span class="sxs-lookup"><span data-stu-id="0bd36-109">Select the indicated root node, and then in the Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, change the **RootNode TypeName** property to a value that is a valid C# identifier and is not a reserved BizTalk keyword.</span></span>