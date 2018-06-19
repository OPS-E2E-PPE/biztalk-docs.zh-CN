---
title: 如何添加断言向地图 Functoid |Microsoft 文档
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
ms.openlocfilehash: 553daa0c6e97d09e8284d2369e801c5d2ff8beee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247757"
---
# <a name="how-to-add-assert-functoids-to-a-map"></a><span data-ttu-id="8b689-102">如何向映射中添加“添加”Functoid</span><span class="sxs-lookup"><span data-stu-id="8b689-102">How to Add Assert Functoids to a Map</span></span>
<span data-ttu-id="8b689-103">**断言**functoid 使您能够在你的代码图中测试你的假设有关条件。</span><span class="sxs-lookup"><span data-stu-id="8b689-103">The **Assert** functoid enables you to test your assumptions about conditions in your map.</span></span> <span data-ttu-id="8b689-104">例如，如果你执行一些计算来确定在产品采购额外折扣，你可能断言额外折扣，通过使用逻辑 functoid 是不能超过 100 美元 (**大于**或**Less Than**)。</span><span class="sxs-lookup"><span data-stu-id="8b689-104">For example, if you perform some calculations to determine an additional discount on product purchases, you might assert that the additional discount be no more than $100 by using a logical functoid (**Greater Than** or **Less Than**).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b689-105">**断言**functoid 才会触发开发内部版本中，或者当**生成调试信息**项目生成设置的属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="8b689-105">The **Assert** functoid only fires in development builds or when the **Generate Debugging Information** property in the project build settings is set to **True**.</span></span> <span data-ttu-id="8b689-106">BizTalk 应用程序部署的编译时与**生成调试信息**属性设置为**False** （默认值）、 断言将被忽略。</span><span class="sxs-lookup"><span data-stu-id="8b689-106">When your BizTalk application is compiled for deployment and the **Generate Debugging Information** property is set to **False** (the default), assertions are ignored.</span></span>  
  
 <span data-ttu-id="8b689-107">有关概念性信息**断言**functoid，请参阅[断言 Functoid](../core/assert-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="8b689-107">For conceptual information about the **Assert** functoid, see [Assert Functoid](../core/assert-functoid.md).</span></span>  
  
## <a name="add-the-assert-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="8b689-108">在向地图添加添加 functoid，并将其配置</span><span class="sxs-lookup"><span data-stu-id="8b689-108">Add the Assert functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="8b689-109">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。</span><span class="sxs-lookup"><span data-stu-id="8b689-109">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span> <span data-ttu-id="8b689-110">此时，将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="8b689-110">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="8b689-111">拖动**断言**functoid (![断言 functoid](../core/media/advanced-assert-functoid.gif "advanced_assert_functoid")) 从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="8b689-111">Drag the **Assert** functoid (![Assert functoid](../core/media/advanced-assert-functoid.gif "advanced_assert_functoid")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8b689-112">该 functoid 将放置到显示的网格页上。</span><span class="sxs-lookup"><span data-stu-id="8b689-112">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="8b689-113">如果你想要将 functoid 放到不同的网格页面上，你需要首先显示其他网格该页。</span><span class="sxs-lookup"><span data-stu-id="8b689-113">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span> 
    >    
    >  <span data-ttu-id="8b689-114">如果你在构造的地图，使用多个 functoid，你需要考虑它们相对的从左到右位置。</span><span class="sxs-lookup"><span data-stu-id="8b689-114">If you are constructing a map that uses more than one functoid, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="8b689-115">Functoid 是按照从左到右的顺序执行的。</span><span class="sxs-lookup"><span data-stu-id="8b689-115">Functoids are executed from left to right.</span></span> <span data-ttu-id="8b689-116">一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="8b689-116">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="8b689-117">该 functoid 必须正好有三个输入参数，并且生成一个输出参数。</span><span class="sxs-lookup"><span data-stu-id="8b689-117">The functoid must have exactly three input parameters and it generates one output parameter.</span></span> <span data-ttu-id="8b689-118">若要建立的第一个参数**断言**functoid，通过将输出拖从其他创建输入的链接**逻辑**functoid 或从输入的实例消息中的变量布尔字段。</span><span class="sxs-lookup"><span data-stu-id="8b689-118">To establish the first parameter for the **Assert** functoid, create an input link by dragging the output from some other **Logical** functoid or from a variable Boolean field in the input instance message.</span></span>  
  
4.  <span data-ttu-id="8b689-119">若要建立的第二个输入的参数**断言**functoid，源架构中的字段节点创建输入的链接**断言**functoid，或插入常量。</span><span class="sxs-lookup"><span data-stu-id="8b689-119">To establish the second input parameter for the **Assert** functoid, create an input link by a field node in the source schema to the **Assert** functoid, or insert a constant.</span></span>  
  
5.  <span data-ttu-id="8b689-120">若要建立的第三个输入的参数**断言**functoid，源架构中的字段节点创建输入的链接**断言**functoid，或插入常量。</span><span class="sxs-lookup"><span data-stu-id="8b689-120">To establish the third input parameter for the **Assert** functoid, create an input link by a field node in the source schema to the **Assert** functoid, or insert a constant.</span></span>  
  
6.  <span data-ttu-id="8b689-121">若要使用输出参数从**断言**functoid，通过拖动创建一条输出链接**断言**functoid 给目标架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="8b689-121">To use the output parameter from the **Assert** functoid, create an output link by dragging the **Assert** functoid to a field in the destination schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8b689-122">其他 functoid 的输出与**断言**functoid 可以用作输入另一个 functoid。</span><span class="sxs-lookup"><span data-stu-id="8b689-122">As with other functoids, the output of the **Assert** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b689-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b689-123">See Also</span></span>  
-  <span data-ttu-id="8b689-124">**断言 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="8b689-124">**Assert Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>   
-  [<span data-ttu-id="8b689-125">向地图添加高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="8b689-125">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)