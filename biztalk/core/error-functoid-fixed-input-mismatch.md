---
title: 错误-Functoid 固定输入个数不匹配 |Microsoft Docs
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
ms.openlocfilehash: 0f33e21a47acd4e00c7a23a1be6735c7fb5c950a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388866"
---
# <a name="error---functoid-fixed-input-mismatch"></a><span data-ttu-id="21016-102">错误-Functoid 固定输入个数不匹配</span><span class="sxs-lookup"><span data-stu-id="21016-102">Error - Functoid Fixed Input Mismatch</span></span>
<span data-ttu-id="21016-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="21016-103">**Error Code**</span></span>  

 <span data-ttu-id="21016-104">btm1010</span><span class="sxs-lookup"><span data-stu-id="21016-104">btm1010</span></span>  

 <span data-ttu-id="21016-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="21016-105">**Explanation**</span></span>  

 <span data-ttu-id="21016-106">所指示的 functoid 没有正确指定的输入参数的数。</span><span class="sxs-lookup"><span data-stu-id="21016-106">The indicated functoid does not have the correct number of input parameters specified.</span></span> <span data-ttu-id="21016-107">输入参数的数目必须是指定的完全一样。</span><span class="sxs-lookup"><span data-stu-id="21016-107">The number of input parameters must be exactly as specified.</span></span>  

 <span data-ttu-id="21016-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="21016-108">**User Action**</span></span>  

 <span data-ttu-id="21016-109">使用一个或多个以下方法提供的输入参数所指示的 functoid，特别要注意输入参数的正确顺序所指示的数目：</span><span class="sxs-lookup"><span data-stu-id="21016-109">Use one or more of the following methods to provide the indicated number of input parameters to the indicated functoid, paying particular attention to the expected order of input parameters:</span></span>  

- <span data-ttu-id="21016-110">若要创建其他链接，拖动以在源架构或位于所指示的 functoid 在映射网格页左侧其他 functoid 的输出中创建所指示的 functoid 和节点之间的链接。</span><span class="sxs-lookup"><span data-stu-id="21016-110">To create additional links, drag to create links between the indicated functoid and either nodes in the source schema or the output of other functoids that are located to the left of the indicated functoid in a map grid page.</span></span>  

- <span data-ttu-id="21016-111">若要创建其他链接，请选择所指示的 functoid，单击省略号 (**...**) 按钮与相关联**输入参数**中的属性[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后配置并重新排列输入参数的顺序**配置\<Functoid\> Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="21016-111">To create additional links, select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then configure and rearrange the order of the input parameters in the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="21016-112">可以创建、 获得值，并放在正确的顺序相对于此对话框中的其他输入参数常数输入的参数。</span><span class="sxs-lookup"><span data-stu-id="21016-112">Constant input parameters can be created, given values, and put in the proper order relative to the other input parameters in this dialog box.</span></span>  

- <span data-ttu-id="21016-113">要删除现有的链接，每个链接连接到左侧和右侧的所指示的 functoid，右键单击该链接，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="21016-113">To remove existing links, for each link connected to the left side of the indicated functoid, right-click the link and then click **Delete**.</span></span>  

- <span data-ttu-id="21016-114">若要删除现有的链接，选择所指示的 functoid，单击省略号 (**...**) 按钮与相关联**输入参数**中的属性[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后在**配置\<Functoid\> Functoid**对话框中，通过选择并单击的所有输入参数的 delete ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")为每个按钮。</span><span class="sxs-lookup"><span data-stu-id="21016-114">To remove existing links, select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then in the **Configure \<Functoid\> Functoid** dialog box, delete all input parameters by selecting and clicking the ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete") button for each of them.</span></span> <span data-ttu-id="21016-115">必须使用此方法来删除常数输入的参数。</span><span class="sxs-lookup"><span data-stu-id="21016-115">You must use this method to delete constant input parameters.</span></span>
