---
title: 错误-Functoid 固定输入不匹配 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.functoidFixedInputMismatch
ms.assetid: d235e7c3-efcf-4128-aef7-cdfdf1f317be
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8de4020105f357905e510be1694c0cf95a4af6c2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="error---functoid-fixed-input-mismatch"></a><span data-ttu-id="b69e8-102">错误-Functoid 固定输入不匹配</span><span class="sxs-lookup"><span data-stu-id="b69e8-102">Error - Functoid Fixed Input Mismatch</span></span>
<span data-ttu-id="b69e8-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="b69e8-103">**Error Code**</span></span>  
  
 <span data-ttu-id="b69e8-104">btm1010</span><span class="sxs-lookup"><span data-stu-id="b69e8-104">btm1010</span></span>  
  
 <span data-ttu-id="b69e8-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="b69e8-105">**Explanation**</span></span>  
  
 <span data-ttu-id="b69e8-106">所指示的 functoid 的输入参数个数不正确。</span><span class="sxs-lookup"><span data-stu-id="b69e8-106">The indicated functoid does not have the correct number of input parameters specified.</span></span> <span data-ttu-id="b69e8-107">输入参数的数目必须与指定的完全一样。</span><span class="sxs-lookup"><span data-stu-id="b69e8-107">The number of input parameters must be exactly as specified.</span></span>  
  
 <span data-ttu-id="b69e8-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="b69e8-108">**User Action**</span></span>  
  
 <span data-ttu-id="b69e8-109">采用以下一种或多种方法为指示的 functoid 提供所指示数目的输入参数，特别要注意确保输入参数的顺序正确：</span><span class="sxs-lookup"><span data-stu-id="b69e8-109">Use one or more of the following methods to provide the indicated number of input parameters to the indicated functoid, paying particular attention to the expected order of input parameters:</span></span>  
  
-   <span data-ttu-id="b69e8-110">若要创建其他链接，请拖动鼠标以在所指示的 functoid 与源架构中的节点或其他 functoid 的输出之间创建链接，这些 functoid 在映射网格页中位于所指示的 functoid 的左侧。</span><span class="sxs-lookup"><span data-stu-id="b69e8-110">To create additional links, drag to create links between the indicated functoid and either nodes in the source schema or the output of other functoids that are located to the left of the indicated functoid in a map grid page.</span></span>  
  
-   <span data-ttu-id="b69e8-111">若要创建更多链接，选择指定的 functoid，单击省略号 (**...**) 与关联的按钮**输入参数**中的属性[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后配置和重新排列中的输入参数的顺序**配置\<Functoid\> Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="b69e8-111">To create additional links, select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then configure and rearrange the order of the input parameters in the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="b69e8-112">也可以创建常数输入参数并为它赋值，然后在此对话框中将该参数放置到相对于其他输入参数的正确位置。</span><span class="sxs-lookup"><span data-stu-id="b69e8-112">Constant input parameters can be created, given values, and put in the proper order relative to the other input parameters in this dialog box.</span></span>  
  
-   <span data-ttu-id="b69e8-113">要删除现有的链接，为每个链接连接到左侧指定 functoid，右键单击该链接，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="b69e8-113">To remove existing links, for each link connected to the left side of the indicated functoid, right-click the link and then click **Delete**.</span></span>  
  
-   <span data-ttu-id="b69e8-114">若要删除现有的链接，选择指定的 functoid，单击省略号 (**...**) 与关联的按钮**输入参数**中的属性[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后在**配置\<Functoid\> Functoid**对话框中，删除所有输入参数，请选择并单击![ ] (../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")为每个按钮。</span><span class="sxs-lookup"><span data-stu-id="b69e8-114">To remove existing links, select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then in the **Configure \<Functoid\> Functoid** dialog box, delete all input parameters by selecting and clicking the ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete") button for each of them.</span></span> <span data-ttu-id="b69e8-115">删除常数输入参数时必须使用这种方法。</span><span class="sxs-lookup"><span data-stu-id="b69e8-115">You must use this method to delete constant input parameters.</span></span>