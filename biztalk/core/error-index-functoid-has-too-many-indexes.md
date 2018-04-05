---
title: 错误-索引 Functoid 有太多索引 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.indexFunctoidHasTooManyIndices
ms.assetid: 5dd2d5b4-3f7a-45be-b6f4-708b0a76805a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a22b49a921b957c0fb36f9e6b6925c991cc3cf6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="error---index-functoid-has-too-many-indexes"></a><span data-ttu-id="a39cd-102">错误-索引 Functoid 有太多的索引</span><span class="sxs-lookup"><span data-stu-id="a39cd-102">Error - Index Functoid Has Too Many Indexes</span></span>
<span data-ttu-id="a39cd-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="a39cd-103">**Error Code**</span></span>  
  
 <span data-ttu-id="a39cd-104">btm1016</span><span class="sxs-lookup"><span data-stu-id="a39cd-104">btm1016</span></span>  
  
 <span data-ttu-id="a39cd-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="a39cd-105">**Explanation**</span></span>  
  
 <span data-ttu-id="a39cd-106">指示**索引**functoid 有太多索引输入的参数指定。</span><span class="sxs-lookup"><span data-stu-id="a39cd-106">The indicated **Index** functoid has too many index input parameters specified.</span></span> <span data-ttu-id="a39cd-107">索引输入参数的数目不能超过的祖先循环数**记录**其中的节点**字段**节点指定为嵌套的第一个输入的参数。</span><span class="sxs-lookup"><span data-stu-id="a39cd-107">The number of index input parameters must not exceed the number of ancestor looping **Record** nodes within which the **Field** node specified as the first input parameter is nested.</span></span>  
  
 <span data-ttu-id="a39cd-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="a39cd-108">**User Action**</span></span>  
  
 <span data-ttu-id="a39cd-109">选择指示**索引**functoid，单击省略号 (**...**) 与关联的按钮**输入参数**属性在 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后在**配置\<Functoid\>Functoid**对话框中，删除多余的索引通过选择并单击输入参数![ ] (../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")为每个按钮。</span><span class="sxs-lookup"><span data-stu-id="a39cd-109">Select the indicated **Index** functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then in the **Configure \<Functoid\> Functoid** dialog box, delete the excess index input parameters by selecting and clicking the  ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete") button for each of them.</span></span>