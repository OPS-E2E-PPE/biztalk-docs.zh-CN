---
title: 如何添加添加 Functoid 映射到 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccdd79a2-b70f-489b-8711-e00a50d8e2d8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4cfeabbbeac860e927854fb79c90d2b1608b9c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015270"
---
# <a name="how-to-add-assert-functoids-to-a-map"></a><span data-ttu-id="f298c-102">如何向映射中添加“添加”Functoid</span><span class="sxs-lookup"><span data-stu-id="f298c-102">How to Add Assert Functoids to a Map</span></span>
<span data-ttu-id="f298c-103">**Assert** functoid，您可以在映射中测试条件的假设。</span><span class="sxs-lookup"><span data-stu-id="f298c-103">The **Assert** functoid enables you to test your assumptions about conditions in your map.</span></span> <span data-ttu-id="f298c-104">例如，如果您执行某些计算来确定产品采购额外折扣，你可能会断言额外折扣，是通过使用判断 functoid 不超过 100 美元 (**Greater Than**或**Less Than**)。</span><span class="sxs-lookup"><span data-stu-id="f298c-104">For example, if you perform some calculations to determine an additional discount on product purchases, you might assert that the additional discount be no more than $100 by using a logical functoid (**Greater Than** or **Less Than**).</span></span>  

> [!NOTE]
>  <span data-ttu-id="f298c-105">**Assert** functoid 才会触发在开发版本时，或者当**生成调试信息**中的项目生成设置的属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="f298c-105">The **Assert** functoid only fires in development builds or when the **Generate Debugging Information** property in the project build settings is set to **True**.</span></span> <span data-ttu-id="f298c-106">BizTalk 应用程序部署的编译时，**生成调试信息**属性设置为**False** （默认值），忽略断言。</span><span class="sxs-lookup"><span data-stu-id="f298c-106">When your BizTalk application is compiled for deployment and the **Generate Debugging Information** property is set to **False** (the default), assertions are ignored.</span></span>  

 <span data-ttu-id="f298c-107">有关概念性信息**Assert** functoid，请参阅[断言 Functoid](../core/assert-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="f298c-107">For conceptual information about the **Assert** functoid, see [Assert Functoid](../core/assert-functoid.md).</span></span>  

## <a name="add-the-assert-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="f298c-108">向映射添加添加 functoid 并对其进行配置</span><span class="sxs-lookup"><span data-stu-id="f298c-108">Add the Assert functoid to a map and configure it</span></span>  

1. <span data-ttu-id="f298c-109">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。</span><span class="sxs-lookup"><span data-stu-id="f298c-109">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span> <span data-ttu-id="f298c-110">此时，将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="f298c-110">The list of advanced functoids in the chosen category appears.</span></span>  

2. <span data-ttu-id="f298c-111">拖动**Assert** functoid (![添加 functoid](../core/media/advanced-assert-functoid.gif "advanced_assert_functoid")) 从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="f298c-111">Drag the **Assert** functoid (![Assert functoid](../core/media/advanced-assert-functoid.gif "advanced_assert_functoid")) from the Toolbox to the appropriate location on a grid page.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="f298c-112">该 functoid 将放置到显示的网格页上。</span><span class="sxs-lookup"><span data-stu-id="f298c-112">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="f298c-113">如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。</span><span class="sxs-lookup"><span data-stu-id="f298c-113">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span> 
   >    
   >  <span data-ttu-id="f298c-114">如果构造使用多个 functoid 的映射，您需要考虑其相对的从左到右位置。</span><span class="sxs-lookup"><span data-stu-id="f298c-114">If you are constructing a map that uses more than one functoid, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="f298c-115">Functoid 是按照从左到右的顺序执行的。</span><span class="sxs-lookup"><span data-stu-id="f298c-115">Functoids are executed from left to right.</span></span> <span data-ttu-id="f298c-116">一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="f298c-116">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  

3. <span data-ttu-id="f298c-117">该 functoid 必须正好有三个输入参数，并且生成一个输出参数。</span><span class="sxs-lookup"><span data-stu-id="f298c-117">The functoid must have exactly three input parameters and it generates one output parameter.</span></span> <span data-ttu-id="f298c-118">若要建立的第一个参数**Assert** functoid 创建输入的链接： 从某个其他拖动输出**逻辑**functoid 或从输入的实例消息中的布尔变量字段。</span><span class="sxs-lookup"><span data-stu-id="f298c-118">To establish the first parameter for the **Assert** functoid, create an input link by dragging the output from some other **Logical** functoid or from a variable Boolean field in the input instance message.</span></span>  

4. <span data-ttu-id="f298c-119">若要建立第二个输入的参数**Assert** functoid，由源架构中的字段节点创建输入的链接**Assert** functoid，或插入一个常量。</span><span class="sxs-lookup"><span data-stu-id="f298c-119">To establish the second input parameter for the **Assert** functoid, create an input link by a field node in the source schema to the **Assert** functoid, or insert a constant.</span></span>  

5. <span data-ttu-id="f298c-120">若要建立第三个输入的参数**Assert** functoid，由源架构中的字段节点创建输入的链接**Assert** functoid，或插入一个常量。</span><span class="sxs-lookup"><span data-stu-id="f298c-120">To establish the third input parameter for the **Assert** functoid, create an input link by a field node in the source schema to the **Assert** functoid, or insert a constant.</span></span>  

6. <span data-ttu-id="f298c-121">若要使用的输出参数**Assert** functoid，创建输出链接： 将**Assert** functoid 到目标架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="f298c-121">To use the output parameter from the **Assert** functoid, create an output link by dragging the **Assert** functoid to a field in the destination schema.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="f298c-122">与其他 functoid 的输出一样**Assert** functoid 可以用作另一个 functoid 的输入。</span><span class="sxs-lookup"><span data-stu-id="f298c-122">As with other functoids, the output of the **Assert** functoid can be used as input to another functoid.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f298c-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="f298c-123">See Also</span></span>  
- <span data-ttu-id="f298c-124">**声明 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="f298c-124">**Assert Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>   
- [<span data-ttu-id="f298c-125">向映射添加高级 Functoid</span><span class="sxs-lookup"><span data-stu-id="f298c-125">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)
