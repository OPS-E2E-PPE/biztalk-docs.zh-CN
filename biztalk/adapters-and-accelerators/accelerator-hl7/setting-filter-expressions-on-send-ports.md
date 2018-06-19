---
title: 在发送端口上设置筛选器表达式 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, context properties
- filtering, send ports
- send ports, filtering
- context properties, send ports
- context properties, filtering
- filtering, context properties
ms.assetid: 48c7c83b-9464-4ed9-bd8d-cf5b75e16702
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b94497f4e1412f81c36df3195994aafa32ecc451
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206077"
---
# <a name="setting-filter-expressions-on-send-ports"></a><span data-ttu-id="a2edd-102">发送端口上设置筛选器表达式</span><span class="sxs-lookup"><span data-stu-id="a2edd-102">Setting Filter Expressions on Send Ports</span></span>
<span data-ttu-id="a2edd-103">您设置上下文属性筛选器表达式中发送端口来控制端口所发送的内容。</span><span class="sxs-lookup"><span data-stu-id="a2edd-103">You set context properties in filter expressions on the send port to control what the port sends.</span></span> <span data-ttu-id="a2edd-104">提供了灵活地如何筛选属性的运算符的数量，可以设置筛选器表达式 (存在的相等运算符或不等、，大于、 大于或等于、 小于且小于或等于)。</span><span class="sxs-lookup"><span data-stu-id="a2edd-104">You can set the filter expressions with a number of operators that offer you flexibility in how you filter the property (equality or inequality, exists, greater than, great than or equal to, less than, and less than or equal to).</span></span>  
  
### <a name="to-set-the-filter-expression-on-a-send-port"></a><span data-ttu-id="a2edd-105">若要在发送端口上设置筛选器表达式</span><span class="sxs-lookup"><span data-stu-id="a2edd-105">To set the filter expression on a send port</span></span>  
  
1.  <span data-ttu-id="a2edd-106">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk 应用程序1** （或另一个应用程序）。</span><span class="sxs-lookup"><span data-stu-id="a2edd-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1** (or another application).</span></span> <span data-ttu-id="a2edd-107">单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="a2edd-107">Click **Send Ports**.</span></span>  
  
2.  <span data-ttu-id="a2edd-108">右键单击你想要设置的筛选器表达式，，然后单击发送端口**属性**。</span><span class="sxs-lookup"><span data-stu-id="a2edd-108">Right-click the send port that you want to set the filter expression for, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="a2edd-109">在控制台树中的发送端口属性对话框中，单击**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="a2edd-109">In the console tree of the Send Port Properties dialog box, click **Filters**.</span></span>  
  
4.  <span data-ttu-id="a2edd-110">单击中的文本框**属性**列，然后选择上下文属性**属性**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a2edd-110">Click the text box in the **Property** column, and then select the context property from the **Property** drop-down list.</span></span>  
  
5.  <span data-ttu-id="a2edd-111">单击**运算符**框中的行的属性，并从下拉列表中选择该属性的运算符。</span><span class="sxs-lookup"><span data-stu-id="a2edd-111">Click the **Operator** box in the row for the property, and select the operator for the property from the drop-down list.</span></span>  
  
6.  <span data-ttu-id="a2edd-112">单击**值**框中，将该属性的行，然后键入值表达式。</span><span class="sxs-lookup"><span data-stu-id="a2edd-112">Click the **Value** box in the row for the property, and type a value expression.</span></span>  
  
7.  <span data-ttu-id="a2edd-113">如果你需要添加筛选器表达式的另一个子句，请单击**Group By**框中，将该属性的行，然后选择**和**或**或**以确定之间的关系子句。</span><span class="sxs-lookup"><span data-stu-id="a2edd-113">If you need to add another  clause for the filter expression, click the **Group By** box in the row for the property, and select **And** or **Or** to determine the relationship of the clauses.</span></span>  
  
8.  <span data-ttu-id="a2edd-114">重复步骤 4 到 6 以添加另一个筛选器子句。</span><span class="sxs-lookup"><span data-stu-id="a2edd-114">Repeat steps 4 through 6 to add another filter clause.</span></span>  
  
9. <span data-ttu-id="a2edd-115">验证是否正确在底部窗格中的筛选器表达式**筛选器**窗格。</span><span class="sxs-lookup"><span data-stu-id="a2edd-115">Verify that the filter expression is correct in the pane at the bottom of the **Filters** pane.</span></span>  
  
10. <span data-ttu-id="a2edd-116">在添加所有筛选子句后，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a2edd-116">When you have added all filter clauses, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2edd-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2edd-117">See Also</span></span>  
 <span data-ttu-id="a2edd-118">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a2edd-118">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 [<span data-ttu-id="a2edd-119">使用上下文属性</span><span class="sxs-lookup"><span data-stu-id="a2edd-119">Using Context Properties</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-context-properties.md)