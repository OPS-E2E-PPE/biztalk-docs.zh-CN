---
title: 在发送端口上设置筛选器表达式 |Microsoft Docs
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
ms.openlocfilehash: ab5fcc0e4245599dfffb29f6f5690707df325c04
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291566"
---
# <a name="setting-filter-expressions-on-send-ports"></a><span data-ttu-id="0a6c3-102">发送端口设置筛选器表达式</span><span class="sxs-lookup"><span data-stu-id="0a6c3-102">Setting Filter Expressions on Send Ports</span></span>
<span data-ttu-id="0a6c3-103">若要控制端口发送的内容在发送端口上筛选器表达式中设置上下文属性。</span><span class="sxs-lookup"><span data-stu-id="0a6c3-103">You set context properties in filter expressions on the send port to control what the port sends.</span></span> <span data-ttu-id="0a6c3-104">可以使用大量运算符，使你能够灵活中如何筛选该属性设置筛选器表达式 (等式或不等式，存在，大于、 大于或等于、 小于且小于或等于)。</span><span class="sxs-lookup"><span data-stu-id="0a6c3-104">You can set the filter expressions with a number of operators that offer you flexibility in how you filter the property (equality or inequality, exists, greater than, great than or equal to, less than, and less than or equal to).</span></span>  
  
### <a name="to-set-the-filter-expression-on-a-send-port"></a><span data-ttu-id="0a6c3-105">若要在发送端口上设置筛选器表达式</span><span class="sxs-lookup"><span data-stu-id="0a6c3-105">To set the filter expression on a send port</span></span>  
  
1.  <span data-ttu-id="0a6c3-106">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk 应用程序1** （或另一个应用程序）。</span><span class="sxs-lookup"><span data-stu-id="0a6c3-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1** (or another application).</span></span> <span data-ttu-id="0a6c3-107">单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="0a6c3-107">Click **Send Ports**.</span></span>  
  
2.  <span data-ttu-id="0a6c3-108">右键单击你想要设置的筛选器表达式，，然后单击发送端口**属性**。</span><span class="sxs-lookup"><span data-stu-id="0a6c3-108">Right-click the send port that you want to set the filter expression for, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="0a6c3-109">在控制台树中的发送端口属性对话框中，单击**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="0a6c3-109">In the console tree of the Send Port Properties dialog box, click **Filters**.</span></span>  
  
4.  <span data-ttu-id="0a6c3-110">单击中的文本框**属性**列中，然后选择上下文属性从**属性**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="0a6c3-110">Click the text box in the **Property** column, and then select the context property from the **Property** drop-down list.</span></span>  
  
5.  <span data-ttu-id="0a6c3-111">单击**运算符**框中的行的属性，并从下拉列表中选择该属性的运算符。</span><span class="sxs-lookup"><span data-stu-id="0a6c3-111">Click the **Operator** box in the row for the property, and select the operator for the property from the drop-down list.</span></span>  
  
6.  <span data-ttu-id="0a6c3-112">单击**值**框的属性，行中，键入值表达式。</span><span class="sxs-lookup"><span data-stu-id="0a6c3-112">Click the **Value** box in the row for the property, and type a value expression.</span></span>  
  
7.  <span data-ttu-id="0a6c3-113">如果需要添加另一个子句的筛选器表达式，请单击**Group By**框中的属性行，然后选择**并**或**或**来确定之间的关系子句。</span><span class="sxs-lookup"><span data-stu-id="0a6c3-113">If you need to add another  clause for the filter expression, click the **Group By** box in the row for the property, and select **And** or **Or** to determine the relationship of the clauses.</span></span>  
  
8.  <span data-ttu-id="0a6c3-114">重复步骤 4 至 6 可添加另一个筛选器子句。</span><span class="sxs-lookup"><span data-stu-id="0a6c3-114">Repeat steps 4 through 6 to add another filter clause.</span></span>  
  
9. <span data-ttu-id="0a6c3-115">验证筛选器表达式是在底部窗格中正确**筛选器**窗格。</span><span class="sxs-lookup"><span data-stu-id="0a6c3-115">Verify that the filter expression is correct in the pane at the bottom of the **Filters** pane.</span></span>  
  
10. <span data-ttu-id="0a6c3-116">已添加所有筛选器子句，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0a6c3-116">When you have added all filter clauses, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a6c3-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a6c3-117">See Also</span></span>  
 <span data-ttu-id="0a6c3-118">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="0a6c3-118">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 [<span data-ttu-id="0a6c3-119">使用上下文属性</span><span class="sxs-lookup"><span data-stu-id="0a6c3-119">Using Context Properties</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-context-properties.md)