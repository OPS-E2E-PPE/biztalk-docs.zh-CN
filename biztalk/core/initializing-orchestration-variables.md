---
title: 初始化业务流程变量 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: 770e4e55-1fb9-4b43-854c-63aec5a3c5ba
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0012e4783f3d8b30c38935f8bb22db8809cb3fa0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332012"
---
# <a name="initializing-orchestration-variables"></a><span data-ttu-id="9c09e-102">初始化业务流程变量</span><span class="sxs-lookup"><span data-stu-id="9c09e-102">Initializing Orchestration Variables</span></span>
<span data-ttu-id="9c09e-103">可以通过将其设置属性窗口中初始化变量的值。</span><span class="sxs-lookup"><span data-stu-id="9c09e-103">You can initialize the value of a variable by setting it in the Properties window.</span></span> <span data-ttu-id="9c09e-104">例如，可以设置**初始值**为 32，以便初始化 System.Int32 类型的变量。</span><span class="sxs-lookup"><span data-stu-id="9c09e-104">For example, you can set the **Initial Value** to 32 to initialize the variable of type System.Int32.</span></span> <span data-ttu-id="9c09e-105">时添加到字符串类型的变量的初始值，必须将初始值用引号引起来，在属性窗口中。</span><span class="sxs-lookup"><span data-stu-id="9c09e-105">When adding an initial value to a variable of type string, you must enclose the initial value in quotation marks in the Properties window.</span></span> <span data-ttu-id="9c09e-106">如果你想要包含引号的字符串，使用反斜杠作为转义符，并使用连续反斜杠，当你想在字符串中的文本反斜杠。</span><span class="sxs-lookup"><span data-stu-id="9c09e-106">If you want the string to contain a quotation mark, use the backslash as an escape character, and use consecutive backslashes when you want a literal backslash in your string.</span></span> <span data-ttu-id="9c09e-107">如果不为变量指定一个值，你将将变量分配默认值就立即创建业务流程的实例。</span><span class="sxs-lookup"><span data-stu-id="9c09e-107">If you do not specify a value for your variables, your variables will be assigned default values as soon as an instance of your orchestration is created.</span></span>  
  
 <span data-ttu-id="9c09e-108">如果变量是类的实例，则可以指定对其进行初始化的构造函数。</span><span class="sxs-lookup"><span data-stu-id="9c09e-108">If the variable is an instance of a class, you can specify a constructor to initialize it.</span></span> <span data-ttu-id="9c09e-109">默认情况下**使用默认构造函数**属性设置为**True**如果默认构造函数不可用; 因此，默认构造函数将调用。</span><span class="sxs-lookup"><span data-stu-id="9c09e-109">By default, the **Use Default Constructor** property is set to **True** if a default constructor is available; therefore, the default constructor will be called.</span></span> <span data-ttu-id="9c09e-110">如果只想要使用的默认构造函数，不需要初始化的变量中再次**表达式**形状中，以避免两次调用的构造函数。</span><span class="sxs-lookup"><span data-stu-id="9c09e-110">If you only intend to use the default constructor, you do not need to initialize the variables again in the **Expression** shape to avoid calling the constructor twice.</span></span> <span data-ttu-id="9c09e-111">如果**使用默认构造函数**属性设置为**False**，将不会调用默认构造函数; 您必须在表达式中调用构造函数或向变量赋值之前您可以使用它在您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="9c09e-111">If the **Use Default Constructor** property is set to **False**, the default constructor will not be called; you must call a constructor in an expression or make an assignment to the variable before you can use it in your orchestration.</span></span> <span data-ttu-id="9c09e-112">此外，如果构造函数要求输入的参数，则必须设置**使用默认构造函数**到**False** ，然后调用从构造函数**表达式**形状; 为示例中， `myVariable = myNamespace.myClass (param1, param2)`。</span><span class="sxs-lookup"><span data-stu-id="9c09e-112">Moreover, if the constructor requires input parameters, you must set **Use Default Constructor** to **False** and then call the constructor from an **Expression** shape; for example, `myVariable = myNamespace.myClass (param1, param2)`.</span></span>  
  
 <span data-ttu-id="9c09e-113">您需要显式初始化变量的唯一应用场合是当您的业务流程包含多个激活接收，因为可以在**作用域**，**并行操作**或**侦听**形状。</span><span class="sxs-lookup"><span data-stu-id="9c09e-113">The only circumstance in which you are required to explicitly initialize your variables is when your orchestration contains more than one activate receive, as is possible in a **Scope**, **Parallel Actions**, or **Listen** shape.</span></span> <span data-ttu-id="9c09e-114">在这种情况下，禁用自动初始化，并且必须使用**表达式**形状来初始化变量。</span><span class="sxs-lookup"><span data-stu-id="9c09e-114">In this case, automatic initialization is disabled, and you must use an **Expression** shape to initialize your variables.</span></span> <span data-ttu-id="9c09e-115">必须将放**表达式**形状和每个激活接收后，在业务流程中访问任何变量之前。</span><span class="sxs-lookup"><span data-stu-id="9c09e-115">You must place an **Expression** shape after each activation receive, and before any variable is accessed in the orchestration.</span></span>