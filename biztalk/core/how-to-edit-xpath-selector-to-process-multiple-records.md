---
title: 如何编辑 XPath 选择器来处理多个记录 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, editing multiple records
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: ef7e1f8d-2e29-4cef-b558-0090648bffc0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34c9b45e3fce9f4ad5730d7f03d2a568b3701742
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254157"
---
# <a name="how-to-edit-xpath-selector-to-process-multiple-records"></a><span data-ttu-id="ba1f2-102">如何编辑 XPath 选择器以处理多个记录</span><span class="sxs-lookup"><span data-stu-id="ba1f2-102">How to Edit XPath Selector to Process Multiple Records</span></span>
<span data-ttu-id="ba1f2-103">单独的子 TypedXmlDocuments 时创建 TypedXmlDocument 断言引擎;请参阅[断言](../core/assert.md)。</span><span class="sxs-lookup"><span data-stu-id="ba1f2-103">Separate child TypedXmlDocuments are created when a TypedXmlDocument is asserted into the engine; see [Assert](../core/assert.md).</span></span> <span data-ttu-id="ba1f2-104">引擎将根据规则中定义的 XPath 选择器决定创建哪些子 TypedXmlDocument。</span><span class="sxs-lookup"><span data-stu-id="ba1f2-104">The engine determines which child TypedXmlDocuments to create based on the XPath selectors defined in the rules.</span></span> <span data-ttu-id="ba1f2-105">在编辑器中生成规则时，XPath 选择器的值默认为事实浏览器的“XML 架构”选项卡中所选节点之上的那个节点。</span><span class="sxs-lookup"><span data-stu-id="ba1f2-105">When you build rules in the Composer, the XPath Selector value defaults to the node above the node selected in the XML Schemas tab in the Facts Explorer.</span></span> <span data-ttu-id="ba1f2-106">相对于所选节点的父节点，XPath 字段的值默认为所选节点本身。</span><span class="sxs-lookup"><span data-stu-id="ba1f2-106">The XPath Field value defaults to the selected node itself, relative to its parent node.</span></span>  
  
 <span data-ttu-id="ba1f2-107">在某些情况下，您可能希望自定义编辑器在生成规则时创建的默认 XPath。</span><span class="sxs-lookup"><span data-stu-id="ba1f2-107">In some situations you may want to customize the default XPath that the Composer creates when building rules.</span></span> <span data-ttu-id="ba1f2-108">假设存在以下示例 XML 文档：</span><span class="sxs-lookup"><span data-stu-id="ba1f2-108">Assume the following sample XML document.</span></span>  
  
```  
<Order>  
   <Orderline>  
      <Hat style="Baseball">                        
         <Cost>10</Cost>  
      </Hat>  
      <Shirt color="Black">  
         <Cost>20</Cost>  
      </Shirt>  
      <Total></Total>  
   </Orderline>  
   <Orderline>  
      <Hat style="Bowler">                        
         <Cost>20</Cost>  
      </Hat>  
      <Shirt color="Red">  
         <Cost>20</Cost>  
      </Shirt>  
      <Total></Total>  
   </Orderline>  
</Order>  
```  
  
 <span data-ttu-id="ba1f2-109">假设您希望生成计算每个 Orderline 的 Total 值的规则。</span><span class="sxs-lookup"><span data-stu-id="ba1f2-109">Assume that you want to build a rule that calculates the Total value for each Orderline.</span></span> <span data-ttu-id="ba1f2-110">该规则应与下面所列相似：</span><span class="sxs-lookup"><span data-stu-id="ba1f2-110">Your rule would look like the following.</span></span>  
  
 <span data-ttu-id="ba1f2-111">IF 1==1</span><span class="sxs-lookup"><span data-stu-id="ba1f2-111">IF 1==1</span></span>  
  
 <span data-ttu-id="ba1f2-112">然后 **/order/Orderline/** 总 = (**/顺序/Orderline/Hat/** 成本 + **/顺序/Orderline/Shirt/** 成本)</span><span class="sxs-lookup"><span data-stu-id="ba1f2-112">THEN **/Order/Orderline/** Total = (**/Order/Orderline/Hat/** Cost + **/Order/Orderline/Shirt/** Cost)</span></span>  
  
 <span data-ttu-id="ba1f2-113">XPath 的粗体部分表示选择器部分，其余部分表示字段 XPath。</span><span class="sxs-lookup"><span data-stu-id="ba1f2-113">The bold portion of the XPaths indicate the Selector portion and the remainder represents the Field XPath.</span></span> <span data-ttu-id="ba1f2-114">这些都是编辑器生成的默认值。</span><span class="sxs-lookup"><span data-stu-id="ba1f2-114">These are the defaults built by the Composer.</span></span> <span data-ttu-id="ba1f2-115">但是，运行此策略将导致创建 6 个对象：2 个 Orderline 对象、2 个 Hat 对象和 2 个 Shirt 对象。</span><span class="sxs-lookup"><span data-stu-id="ba1f2-115">Running this policy, however, would result in the creation of 6 objects—2 Orderline objects, 2 Hat objects, and 2 Shirt objects.</span></span> <span data-ttu-id="ba1f2-116">Orderline 总计值将针对 Hat 对象和 Shirt 对象的每个组合来进行计算，并始终设置为同一值，该值源自上次执行规则所得的结果。</span><span class="sxs-lookup"><span data-stu-id="ba1f2-116">The Orderline totals would be calculated for each combination of Hat and Shirt objects and the totals would always be set to the same value, which resulted from the last execution of the rule.</span></span> <span data-ttu-id="ba1f2-117">该规则将触发 8 次。</span><span class="sxs-lookup"><span data-stu-id="ba1f2-117">The rule would fire 8 times.</span></span> <span data-ttu-id="ba1f2-118">然而，这并不是本方案的预期结果。</span><span class="sxs-lookup"><span data-stu-id="ba1f2-118">This is not what is intended in this scenario.</span></span>  
  
 <span data-ttu-id="ba1f2-119">一种解决方案是按如下所示编辑 XPath 值：</span><span class="sxs-lookup"><span data-stu-id="ba1f2-119">One solution would be to edit the XPath values to be as follows.</span></span>  
  
 <span data-ttu-id="ba1f2-120">IF 1==1</span><span class="sxs-lookup"><span data-stu-id="ba1f2-120">IF 1==1</span></span>  
  
 <span data-ttu-id="ba1f2-121">然后 **/order/Orderline/** 总 = (**/order/Orderline/** Hat/成本 + **/order/Orderline/** Shirt/成本)</span><span class="sxs-lookup"><span data-stu-id="ba1f2-121">THEN **/Order/Orderline/** Total = (**/Order/Orderline/** Hat/Cost + **/Order/Orderline/** Shirt/Cost)</span></span>  
  
 <span data-ttu-id="ba1f2-122">所有三个字段的选择器 XPath 值均已设置为同一 /Order/Orderline 值，并且字段 XPath 值也已进行相应的编辑。</span><span class="sxs-lookup"><span data-stu-id="ba1f2-122">The Selector XPath values for all three fields have been set to the same /Order/Orderline value and the Field XPath values have been edited accordingly.</span></span> <span data-ttu-id="ba1f2-123">这是在“XML 架构”选项卡中选择节点后，通过更改“属性”窗口中的 XPath 选择器和 XPath 字段值来完成的。该操作应在将字段拖到规则参数中之前完成。</span><span class="sxs-lookup"><span data-stu-id="ba1f2-123">This is done by changing the XPath Selector and XPath Field values in the Properties window when a node is selected in the XML Schemas tab. This should be done prior to dragging the field into a rule argument.</span></span>  
  
 <span data-ttu-id="ba1f2-124">如果执行包含此更改的策略，则会根据每个 Orderline 内 Shirt 节点和 Hat 节点的 Cost 值正确计算出该 Orderline 的 Total 值。</span><span class="sxs-lookup"><span data-stu-id="ba1f2-124">Executing the policy with this change would result in the Total value being correctly calculated for each Orderline based on the Cost values of the Shirt and Hat nodes within that Orderline.</span></span>