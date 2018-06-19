---
title: 逻辑运算符 |Microsoft 文档
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
ms.openlocfilehash: 6e3b3c187e353babafd86590fdeacdc19fc115b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262069"
---
# <a name="logical-operators"></a><span data-ttu-id="23a26-102">逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="23a26-102">Logical Operators</span></span>
<span data-ttu-id="23a26-103">业务规则框架支持在创建业务规则时使用“逻辑与”、“逻辑或”和“逻辑非”运算符。</span><span class="sxs-lookup"><span data-stu-id="23a26-103">The Business Rules Framework supports using the logical AND, logical OR, and logical NOT operators in creating business rules.</span></span> <span data-ttu-id="23a26-104">下表介绍这些逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="23a26-104">The following table describes the logical operators.</span></span>  
  
|<span data-ttu-id="23a26-105">逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="23a26-105">Logical Operator</span></span>|<span data-ttu-id="23a26-106">Description</span><span class="sxs-lookup"><span data-stu-id="23a26-106">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="23a26-107">**AND**</span><span class="sxs-lookup"><span data-stu-id="23a26-107">**AND**</span></span>|<span data-ttu-id="23a26-108">返回**true**如果两个操作数的计算结果为**true**; 否则返回**false**。</span><span class="sxs-lookup"><span data-stu-id="23a26-108">Returns **true** if both the operands evaluate to **true**; otherwise returns **false**.</span></span>|  
|<span data-ttu-id="23a26-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="23a26-109">**OR**</span></span>|<span data-ttu-id="23a26-110">返回**true**如果其中一个操作数的计算结果为**true**，否则返回**false**。</span><span class="sxs-lookup"><span data-stu-id="23a26-110">Returns **true** if one of the operands evaluates to **true**, otherwise returns **false**.</span></span>|  
|<span data-ttu-id="23a26-111">**NOT**</span><span class="sxs-lookup"><span data-stu-id="23a26-111">**NOT**</span></span>|<span data-ttu-id="23a26-112">返回**true**如果操作数的计算结果为**false**，否则返回**false**。</span><span class="sxs-lookup"><span data-stu-id="23a26-112">Returns **true** if the operand evaluates to **false**, otherwise returns **false**.</span></span>|  
  
 <span data-ttu-id="23a26-113">当操作数为不同类型时，在计算表达式之前，规则引擎会将一个参数的类型转换为匹配其他参数的类型，或将两个参数类型都转换为常见类型。</span><span class="sxs-lookup"><span data-stu-id="23a26-113">When operands are of different types, the rule engine converts type of one of the parameters to match the type of the other parameter or converts types of both the parameters to a common type before evaluating the expression.</span></span>  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a><span data-ttu-id="23a26-114">在业务规则中使用逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="23a26-114">To use a logical operator in a business rule</span></span>  
 <span data-ttu-id="23a26-115">利用以下过程可在业务规则中使用逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="23a26-115">Use the following procedure to use a logical operator in a business rule.</span></span>  
  
1.  <span data-ttu-id="23a26-116">在**如果**的业务规则编辑器窗格中右键单击**条件**节点，，然后选择你想要将添加到逻辑表达式的逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="23a26-116">In the **IF** pane of Business Rule Composer, right-click the **Conditions** node, and then select the logical operator that you wish to add to the logical expression.</span></span>  
  
2.  <span data-ttu-id="23a26-117">右键单击该逻辑运算符，然后添加所需的谓词或嵌套逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="23a26-117">Right-click the logical operator, and add the predicates or nested logical operators you want to add.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23a26-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23a26-118">See Also</span></span>  
 [<span data-ttu-id="23a26-119">算术运算符</span><span class="sxs-lookup"><span data-stu-id="23a26-119">Arithmetic Operators</span></span>](../core/arithmetic-operators.md)