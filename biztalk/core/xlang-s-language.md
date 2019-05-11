---
title: Xlang-s 语言 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, properties
ms.assetid: 97b62f17-5a8d-4d87-8563-1f6d941f027f
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b04a28390546e4e22e5f293d772f88371f76696
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394730"
---
# <a name="xlang-s-language"></a><span data-ttu-id="e7c4c-102">Xlang-s 语言</span><span class="sxs-lookup"><span data-stu-id="e7c4c-102">XLANG-s Language</span></span>
<span data-ttu-id="e7c4c-103">XLANG/s 设计为使用 Internet 标准，如 XML、 XSD 和 Web 服务描述语言 (WSDL)，并具有嵌入对处理支持。基于网络的对象和消息。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-103">XLANG/s was designed to use Internet standards such as XML, XSD, and Web Services Description Language (WSDL), and has embedded support for working with .NET-based objects and messages.</span></span> <span data-ttu-id="e7c4c-104">XLANG/s 可被视为的表达式功能的某些消息传递语言C#。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-104">XLANG/s can be viewed as a messaging language with some of the expression capabilities of C#.</span></span> <span data-ttu-id="e7c4c-105">但是，代码不是 XLANG/s 之间可移植和C#。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-105">However, code is not portable between XLANG/s and C#.</span></span>  
  
 <span data-ttu-id="e7c4c-106">XLANG/s 鼓励明显不同进程和实现。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-106">XLANG/s encourages a clear separation between process and implementation.</span></span> <span data-ttu-id="e7c4c-107">例如，XLANG/s，以指定的业务流程或协议，并且在其他.NET 等编程语言中实现应用程序，如数据库访问权限的本地方面C#或 Visual Basic.NET。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-107">For example, the business process or protocol is specified in XLANG/s, and the local aspects of the application, such as database access, are implemented in other .NET programming languages such as C# or Visual Basic.NET.</span></span>  
  
 <span data-ttu-id="e7c4c-108">XLANG/s 分配和表达式语法以它为模型C#，并应引用C#的确切语法规范。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-108">XLANG/s assignment and expression syntax is modeled after C#, and you should reference the C# specification for exact syntax.</span></span> <span data-ttu-id="e7c4c-109">XLANG/s 定义一组丰富的用于定义业务流程的高级构造。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-109">XLANG/s defines a rich set of high-level constructs that are used to define business processes.</span></span> <span data-ttu-id="e7c4c-110">XLANG/s 为低级别的数据类型，如字符串和整数提供支持，但还定义高级数据类型： 消息、 端口、 相关性和服务的链接。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-110">While XLANG/s provides support for low-level data types like string and integer, high-level data types are also defined: messages, ports, correlations, and service links.</span></span> <span data-ttu-id="e7c4c-111">这些数据类型用于严格地定义与业务流程相关的语义和补充过程控制语句，例如**虽然**或**作用域**。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-111">These data types are used to rigorously define the semantics associated with a business process, and are complemented by process control statements such as **while** or **scope**.</span></span>  
  
 <span data-ttu-id="e7c4c-112">XLANG/s 语句通常分为两个类别之一： 简单语句，对其自身，例如**接收**或**发送**，并包含或组是简单的语句的复杂语句或其他复杂语句，如**作用域**，**并行**，并**侦听**。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-112">XLANG/s statements generally fall into one of two categories: simple statements that act on their own, such as **receive** or **send**, and complex statements that contain or group either simple statements or other complex statements, such as **scope**, **parallel**, and **listen**.</span></span> <span data-ttu-id="e7c4c-113">XLANG/s 中体现的语义是反射的业务流程执行语言由 Microsoft、 IBM 和 BEA 发布定义的业务过程语义的 Web 服务 (BPEL4WS) 规范中定义的那些。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-113">The semantics embodied in XLANG/s are a reflection of those defined in the Business Process Execution Language for Web Services (BPEL4WS) specification published by Microsoft, IBM, and BEA for the definition of business process semantics.</span></span>  
  
 <span data-ttu-id="e7c4c-114">了解 XLANG/s 的主要构造是可选的因为它们在 BizTalk 业务流程设计器中绘制业务流程关系图生成。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-114">Understanding the main constructs of XLANG/s is optional because they are produced as a result of drawing orchestration diagrams in BizTalk Orchestration Designer.</span></span> <span data-ttu-id="e7c4c-115">业务流程设计器是用于以可视方式设计业务流程的丰富图形工具。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-115">Orchestration Designer is a rich graphical tool for visually designing business processes.</span></span> <span data-ttu-id="e7c4c-116">它将生成具有.odx 扩展名，并且包含在其标头中的其他可视化信息和在其主体的自定义特性信息的 XLANG/s 文件。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-116">It generates XLANG/s files that have an .odx extension and contain additional visual information in their headers and custom attribute information in their bodies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7c4c-117">XLANG/s 语言是专有，并不完全记录。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-117">The XLANG/s language is proprietary and is not fully documented.</span></span> <span data-ttu-id="e7c4c-118">本部分中显示的语言，可能需要注意的开发您的业务流程的某些部分。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-118">This section exposes certain parts of the language that you might need to be aware of as you develop your orchestrations.</span></span> <span data-ttu-id="e7c4c-119">不支持的.odx 文件直接修改。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-119">Direct modification of the .odx files is not supported.</span></span>  
  
## <a name="xlangs-programs"></a><span data-ttu-id="e7c4c-120">XLANG/s 程序</span><span class="sxs-lookup"><span data-stu-id="e7c4c-120">XLANG/s Programs</span></span>  
 <span data-ttu-id="e7c4c-121">最简单的 XLANG/s 程序需要定义消息类型，它可使业务流程启动要使用的某些数据。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-121">The simplest XLANG/s program requires that a message type be defined, which gives the orchestration some data to start to work with.</span></span> <span data-ttu-id="e7c4c-122">业务流程通过端口接收的消息，然后终止。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-122">The orchestration receives the message over a port and then terminates.</span></span> <span data-ttu-id="e7c4c-123">以下代码是一个示例：</span><span class="sxs-lookup"><span data-stu-id="e7c4c-123">The following code is an example:</span></span>  
  
```  
module HelloWorldApp  
{  
     private porttype ptPOReceive  
     {  
      oneway opPOReceive  
      {  
       HelloWorldApp.PurchaseOrder  
      }  
     }  
     private porttype ptPOSend  
     {  
      oneway opPOSend  
      {  
       HelloWorldApp.PurchaseOrder  
      }  
     }  
     private service  HelloWorld  
     {  
      port implements HelloWorldApp.ptPOReceive poPOReceive;  
      port uses HelloWorldApp.ptPOSend poPOSend;  
      message HelloWorldApp.PurchaseOrder msgPO;  
      body ()  
      {  
       activate receive (poPOReceive.opPOReceive, msgPO);  
       send (poPOSend.opPOSend, msgPO);  
       }  
     }  
}  
```  
  
 <span data-ttu-id="e7c4c-124">在前面的 XLANG/s 程序中，`module`关键字定义 XLANG/s 程序的编译期间的单位。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-124">In the preceding XLANG/s program, the `module` keyword defines the unit of compilations for an XLANG/s program.</span></span> <span data-ttu-id="e7c4c-125">在程序中使用的所有类型，如**porttype**， **correlationsettype**， **servicelinktype**，并**messagetype**— 的作用域在此级别。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-125">All types used in the program—such as **porttype**, **correlationsettype**, **servicelinktype**, and **messagetype**—are scoped at this level.</span></span>  
  
 <span data-ttu-id="e7c4c-126">端口是一种构造，XLANG/s 可发送或接收消息的并且端口具有已定义的类型称为**porttype**。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-126">A port is a construct that XLANG/s can send or receive messages to or from, and the port has a defined type called **porttype**.</span></span> <span data-ttu-id="e7c4c-127">**Porttype**构造定义可用的端口的操作的集合。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-127">The **porttype** construct defines a collection of operations that can be used on the port.</span></span> <span data-ttu-id="e7c4c-128">这些操作通过端口定义的单个有效的消息交换。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-128">These operations define a single valid message exchange over the port.</span></span> <span data-ttu-id="e7c4c-129">在定义**porttype**， **messagetype**， **servicelinktype**，或者**correlationsettype**构造，XLANG/s 的作者程序实质上创建复杂数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-129">In defining **porttype**, **messagetype**, **servicelinktype**, or **correlationsettype** constructs, the author of an XLANG/s program is essentially creating complex data type definitions.</span></span> <span data-ttu-id="e7c4c-130">这些定义拥有相同的好处，如在其他语言中的复杂数据类型执行操作：这些抽象概念体现在更高层次的数据类型，它们用于方便的数据类型重复使用。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-130">These definitions have the same advantages as complex data types do in other languages: They abstract the notions embodied in the data type to a higher level, and they allow for easy reuse of the data type.</span></span>  
  
 <span data-ttu-id="e7c4c-131">**PtPOReceive**端口中前面 HelloWorldApp 模块定义使用一个单向接收端口操作**opPOReceive**。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-131">The **ptPOReceive** port in the preceding HelloWorldApp module is defined with a one-way receive port operation, **opPOReceive**.</span></span> <span data-ttu-id="e7c4c-132">服务 HelloWorld 块定义此过程，它可能会使用，包括端口和消息变量的任何变量的实际实现。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-132">The service HelloWorld block defines the actual implementation of the process and any variables it may use, including port and message variables.</span></span> <span data-ttu-id="e7c4c-133">在此块中的代码的前三行定义端口变量**poPOReceive**并**poPOSend**和消息**msgPO**分别。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-133">The first three lines of code within this block define the port variables **poPOReceive** and **poPOSend** and the message **msgPO** respectively.</span></span> <span data-ttu-id="e7c4c-134">正文包含描述该服务并执行行为的参数的代码。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-134">The body contains the code describing parameters to the service and the execution behavior.</span></span> <span data-ttu-id="e7c4c-135">所有变量，除非使用嵌套的作用域块，定义到此级别中的作用都域。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-135">All variables, unless defined with a nested scope block, are scoped to this level.</span></span> <span data-ttu-id="e7c4c-136">Receive 语句，这是激活接收，接收**msgPO**从消息**poPOReceive.opPOReceive**端口，并创建业务流程的新实例。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-136">The receive statement, which is an activate receive, receives the **msgPO** message from the **poPOReceive.opPOReceive** port and creates a new instance of the orchestration.</span></span> <span data-ttu-id="e7c4c-137">接收消息后，send 语句将定向到发送端口的消息。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-137">After the message is received, the send statement directs the message to a send port.</span></span> <span data-ttu-id="e7c4c-138">在前面的代码中，在两个端口声明中**poPOReceive**使用 implements 修饰符，而**poPOSend**使用 uses 修饰符。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-138">In the two port declarations in the preceding code, **poPOReceive** uses the implements modifier, whereas **poPOSend** uses the uses modifier.</span></span> <span data-ttu-id="e7c4c-139">Implements 修饰符指示运行时，它将通过该端口接收消息。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-139">The implements modifier tells the runtime it will be receiving a message over that port.</span></span> <span data-ttu-id="e7c4c-140">使用修饰符指示运行时，它将发送一条消息通过该端口。</span><span class="sxs-lookup"><span data-stu-id="e7c4c-140">The uses modifier tells the runtime that it will be sending a message over that port.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e7c4c-141">本节内容</span><span class="sxs-lookup"><span data-stu-id="e7c4c-141">In This Section</span></span>  
  
-   [<span data-ttu-id="e7c4c-142">XLANG-s 数据类型</span><span class="sxs-lookup"><span data-stu-id="e7c4c-142">XLANG-s Data Types</span></span>](../core/xlang-s-data-types.md)  
  
-   [<span data-ttu-id="e7c4c-143">XLANG-s 语句</span><span class="sxs-lookup"><span data-stu-id="e7c4c-143">XLANG-s Statements</span></span>](../core/xlang-s-statements.md)  
  
-   [<span data-ttu-id="e7c4c-144">XLANG-s 变量和运算符</span><span class="sxs-lookup"><span data-stu-id="e7c4c-144">XLANG-s Variables and Operators</span></span>](../core/xlang-s-variables-and-operators.md)  
  
-   [<span data-ttu-id="e7c4c-145">XLANG-s 表达式</span><span class="sxs-lookup"><span data-stu-id="e7c4c-145">XLANG-s Expressions</span></span>](../core/xlang-s-expressions.md)  
  
-   [<span data-ttu-id="e7c4c-146">XLANG-s 保留字</span><span class="sxs-lookup"><span data-stu-id="e7c4c-146">XLANG-s Reserved Words</span></span>](../core/xlang-s-reserved-words.md)  
  
-   [<span data-ttu-id="e7c4c-147">XLANG-s 到 BPEL4WS 的类型转换</span><span class="sxs-lookup"><span data-stu-id="e7c4c-147">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)  
  
## <a name="see-also"></a><span data-ttu-id="e7c4c-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7c4c-148">See Also</span></span>  
 [<span data-ttu-id="e7c4c-149">关于 BizTalk 业务流程引擎</span><span class="sxs-lookup"><span data-stu-id="e7c4c-149">About the BizTalk Orchestration Engine</span></span>](../core/about-the-biztalk-orchestration-engine.md)