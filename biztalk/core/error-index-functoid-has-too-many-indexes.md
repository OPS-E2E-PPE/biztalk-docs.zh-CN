---
title: 错误-索引 Functoid 具有索引太多 |Microsoft Docs
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
ms.openlocfilehash: 800d8ca920dac64ee2d9c603bfcb949188824764
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348141"
---
# <a name="error---index-functoid-has-too-many-indexes"></a><span data-ttu-id="d2f38-102">错误-索引 Functoid 具有索引太多</span><span class="sxs-lookup"><span data-stu-id="d2f38-102">Error - Index Functoid Has Too Many Indexes</span></span>
<span data-ttu-id="d2f38-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="d2f38-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d2f38-104">btm1016</span><span class="sxs-lookup"><span data-stu-id="d2f38-104">btm1016</span></span>  
  
 <span data-ttu-id="d2f38-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="d2f38-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d2f38-106">所指示**索引**functoid 具有太多的索引输入的参数指定。</span><span class="sxs-lookup"><span data-stu-id="d2f38-106">The indicated **Index** functoid has too many index input parameters specified.</span></span> <span data-ttu-id="d2f38-107">索引输入参数数目不能超过的祖先循环**记录**节点内的**字段**节点指定为嵌套的第一个输入的参数。</span><span class="sxs-lookup"><span data-stu-id="d2f38-107">The number of index input parameters must not exceed the number of ancestor looping **Record** nodes within which the **Field** node specified as the first input parameter is nested.</span></span>  
  
 <span data-ttu-id="d2f38-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="d2f38-108">**User Action**</span></span>  
  
 <span data-ttu-id="d2f38-109">选择所指示**索引**functoid，单击省略号 (**...**) 按钮与相关联**输入参数**属性在 microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后在**配置\<Functoid\>Functoid**对话框中，删除多余的索引输入参数，通过选择并单击![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")为每个按钮。</span><span class="sxs-lookup"><span data-stu-id="d2f38-109">Select the indicated **Index** functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then in the **Configure \<Functoid\> Functoid** dialog box, delete the excess index input parameters by selecting and clicking the  ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete") button for each of them.</span></span>