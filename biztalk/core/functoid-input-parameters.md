---
title: Functoid 输入参数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cca24f93-74a8-460c-b9ab-9aa2c767fe2f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a4a93d827a5f58401bb9b8fcdf9727c2a61767e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008094"
---
# <a name="functoid-input-parameters"></a><span data-ttu-id="cf525-102">Functoid 输入参数</span><span class="sxs-lookup"><span data-stu-id="cf525-102">Functoid Input Parameters</span></span>
<span data-ttu-id="cf525-103">在映射中使用 functoid 的关键是正确配置 functoid 的输入参数。</span><span class="sxs-lookup"><span data-stu-id="cf525-103">A critical aspect of using functoids in your maps is properly configuring the input parameters to the functoid.</span></span> <span data-ttu-id="cf525-104">虽然输入参数的顺序并不重要的所有 functoid (如**加法**将显示该 functoid 将一个预期从添加的属性相关联)，许多 functoid 必须具有其输入的参数指定正确的顺序。</span><span class="sxs-lookup"><span data-stu-id="cf525-104">While the order of input parameters is not critical for all functoids (such as the **Addition** functoid, which displays the same associate properties that one expects from addition), many functoids must have their input parameters specified in the correct order.</span></span>  
  
## <a name="create-input-paramaters"></a><span data-ttu-id="cf525-105">创建输入的参数</span><span class="sxs-lookup"><span data-stu-id="cf525-105">Create input paramaters</span></span>
 <span data-ttu-id="cf525-106">有两种为 functoid 创建输入参数的方法：</span><span class="sxs-lookup"><span data-stu-id="cf525-106">There are two ways that input parameters to a functoid can be created:</span></span>  
  
- <span data-ttu-id="cf525-107">通过在显示的网格页中创建指向左侧的 functoid 的链接。</span><span class="sxs-lookup"><span data-stu-id="cf525-107">By creating links into the left side of a functoid in the displayed grid page.</span></span> <span data-ttu-id="cf525-108">链接的创建顺序即为将关联的输入参数传递给 functoid 的顺序。</span><span class="sxs-lookup"><span data-stu-id="cf525-108">The order in which you create the links is the order in which the associated input parameters are passed to the functoid.</span></span>  
  
- <span data-ttu-id="cf525-109">通过打开**配置\<Functoid\> Functoid**对话框并添加新的输入参数。</span><span class="sxs-lookup"><span data-stu-id="cf525-109">By opening the **Configure \<Functoid\> Functoid** dialog box and adding new input parameters.</span></span> <span data-ttu-id="cf525-110">由于此对话框允许重排 functoid 的输入参数的顺序以确保顺序正确，因此该对话框也很重要。</span><span class="sxs-lookup"><span data-stu-id="cf525-110">This dialog box is also important because it allows you to reorder the input parameters to a functoid so that they are in the correct order.</span></span> <span data-ttu-id="cf525-111">例如，如果按错误的顺序创建指向 functoid 的链接，则可以转到此对话框进行必要的更正。</span><span class="sxs-lookup"><span data-stu-id="cf525-111">For example, if you create links to the functoid in the incorrect order, you can go to this dialog box and make the necessary corrections.</span></span> <span data-ttu-id="cf525-112">配置 functoid 的输入的参数的分步说明，请参阅[如何配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="cf525-112">For step-by-step instructions on configuring the input parameters for a functoid, see [How to Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md).</span></span>  
  
  <span data-ttu-id="cf525-113">必须使用**配置\<Functoid\> Functoid**对话框可以创建常数输入的参数。</span><span class="sxs-lookup"><span data-stu-id="cf525-113">You must use the **Configure \<Functoid\> Functoid** dialog box to create input parameters that are constants.</span></span>  
  
  <span data-ttu-id="cf525-114">当某个链接或 functoid 使用提供的标签**标签**属性在属性窗口中选择链接或 functoid 时，将在显示该标签**配置\<Functoid\>Functoid**对话框而不是 schema 节点的相应 XPath 或用作输入参数的 functoid 的名称。</span><span class="sxs-lookup"><span data-stu-id="cf525-114">When you provide a label for a link or functoid using the **Label** property in the Properties window when the link or functoid is selected, that label will be shown in the **Configure \<Functoid\> Functoid** dialog box rather than the corresponding XPath of a schema node, or the name of a functoid being used as an input parameter.</span></span> <span data-ttu-id="cf525-115">使用标签可以更容易地标识参数并将参数按正确顺序排列。</span><span class="sxs-lookup"><span data-stu-id="cf525-115">With labels, it will be much easier to tell which parameter is which, and to get them into the correct order.</span></span>  
  
  <span data-ttu-id="cf525-116">有关 functoid 输入参数的正确顺序的权威信息，请参阅**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="cf525-116">For definitive information about the correct order of functoid input parameters, see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cf525-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf525-117">See Also</span></span>  
 <span data-ttu-id="cf525-118">[配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="cf525-118">[Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md) </span></span>  
 <span data-ttu-id="cf525-119">[配置脚本 Functoid](../core/how-to-configure-the-scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="cf525-119">[Configure the Scripting Functoid](../core/how-to-configure-the-scripting-functoid.md) </span></span>  
 [<span data-ttu-id="cf525-120">配置“表循环”和“表提取程序”Functoid</span><span class="sxs-lookup"><span data-stu-id="cf525-120">Configure the Table Looping and Table Extractor Functoids</span></span>](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)