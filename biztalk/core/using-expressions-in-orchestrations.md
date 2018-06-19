---
title: 在业务流程中使用表达式 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1947cd39-6ef2-4b2d-afeb-a0132b19db97
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 880e1ee08a232aca3a04763c5d5c1797fd238fbe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287133"
---
# <a name="using-expressions-in-orchestrations"></a><span data-ttu-id="9624f-102">在业务流程中使用表达式</span><span class="sxs-lookup"><span data-stu-id="9624f-102">Using Expressions in Orchestrations</span></span>
<span data-ttu-id="9624f-103">BizTalk 表达式编辑器可用于输入 XLANG/s 表达式，以添加逻辑来操作和测试你的业务流程变量和消息的值。</span><span class="sxs-lookup"><span data-stu-id="9624f-103">You can use BizTalk Expression Editor to enter XLANG/s expressions to add logic to manipulate and test the values of your orchestration variables and messages.</span></span> <span data-ttu-id="9624f-104">但是，它不是作为最佳做法，使用它来执行高级业务流程逻辑，最好是将是在绘制自身的业务流程中可见。</span><span class="sxs-lookup"><span data-stu-id="9624f-104">However, it is not a good practice to use it to perform high-level orchestration logic, which preferably would be visible in the orchestration drawing itself.</span></span> <span data-ttu-id="9624f-105">对业务进程透明度便捷的重新配置，我们建议你使用简单和模块化表达式。</span><span class="sxs-lookup"><span data-stu-id="9624f-105">For business process transparency and easy of reconfiguration, we recommend that you use simple and modular expressions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9624f-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="9624f-106">In This Section</span></span>  
 [<span data-ttu-id="9624f-107">表达式的要求和限制</span><span class="sxs-lookup"><span data-stu-id="9624f-107">Requirements and Limitations for Expressions</span></span>](../core/requirements-and-limitations-for-expressions.md)  
  
 [<span data-ttu-id="9624f-108">采用表达式的形状</span><span class="sxs-lookup"><span data-stu-id="9624f-108">Shapes that Take Expressions</span></span>](../core/shapes-that-take-expressions.md)  
  
 [<span data-ttu-id="9624f-109">如何创建表达式</span><span class="sxs-lookup"><span data-stu-id="9624f-109">How to Create Expressions</span></span>](../core/how-to-create-expressions.md)  
  
 [<span data-ttu-id="9624f-110">在表达式中使用运算符</span><span class="sxs-lookup"><span data-stu-id="9624f-110">Using Operators in Expressions</span></span>](../core/using-operators-in-expressions.md)  
  
 [<span data-ttu-id="9624f-111">如何使用表达式来执行消息分配</span><span class="sxs-lookup"><span data-stu-id="9624f-111">How to Use Expressions to Perform Message Assignments</span></span>](../core/how-to-use-expressions-to-perform-message-assignments.md)  
  
 [<span data-ttu-id="9624f-112">如何使用动态转换消息的表达式</span><span class="sxs-lookup"><span data-stu-id="9624f-112">How to Use Expressions to Dynamic Transform Messages</span></span>](../core/how-to-use-expressions-to-dynamic-transform-messages.md)  
  
 [<span data-ttu-id="9624f-113">如何使用表达式来执行管道</span><span class="sxs-lookup"><span data-stu-id="9624f-113">How to Use Expressions to Execute Pipelines</span></span>](../core/how-to-use-expressions-to-execute-pipelines.md)  
  
 [<span data-ttu-id="9624f-114">如何使用表达式来创建对象并调用对象方法</span><span class="sxs-lookup"><span data-stu-id="9624f-114">How to Use Expressions to Create Objects and Call Object Methods</span></span>](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md)  
  
 [<span data-ttu-id="9624f-115">如何使用表达式将值分配到动态端口</span><span class="sxs-lookup"><span data-stu-id="9624f-115">How to Use Expressions to Assign Values to Dynamic Ports</span></span>](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)  
  
## <a name="see-also"></a><span data-ttu-id="9624f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9624f-116">See Also</span></span>  
 <span data-ttu-id="9624f-117">[XLANG-s 语言](../core/xlang-s-language.md) </span><span class="sxs-lookup"><span data-stu-id="9624f-117">[XLANG-s Language](../core/xlang-s-language.md) </span></span>  
 <span data-ttu-id="9624f-118">[在业务流程中使用消息](../core/using-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="9624f-118">[Using Messages in Orchestrations](../core/using-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="9624f-119">在业务流程中使用变量</span><span class="sxs-lookup"><span data-stu-id="9624f-119">Using Variables in Orchestrations</span></span>](../core/using-variables-in-orchestrations.md)