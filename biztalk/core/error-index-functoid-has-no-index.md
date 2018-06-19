---
title: 错误-索引 Functoid 不具有索引 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.indexFunctoidHasNoIndex
ms.assetid: a523705e-6134-4d98-8ea6-dbfc7b43dae5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0159d308c9befc90590d281351409ba571921a53
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968435"
---
# <a name="error---index-functoid-has-no-index"></a><span data-ttu-id="09c90-102">错误-索引 Functoid 不具有索引</span><span class="sxs-lookup"><span data-stu-id="09c90-102">Error - Index Functoid Has No Index</span></span>
<span data-ttu-id="09c90-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="09c90-103">**Error Code**</span></span>  
  
 <span data-ttu-id="09c90-104">btm1014</span><span class="sxs-lookup"><span data-stu-id="09c90-104">btm1014</span></span>  
  
 <span data-ttu-id="09c90-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="09c90-105">**Explanation**</span></span>  
  
 <span data-ttu-id="09c90-106">提供了无索引值的指示**索引**functoid。</span><span class="sxs-lookup"><span data-stu-id="09c90-106">No index value(s) have been provided for the indicated **Index** functoid.</span></span>  
  
 <span data-ttu-id="09c90-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="09c90-107">**User Action**</span></span>  
  
 <span data-ttu-id="09c90-108">为指示提供适当数量的索引输入参数**索引**functoid，其中的适当数量由的循环数**记录**其中的节点**字段**嵌套源架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="09c90-108">Provide an appropriate number of index input parameters for the indicated **Index** functoid, where the appropriate number is determined by the number of looping **Record** nodes within which the **Field** node in the source schema is nested.</span></span> <span data-ttu-id="09c90-109">若要创建索引输入的参数，选择指定的 functoid，单击省略号 (**...**) 与关联的按钮**输入参数**属性在 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口，然后使用![ ] (../core/media/bts-tls-paraminsert.gif "bts_tls_paraminsert")按钮内**配置\<Functoid\> Functoid**对话框中添加一个或多个常量输入的参数，其中第一个到直接父表示索引循环**记录**节点和后续索引输入参数表示较远的祖先循环**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="09c90-109">To created index input parameters, select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then use the  ![](../core/media/bts-tls-paraminsert.gif "bts_tls_paraminsert") button within the **Configure \<Functoid\> Functoid** dialog box to add one or more constant input parameters, where the first one represents an index into the immediate parent looping **Record** node, and subsequent index input parameters represent increasingly remote ancestor looping **Record** nodes.</span></span>