---
title: 如何编辑 XPath 选择器以处理多个记录 |Microsoft Docs
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
ms.openlocfilehash: 826158471dbff3116df55a00f653740ab183e2d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338053"
---
# <a name="how-to-edit-xpath-selector-to-process-multiple-records"></a><span data-ttu-id="1e71e-102">如何编辑 XPath 选择器以处理多个记录</span><span class="sxs-lookup"><span data-stu-id="1e71e-102">How to Edit XPath Selector to Process Multiple Records</span></span>
<span data-ttu-id="1e71e-103">单独的子 Typedxmldocument 时，会创建将 TypedXmlDocument 添加到引擎中;请参阅[Assert](../core/assert.md)。</span><span class="sxs-lookup"><span data-stu-id="1e71e-103">Separate child TypedXmlDocuments are created when a TypedXmlDocument is asserted into the engine; see [Assert](../core/assert.md).</span></span> <span data-ttu-id="1e71e-104">在引擎确定哪些子 Typedxmldocument 创建基于在规则中定义的 XPath 选择器。</span><span class="sxs-lookup"><span data-stu-id="1e71e-104">The engine determines which child TypedXmlDocuments to create based on the XPath selectors defined in the rules.</span></span> <span data-ttu-id="1e71e-105">生成在编辑器中的规则时，XPath 选择器值默认为事实浏览器中的 XML 架构选项卡中选择的节点上方的节点。</span><span class="sxs-lookup"><span data-stu-id="1e71e-105">When you build rules in the Composer, the XPath Selector value defaults to the node above the node selected in the XML Schemas tab in the Facts Explorer.</span></span> <span data-ttu-id="1e71e-106">XPath 字段值默认为所选节点本身，相对于其父节点。</span><span class="sxs-lookup"><span data-stu-id="1e71e-106">The XPath Field value defaults to the selected node itself, relative to its parent node.</span></span>  
  
 <span data-ttu-id="1e71e-107">在某些情况下您可能想要自定义默认的生成规则时创建编辑器的 XPath。</span><span class="sxs-lookup"><span data-stu-id="1e71e-107">In some situations you may want to customize the default XPath that the Composer creates when building rules.</span></span> <span data-ttu-id="1e71e-108">假定下面的示例 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="1e71e-108">Assume the following sample XML document.</span></span>  
  
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
  
 <span data-ttu-id="1e71e-109">假设你想要生成的规则，计算每个 Orderline 总计值。</span><span class="sxs-lookup"><span data-stu-id="1e71e-109">Assume that you want to build a rule that calculates the Total value for each Orderline.</span></span> <span data-ttu-id="1e71e-110">你的规则如以下所示。</span><span class="sxs-lookup"><span data-stu-id="1e71e-110">Your rule would look like the following.</span></span>  
  
 <span data-ttu-id="1e71e-111">IF 1==1</span><span class="sxs-lookup"><span data-stu-id="1e71e-111">IF 1==1</span></span>  
  
 <span data-ttu-id="1e71e-112">然后<strong>/o/Orderline/</strong>总 = (<strong>顺序/Orderline/Hat/</strong>成本 + <strong>顺序/Orderline/Shirt/</strong>成本)</span><span class="sxs-lookup"><span data-stu-id="1e71e-112">THEN <strong>/Order/Orderline/</strong>Total = (<strong>/Order/Orderline/Hat/</strong>Cost + <strong>/Order/Orderline/Shirt/</strong>Cost)</span></span>  
  
 <span data-ttu-id="1e71e-113">Xpath 的粗体部分表示选择器部分，其余部分表示字段 XPath。</span><span class="sxs-lookup"><span data-stu-id="1e71e-113">The bold portion of the XPaths indicate the Selector portion and the remainder represents the Field XPath.</span></span> <span data-ttu-id="1e71e-114">这些是编辑器生成的默认值。</span><span class="sxs-lookup"><span data-stu-id="1e71e-114">These are the defaults built by the Composer.</span></span> <span data-ttu-id="1e71e-115">运行此策略，但是，将导致创建 6 个对象-2 个 Orderline 对象、 2 个 Hat 对象和 2 个 Shirt 对象。</span><span class="sxs-lookup"><span data-stu-id="1e71e-115">Running this policy, however, would result in the creation of 6 objects—2 Orderline objects, 2 Hat objects, and 2 Shirt objects.</span></span> <span data-ttu-id="1e71e-116">将为 Hat 和 Shirt 对象的每个组合计算 Orderline 总计和总计将始终设置为相同的值，该值源自上次执行规则。</span><span class="sxs-lookup"><span data-stu-id="1e71e-116">The Orderline totals would be calculated for each combination of Hat and Shirt objects and the totals would always be set to the same value, which resulted from the last execution of the rule.</span></span> <span data-ttu-id="1e71e-117">该规则将触发 8 次。</span><span class="sxs-lookup"><span data-stu-id="1e71e-117">The rule would fire 8 times.</span></span> <span data-ttu-id="1e71e-118">这是不是为想在此方案中。</span><span class="sxs-lookup"><span data-stu-id="1e71e-118">This is not what is intended in this scenario.</span></span>  
  
 <span data-ttu-id="1e71e-119">一种解决方案是编辑 XPath 值是按如下所示。</span><span class="sxs-lookup"><span data-stu-id="1e71e-119">One solution would be to edit the XPath values to be as follows.</span></span>  
  
 <span data-ttu-id="1e71e-120">IF 1==1</span><span class="sxs-lookup"><span data-stu-id="1e71e-120">IF 1==1</span></span>  
  
 <span data-ttu-id="1e71e-121">然后<strong>/o/Orderline/</strong>总 = (<strong>/o/Orderline/</strong>Hat/成本 + <strong>/o/Orderline/</strong>Shirt/成本)</span><span class="sxs-lookup"><span data-stu-id="1e71e-121">THEN <strong>/Order/Orderline/</strong>Total = (<strong>/Order/Orderline/</strong>Hat/Cost + <strong>/Order/Orderline/</strong>Shirt/Cost)</span></span>  
  
 <span data-ttu-id="1e71e-122">所有三个字段的选择器 XPath 值已设置为同一 /Order/Orderline 值并相应地编辑的字段 XPath 值。</span><span class="sxs-lookup"><span data-stu-id="1e71e-122">The Selector XPath values for all three fields have been set to the same /Order/Orderline value and the Field XPath values have been edited accordingly.</span></span> <span data-ttu-id="1e71e-123">这是通过在 XML 架构选项卡中选择节点时更改属性窗口中的 XPath 选择器和 XPath 字段值。这应在将字段拖动到规则参数之前完成。</span><span class="sxs-lookup"><span data-stu-id="1e71e-123">This is done by changing the XPath Selector and XPath Field values in the Properties window when a node is selected in the XML Schemas tab. This should be done prior to dragging the field into a rule argument.</span></span>  
  
 <span data-ttu-id="1e71e-124">执行此更改的策略将导致每个 Orderline 基于该 Orderline 内 Shirt 和 Hat 节点的 Cost 值正确计算出的总计值。</span><span class="sxs-lookup"><span data-stu-id="1e71e-124">Executing the policy with this change would result in the Total value being correctly calculated for each Orderline based on the Cost values of the Shirt and Hat nodes within that Orderline.</span></span>