---
title: 错误-第一个输入到无效的索引 Functoid |Microsoft 文档
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
ms.openlocfilehash: 163de330945cc085648188dffcb75821c11ec5d6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969643"
---
# <a name="error---first-input-to-index-functoid-not-valid"></a><span data-ttu-id="3c509-102">错误-第一个输入到无效的索引 Functoid</span><span class="sxs-lookup"><span data-stu-id="3c509-102">Error - First Input to Index Functoid Not Valid</span></span>
<span data-ttu-id="3c509-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="3c509-103">**Error Code**</span></span>  
  
 <span data-ttu-id="3c509-104">btm1015</span><span class="sxs-lookup"><span data-stu-id="3c509-104">btm1015</span></span>  
  
 <span data-ttu-id="3c509-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="3c509-105">**Explanation**</span></span>  
  
 <span data-ttu-id="3c509-106">第一个输入的参数指示**索引**functoid 不是来自**字段**中循环节点**记录**源架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="3c509-106">The first input parameter to the indicated **Index** functoid is not from a **Field** node within a looping **Record** node in the source schema.</span></span>  
  
 <span data-ttu-id="3c509-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="3c509-107">**User Action**</span></span>  
  
 <span data-ttu-id="3c509-108">通过拖动之间创建相应的输入的链接**字段**中循环节点**记录**节点源架构和指示**索引**functoid。</span><span class="sxs-lookup"><span data-stu-id="3c509-108">Create the appropriate input link by dragging between a **Field** node within a looping **Record** node in the source schema and the indicated **Index** functoid.</span></span> <span data-ttu-id="3c509-109">它可能需要打开**配置\<Functoid\> Functoid**对话框中，通过选择指示**索引**functoid，然后单击省略号 (**...**) 与关联的按钮**输入参数**属性在 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]为了确保新创建的链接是为指示的第一个输入的参数的属性窗口**索引**functoid。</span><span class="sxs-lookup"><span data-stu-id="3c509-109">It may be necessary to open the **Configure \<Functoid\> Functoid** dialog box by selecting the indicated **Index** functoid and clicking the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window in order to ensure that the newly created link is the first input parameter to the indicated **Index** functoid.</span></span>