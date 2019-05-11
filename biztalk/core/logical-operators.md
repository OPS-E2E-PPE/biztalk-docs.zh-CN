---
title: 逻辑运算符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8aaceb64-a5a0-462a-a0eb-8352bed999e5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 940f9a1c3604108de58a44aa6998dcdd82e86abb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380572"
---
# <a name="logical-operators"></a><span data-ttu-id="a41ee-102">逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="a41ee-102">Logical Operators</span></span>
<span data-ttu-id="a41ee-103">使用逻辑 AND、 逻辑或业务规则框架支持和逻辑 NOT 运算符在创建业务规则。</span><span class="sxs-lookup"><span data-stu-id="a41ee-103">The Business Rules Framework supports using the logical AND, logical OR, and logical NOT operators in creating business rules.</span></span> <span data-ttu-id="a41ee-104">下表描述的逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="a41ee-104">The following table describes the logical operators.</span></span>  
  
|<span data-ttu-id="a41ee-105">逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="a41ee-105">Logical Operator</span></span>|<span data-ttu-id="a41ee-106">Description</span><span class="sxs-lookup"><span data-stu-id="a41ee-106">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="a41ee-107">**AND**</span><span class="sxs-lookup"><span data-stu-id="a41ee-107">**AND**</span></span>|<span data-ttu-id="a41ee-108">返回 **，则返回 true**如果两个操作数的计算结果为**true**; 否则返回**false**。</span><span class="sxs-lookup"><span data-stu-id="a41ee-108">Returns **true** if both the operands evaluate to **true**; otherwise returns **false**.</span></span>|  
|<span data-ttu-id="a41ee-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="a41ee-109">**OR**</span></span>|<span data-ttu-id="a41ee-110">返回 **，则返回 true**如果其中一个操作数计算结果为**true**，否则将返回**false**。</span><span class="sxs-lookup"><span data-stu-id="a41ee-110">Returns **true** if one of the operands evaluates to **true**, otherwise returns **false**.</span></span>|  
|<span data-ttu-id="a41ee-111">**NOT**</span><span class="sxs-lookup"><span data-stu-id="a41ee-111">**NOT**</span></span>|<span data-ttu-id="a41ee-112">返回 **，则返回 true**如果操作数计算结果为**false**，否则将返回**false**。</span><span class="sxs-lookup"><span data-stu-id="a41ee-112">Returns **true** if the operand evaluates to **false**, otherwise returns **false**.</span></span>|  
  
 <span data-ttu-id="a41ee-113">不同类型的操作数时，规则引擎将转换一个要与其他参数，则转换的类型为通用类型的两个参数的类型匹配之前对表达式求值的参数的类型。</span><span class="sxs-lookup"><span data-stu-id="a41ee-113">When operands are of different types, the rule engine converts type of one of the parameters to match the type of the other parameter or converts types of both the parameters to a common type before evaluating the expression.</span></span>  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a><span data-ttu-id="a41ee-114">若要在业务规则中使用逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="a41ee-114">To use a logical operator in a business rule</span></span>  
 <span data-ttu-id="a41ee-115">使用以下过程在业务规则中使用逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="a41ee-115">Use the following procedure to use a logical operator in a business rule.</span></span>  
  
1.  <span data-ttu-id="a41ee-116">在中**IF**窗格中的业务规则编辑器中，右键单击**条件**节点，并选择你想要添加到逻辑表达式的逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="a41ee-116">In the **IF** pane of Business Rule Composer, right-click the **Conditions** node, and then select the logical operator that you wish to add to the logical expression.</span></span>  
  
2.  <span data-ttu-id="a41ee-117">右键单击该逻辑运算符，并添加谓词或你想要添加的嵌套逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="a41ee-117">Right-click the logical operator, and add the predicates or nested logical operators you want to add.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a41ee-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a41ee-118">See Also</span></span>  
 [<span data-ttu-id="a41ee-119">算术运算符</span><span class="sxs-lookup"><span data-stu-id="a41ee-119">Arithmetic Operators</span></span>](../core/arithmetic-operators.md)