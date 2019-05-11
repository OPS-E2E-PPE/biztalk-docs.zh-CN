---
title: 错误-Functoid 具有任何输入 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.functiodHasNoInput
ms.assetid: ea59b902-953d-4a5f-aa28-dbaa0a017dca
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db8ea58b62537d26b8bc088d84eefa6186dc8941
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348358"
---
# <a name="error---functoid-has-no-input"></a><span data-ttu-id="31e62-102">错误-Functoid 具有任何输入</span><span class="sxs-lookup"><span data-stu-id="31e62-102">Error - Functoid Has No Input</span></span>
<span data-ttu-id="31e62-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="31e62-103">**Error Code**</span></span>  

 <span data-ttu-id="31e62-104">btm1012</span><span class="sxs-lookup"><span data-stu-id="31e62-104">btm1012</span></span>  

 <span data-ttu-id="31e62-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="31e62-105">**Explanation**</span></span>  

 <span data-ttu-id="31e62-106">所指示的 functoid 需要至少一个输入的参数，但尚未指定任何输入的参数。</span><span class="sxs-lookup"><span data-stu-id="31e62-106">The indicated functoid requires at least one input parameter, but no input parameters have been specified.</span></span>  

 <span data-ttu-id="31e62-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="31e62-107">**User Action**</span></span>  

 <span data-ttu-id="31e62-108">使用一个或两个以下方法提供适当数量的输入参数所指示的 functoid，特别要注意输入参数的正确顺序：</span><span class="sxs-lookup"><span data-stu-id="31e62-108">Use one or both of the following methods to provide the appropriate number of input parameters to the indicated functoid, paying particular attention to the expected order of input parameters:</span></span>  

- <span data-ttu-id="31e62-109">拖动以在源架构或位于所指示的 functoid 在映射网格页左侧其他 functoid 的输出中创建所指示的 functoid 和节点之间的链接。</span><span class="sxs-lookup"><span data-stu-id="31e62-109">Drag to create links between the indicated functoid and either nodes in the source schema or the output of other functoids that are located to the left of the indicated functoid in a map grid page.</span></span>  

- <span data-ttu-id="31e62-110">选择所指示的 functoid，单击省略号 (**...**) 按钮与相关联**输入参数**属性在 microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后配置并重新排列输入参数的顺序**配置\<Functoid\> Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="31e62-110">Select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then configure and rearrange the order of the input parameters in the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="31e62-111">可以创建、 获得值，并放在正确的顺序相对于此对话框中的其他输入参数常数输入的参数。</span><span class="sxs-lookup"><span data-stu-id="31e62-111">Constant input parameters can be created, given values, and put in the proper order relative to the other input parameters in this dialog box.</span></span>
