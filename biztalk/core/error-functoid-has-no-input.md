---
title: "错误-Functoid 有没有输入 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.functiodHasNoInput
ms.assetid: ea59b902-953d-4a5f-aa28-dbaa0a017dca
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97505d0c00e0cc9015dd17cb487bb5dbf6a50d90
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---functoid-has-no-input"></a><span data-ttu-id="234cb-102">错误-Functoid 有没有输入</span><span class="sxs-lookup"><span data-stu-id="234cb-102">Error - Functoid Has No Input</span></span>
<span data-ttu-id="234cb-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="234cb-103">**Error Code**</span></span>  
  
 <span data-ttu-id="234cb-104">btm1012</span><span class="sxs-lookup"><span data-stu-id="234cb-104">btm1012</span></span>  
  
 <span data-ttu-id="234cb-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="234cb-105">**Explanation**</span></span>  
  
 <span data-ttu-id="234cb-106">所指示的 functoid 至少需要一个输入参数，但当前未指定任何输入参数。</span><span class="sxs-lookup"><span data-stu-id="234cb-106">The indicated functoid requires at least one input parameter, but no input parameters have been specified.</span></span>  
  
 <span data-ttu-id="234cb-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="234cb-107">**User Action**</span></span>  
  
 <span data-ttu-id="234cb-108">采用以下一种或两种方法为所指示的 functoid 提供适当数目的输入参数，特别要注意输入参数的正确顺序：</span><span class="sxs-lookup"><span data-stu-id="234cb-108">Use one or both of the following methods to provide the appropriate number of input parameters to the indicated functoid, paying particular attention to the expected order of input parameters:</span></span>  
  
-   <span data-ttu-id="234cb-109">拖动鼠标，在所指示的 functoid 与源架构中的节点或其他 functoid 的输出之间创建链接，这些 functoid 在映射网格页中位于所指示的 functoid 的左侧。</span><span class="sxs-lookup"><span data-stu-id="234cb-109">Drag to create links between the indicated functoid and either nodes in the source schema or the output of other functoids that are located to the left of the indicated functoid in a map grid page.</span></span>  
  
-   <span data-ttu-id="234cb-110">选择指定的 functoid，单击省略号 (**...**) 与关联的按钮**输入参数**属性在 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后配置和重新排列中的输入参数的顺序**配置\<Functoid > Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="234cb-110">Select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then configure and rearrange the order of the input parameters in the **Configure \<Functoid> Functoid** dialog box.</span></span> <span data-ttu-id="234cb-111">也可以创建常数输入参数并为它赋值，然后在此对话框中将该参数放置到相对于其他输入参数的正确位置。</span><span class="sxs-lookup"><span data-stu-id="234cb-111">Constant input parameters can be created, given values, and put in the proper order relative to the other input parameters in this dialog box.</span></span>