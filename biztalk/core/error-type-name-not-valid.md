---
title: 错误-类型名无效 |Microsoft Docs
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
ms.openlocfilehash: e7a99d3ca15b99c2c1a5669ddc2b89e8ae643eb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346302"
---
# <a name="error---type-name-not-valid"></a><span data-ttu-id="4a677-102">错误-类型名无效</span><span class="sxs-lookup"><span data-stu-id="4a677-102">Error - Type Name Not Valid</span></span>
<span data-ttu-id="4a677-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="4a677-103">**Error Code**</span></span>  
  
 <span data-ttu-id="4a677-104">BEC2011</span><span class="sxs-lookup"><span data-stu-id="4a677-104">BEC2011</span></span>  
  
 <span data-ttu-id="4a677-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="4a677-105">**Explanation**</span></span>  
  
 <span data-ttu-id="4a677-106">**类型名称**此架构文件属性无效。</span><span class="sxs-lookup"><span data-stu-id="4a677-106">The **Type Name** property of this schema file is not valid.</span></span> <span data-ttu-id="4a677-107">因为的值**类型名称**属性使用的自动生成名称为C#类名必须是有效C#标识符且不能为保留的 BizTalk 关键字。</span><span class="sxs-lookup"><span data-stu-id="4a677-107">Because the value of the **Type Name** property is used as the name of an automatically generated C# class name, it must be a valid C# identifier and cannot be a reserved BizTalk keyword.</span></span>  
  
 <span data-ttu-id="4a677-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="4a677-108">**User Action**</span></span>  
  
 <span data-ttu-id="4a677-109">选择相关的架构文件中 Microsoft®[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，然后在属性窗口中更改**类型名称**属性是一个有效的值C#标识符并不是保留的 BizTalk 关键字。</span><span class="sxs-lookup"><span data-stu-id="4a677-109">Select the relevant schema file in Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, and then in the Properties window, change the **Type Name** property to a value that is a valid C# identifier and is not a reserved BizTalk keyword.</span></span>