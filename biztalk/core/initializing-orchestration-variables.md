---
title: 初始化 Orchestration 变量 |Microsoft 文档
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
ms.openlocfilehash: a90fbc33343e3576d6199a0a97a7a57ca881f720
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256821"
---
# <a name="initializing-orchestration-variables"></a><span data-ttu-id="55ce0-102">初始化业务流程变量</span><span class="sxs-lookup"><span data-stu-id="55ce0-102">Initializing Orchestration Variables</span></span>
<span data-ttu-id="55ce0-103">可以通过在“属性”窗口中设置某一变量的值，初始化该值。</span><span class="sxs-lookup"><span data-stu-id="55ce0-103">You can initialize the value of a variable by setting it in the Properties window.</span></span> <span data-ttu-id="55ce0-104">例如，你可以设置**初始值**为 32 初始化类型 System.Int32 的变量。</span><span class="sxs-lookup"><span data-stu-id="55ce0-104">For example, you can set the **Initial Value** to 32 to initialize the variable of type System.Int32.</span></span> <span data-ttu-id="55ce0-105">在向字符串类型的变量添加初始值时，必须在“属性”窗口中将初始值用引号括起来。</span><span class="sxs-lookup"><span data-stu-id="55ce0-105">When adding an initial value to a variable of type string, you must enclose the initial value in quotation marks in the Properties window.</span></span> <span data-ttu-id="55ce0-106">如果您希望该字符串包含一个引号，则使用反斜杠作为转义符；如果您希望字符串中包括的是反斜杠字符本身，则使用连续的反斜杠。</span><span class="sxs-lookup"><span data-stu-id="55ce0-106">If you want the string to contain a quotation mark, use the backslash as an escape character, and use consecutive backslashes when you want a literal backslash in your string.</span></span> <span data-ttu-id="55ce0-107">如果你未为变量指定一个值，你的变量将分配默认值就会立即创建你的业务流程的实例。</span><span class="sxs-lookup"><span data-stu-id="55ce0-107">If you do not specify a value for your variables, your variables will be assigned default values as soon as an instance of your orchestration is created.</span></span>  
  
 <span data-ttu-id="55ce0-108">如果该变量是某个类的实例，则可以指定一个构造函数来对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="55ce0-108">If the variable is an instance of a class, you can specify a constructor to initialize it.</span></span> <span data-ttu-id="55ce0-109">默认情况下，**使用默认构造函数**属性设置为**True**如果默认构造函数是可用; 因此，默认构造函数将调用它。</span><span class="sxs-lookup"><span data-stu-id="55ce0-109">By default, the **Use Default Constructor** property is set to **True** if a default constructor is available; therefore, the default constructor will be called.</span></span> <span data-ttu-id="55ce0-110">如果你只想要使用默认构造函数，不需要初始化的变量中再次**表达式**形状以避免两次调用的构造函数。</span><span class="sxs-lookup"><span data-stu-id="55ce0-110">If you only intend to use the default constructor, you do not need to initialize the variables again in the **Expression** shape to avoid calling the constructor twice.</span></span> <span data-ttu-id="55ce0-111">如果**使用默认构造函数**属性设置为**False**，将不会调用默认构造函数; 您必须在表达式中调用构造函数或之前您可以使用它进行变量赋值在您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="55ce0-111">If the **Use Default Constructor** property is set to **False**, the default constructor will not be called; you must call a constructor in an expression or make an assignment to the variable before you can use it in your orchestration.</span></span> <span data-ttu-id="55ce0-112">此外，如果构造函数需要输入的参数，则必须设置**使用默认构造函数**到**False** ，然后调用的构造函数从**表达式**调整; 为示例中， `myVariable = myNamespace.myClass (param1, param2)`。</span><span class="sxs-lookup"><span data-stu-id="55ce0-112">Moreover, if the constructor requires input parameters, you must set **Use Default Constructor** to **False** and then call the constructor from an **Expression** shape; for example, `myVariable = myNamespace.myClass (param1, param2)`.</span></span>  
  
 <span data-ttu-id="55ce0-113">只有你需要显式初始化你的变量的情况是当您的业务流程包含多个一个激活收到，尽可能在**作用域**，**并行操作**或**侦听**形状。</span><span class="sxs-lookup"><span data-stu-id="55ce0-113">The only circumstance in which you are required to explicitly initialize your variables is when your orchestration contains more than one activate receive, as is possible in a **Scope**, **Parallel Actions**, or **Listen** shape.</span></span> <span data-ttu-id="55ce0-114">在这种情况下，禁用了自动初始化，并且你必须使用**表达式**形状初始化你的变量。</span><span class="sxs-lookup"><span data-stu-id="55ce0-114">In this case, automatic initialization is disabled, and you must use an **Expression** shape to initialize your variables.</span></span> <span data-ttu-id="55ce0-115">你必须将放**表达式**形状和接收的每次激活后之前在业务流程中访问任何变量。</span><span class="sxs-lookup"><span data-stu-id="55ce0-115">You must place an **Expression** shape after each activation receive, and before any variable is accessed in the orchestration.</span></span>