---
title: 在业务流程中使用表达式 |Microsoft Docs
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
ms.openlocfilehash: 3f8c528254dc5acc853e7c1f3fb4fe412f6e3eff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247375"
---
# <a name="using-expressions-in-orchestrations"></a><span data-ttu-id="2ab88-102">在业务流程中使用表达式</span><span class="sxs-lookup"><span data-stu-id="2ab88-102">Using Expressions in Orchestrations</span></span>
<span data-ttu-id="2ab88-103">BizTalk 表达式编辑器可用于输入要添加逻辑来处理和测试你的业务流程变量和消息的值的 XLANG/s 表达式。</span><span class="sxs-lookup"><span data-stu-id="2ab88-103">You can use BizTalk Expression Editor to enter XLANG/s expressions to add logic to manipulate and test the values of your orchestration variables and messages.</span></span> <span data-ttu-id="2ab88-104">但是，它不是使用它来执行高级业务流程逻辑，最好是在业务流程设计图本身中可见的好办法。</span><span class="sxs-lookup"><span data-stu-id="2ab88-104">However, it is not a good practice to use it to perform high-level orchestration logic, which preferably would be visible in the orchestration drawing itself.</span></span> <span data-ttu-id="2ab88-105">为业务过程透明度和重新配置的轻松，我们建议使用简单的模块化表达式。</span><span class="sxs-lookup"><span data-stu-id="2ab88-105">For business process transparency and easy of reconfiguration, we recommend that you use simple and modular expressions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ab88-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="2ab88-106">In This Section</span></span>  
 [<span data-ttu-id="2ab88-107">对表达式的要求和限制</span><span class="sxs-lookup"><span data-stu-id="2ab88-107">Requirements and Limitations for Expressions</span></span>](../core/requirements-and-limitations-for-expressions.md)  
  
 [<span data-ttu-id="2ab88-108">使用表达式的形状</span><span class="sxs-lookup"><span data-stu-id="2ab88-108">Shapes that Take Expressions</span></span>](../core/shapes-that-take-expressions.md)  
  
 [<span data-ttu-id="2ab88-109">如何创建表达式</span><span class="sxs-lookup"><span data-stu-id="2ab88-109">How to Create Expressions</span></span>](../core/how-to-create-expressions.md)  
  
 [<span data-ttu-id="2ab88-110">在表达式中使用运算符</span><span class="sxs-lookup"><span data-stu-id="2ab88-110">Using Operators in Expressions</span></span>](../core/using-operators-in-expressions.md)  
  
 [<span data-ttu-id="2ab88-111">如何使用表达式来执行消息分配</span><span class="sxs-lookup"><span data-stu-id="2ab88-111">How to Use Expressions to Perform Message Assignments</span></span>](../core/how-to-use-expressions-to-perform-message-assignments.md)  
  
 [<span data-ttu-id="2ab88-112">如何使用表达式来动态转换消息</span><span class="sxs-lookup"><span data-stu-id="2ab88-112">How to Use Expressions to Dynamic Transform Messages</span></span>](../core/how-to-use-expressions-to-dynamic-transform-messages.md)  
  
 [<span data-ttu-id="2ab88-113">如何使用表达式执行管道</span><span class="sxs-lookup"><span data-stu-id="2ab88-113">How to Use Expressions to Execute Pipelines</span></span>](../core/how-to-use-expressions-to-execute-pipelines.md)  
  
 [<span data-ttu-id="2ab88-114">如何使用表达式创建对象和调用对象方法</span><span class="sxs-lookup"><span data-stu-id="2ab88-114">How to Use Expressions to Create Objects and Call Object Methods</span></span>](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md)  
  
 [<span data-ttu-id="2ab88-115">如何使用表达式向动态端口赋值</span><span class="sxs-lookup"><span data-stu-id="2ab88-115">How to Use Expressions to Assign Values to Dynamic Ports</span></span>](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)  
  
## <a name="see-also"></a><span data-ttu-id="2ab88-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ab88-116">See Also</span></span>  
 <span data-ttu-id="2ab88-117">[XLANG-s 语言](../core/xlang-s-language.md) </span><span class="sxs-lookup"><span data-stu-id="2ab88-117">[XLANG-s Language](../core/xlang-s-language.md) </span></span>  
 <span data-ttu-id="2ab88-118">[业务流程中使用的消息](../core/using-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="2ab88-118">[Using Messages in Orchestrations](../core/using-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="2ab88-119">在业务流程中使用变量</span><span class="sxs-lookup"><span data-stu-id="2ab88-119">Using Variables in Orchestrations</span></span>](../core/using-variables-in-orchestrations.md)