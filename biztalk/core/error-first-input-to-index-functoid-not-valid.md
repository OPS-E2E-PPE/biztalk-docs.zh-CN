---
title: 错误-第一个输入无效的索引 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputToIndexNotValid
ms.assetid: f7dbe9cc-9cfa-4fc7-af3e-1241cb2b50a9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6746912273d72df958c7df5e8f092aeb8f490ecb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388880"
---
# <a name="error---first-input-to-index-functoid-not-valid"></a><span data-ttu-id="56f25-102">错误-第一个输入无效的索引 Functoid</span><span class="sxs-lookup"><span data-stu-id="56f25-102">Error - First Input to Index Functoid Not Valid</span></span>
<span data-ttu-id="56f25-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="56f25-103">**Error Code**</span></span>  
  
 <span data-ttu-id="56f25-104">btm1015</span><span class="sxs-lookup"><span data-stu-id="56f25-104">btm1015</span></span>  
  
 <span data-ttu-id="56f25-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="56f25-105">**Explanation**</span></span>  
  
 <span data-ttu-id="56f25-106">所指示的第一个输入的参数**索引**functoid 不是来自**字段**中的循环节点**记录**源架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="56f25-106">The first input parameter to the indicated **Index** functoid is not from a **Field** node within a looping **Record** node in the source schema.</span></span>  
  
 <span data-ttu-id="56f25-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="56f25-107">**User Action**</span></span>  
  
 <span data-ttu-id="56f25-108">创建相应的输入的链接： 将之间**字段**节点内的循环**记录**中的源架构和所指示的节点**索引**functoid。</span><span class="sxs-lookup"><span data-stu-id="56f25-108">Create the appropriate input link by dragging between a **Field** node within a looping **Record** node in the source schema and the indicated **Index** functoid.</span></span> <span data-ttu-id="56f25-109">可能有必要，打开**配置\<Functoid\> Functoid**通过选择所指示的对话框**索引**functoid，然后单击省略号 (**...**) 按钮与相关联**输入参数**属性在 microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]为了确保新创建的链接是所指示的第一个输入的参数属性窗口**索引**functoid。</span><span class="sxs-lookup"><span data-stu-id="56f25-109">It may be necessary to open the **Configure \<Functoid\> Functoid** dialog box by selecting the indicated **Index** functoid and clicking the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window in order to ensure that the newly created link is the first input parameter to the indicated **Index** functoid.</span></span>