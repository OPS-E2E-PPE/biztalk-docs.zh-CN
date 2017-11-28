---
title: "使用自定义代码进行调试业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, debugging
- building, debugging
ms.assetid: 94e569fa-8dea-4027-abb5-37b4a8015621
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47f69fa635a90db90c461f75c300334ccc499b94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="debugging-orchestrations-by-using-custom-code"></a><span data-ttu-id="61401-102">使用自定义代码进行调试业务流程</span><span class="sxs-lookup"><span data-stu-id="61401-102">Debugging Orchestrations by using Custom Code</span></span>
<span data-ttu-id="61401-103">如果您的业务流程要小心，在测试环境中或要创建原型并且想要修改消息字段和业务流程变量的值，你可以将输出写入到[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]控制台中使用下面的代码中**表达式**形状：</span><span class="sxs-lookup"><span data-stu-id="61401-103">If your orchestration is going to be exercised in a test environment or you are creating a prototype and want to modify the values of message fields and orchestration variables, you can write the output to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] console by using the following code in an **Expression** shape:</span></span>  
  
```  
System.Diagnostics.Debug.WriteLine(iResult);  
```  
  
 <span data-ttu-id="61401-104">你需要将该**表达式**立即后将执行该操作，因此你可以输出调试的结果的形状的形状。</span><span class="sxs-lookup"><span data-stu-id="61401-104">You need to place this **Expression** shape immediately after the shape that performs the operation so that you can output the result for debugging.</span></span>  
  
 <span data-ttu-id="61401-105">或者，可以通过用包含方法的类创建调试 DLL 来编写简单的自定义调试器，在业务流程中定义格式并在调试 DLL 中引用该格式的情况下，该调试器会将输入理解为消息。</span><span class="sxs-lookup"><span data-stu-id="61401-105">Alternatively, you can write a simple custom debugger by creating a debugging DLL with a class that includes a method which takes as input a message with a format defined in your orchestration and referenced in the debug DLL.</span></span> <span data-ttu-id="61401-106">有关作为参数传递消息的详细信息，请参阅[如何对创建对象和调用对象方法的使用表达式](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="61401-106">For more information about passing a message as a parameter, see [How to Use Expressions to Create Objects and Call Object Methods](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md).</span></span>  
  
 <span data-ttu-id="61401-107">此方法可以调出包括组合框或其他控件的调试对话框，允许用户修改值、取回编辑后的消息，并将其以返回值的形式传回。</span><span class="sxs-lookup"><span data-stu-id="61401-107">This method can bring up a debug dialog that includes a combo box or other control to allow user modification of values, puts the edited message back together, and passes it back out as the return value.</span></span>  
  
 <span data-ttu-id="61401-108">将布尔变量设置为指示您的业务流程是否处于调试模式，然后从该处你想要能够修改值业务流程中具有的点的任何位置，你可以添加**确定**具有一个实时的形状仅在你调试模式变量设置为 True，或你想要检查的特定条件发生时运行的分支。</span><span class="sxs-lookup"><span data-stu-id="61401-108">Set up a Boolean variable to indicate whether or not your orchestration is in debug mode, then wherever you have a point in your orchestration at which you would like to be able to modify values, you can add a **Decide** shape with one live branch that runs only when your debug mode variable is set to True, or when a particular condition arises that you want to examine.</span></span> <span data-ttu-id="61401-109">调用你的方法从**表达式**的实时分支中的形状**确定**。</span><span class="sxs-lookup"><span data-stu-id="61401-109">You call your method from an **Expression** shape in the live branch of the **Decide**.</span></span> <span data-ttu-id="61401-110">当你不再需要进行调试时，你将你的调试模式下变量设置为 False，或删除**确定**形状一起删除并重新编译。</span><span class="sxs-lookup"><span data-stu-id="61401-110">When you no longer need to debug, you set your debug mode variable to False, or remove the **Decide** shape(s) altogether and recompile.</span></span>  
  
## <a name="to-debug-a-net-component-called-by-an-orchestration"></a><span data-ttu-id="61401-111">调试业务流程调用的 .NET 组件</span><span class="sxs-lookup"><span data-stu-id="61401-111">To Debug a .NET component called by an Orchestration</span></span>  
 <span data-ttu-id="61401-112">以下步骤演示如何调试业务流程调用的 .NET 组件：</span><span class="sxs-lookup"><span data-stu-id="61401-112">The following steps demonstrate how to debug a .NET component called by an Orchestration:</span></span>  
  
1.  <span data-ttu-id="61401-113">打开组件的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目。</span><span class="sxs-lookup"><span data-stu-id="61401-113">Open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for your component.</span></span>  
  
2.  <span data-ttu-id="61401-114">在业务流程所调用的组件方法上设置断点。</span><span class="sxs-lookup"><span data-stu-id="61401-114">Set a breakpoint in your component on the method that is called by the orchestration.</span></span>  
  
3.  <span data-ttu-id="61401-115">单击**调试**菜单，然后选择**附加到进程...**</span><span class="sxs-lookup"><span data-stu-id="61401-115">Click the **Debug** menu and select **Attach to Process…**</span></span> <span data-ttu-id="61401-116">若要显示**附加到进程**对话框。</span><span class="sxs-lookup"><span data-stu-id="61401-116">to display the **Attach to Process** dialog.</span></span>  
  
4.  <span data-ttu-id="61401-117">单击**选择...**</span><span class="sxs-lookup"><span data-stu-id="61401-117">Click the **Select…**</span></span> <span data-ttu-id="61401-118">下一步按钮**将附加到：**文本框中，用于显示**选择代码类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="61401-118">button next to the **Attach to:** text box to display the **Select Code Type** dialog.</span></span>  
  
5.  <span data-ttu-id="61401-119">单击此项可选择该选项以**调试以下代码类型：**和选择**托管**，然后单击**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="61401-119">Click to select the option to **Debug these code types:** and select **Managed** and then click the **OK** button.</span></span>  
  
6.  <span data-ttu-id="61401-120">单击以选择**BTSNTSvc.exe**进程**可用进程**，然后单击**附加**按钮。</span><span class="sxs-lookup"><span data-stu-id="61401-120">Click to select the **BTSNTSvc.exe** process from **Available Processes** and then click the **Attach** button.</span></span>  
  
7.  <span data-ttu-id="61401-121">通过接收端口将消息发送至业务流程。</span><span class="sxs-lookup"><span data-stu-id="61401-121">Send a message to your orchestration through a receive port.</span></span>  
  
8.  <span data-ttu-id="61401-122">.NET 组件应该在断点停止。</span><span class="sxs-lookup"><span data-stu-id="61401-122">The .NET component should be stopped in the breakpoint.</span></span>  
  
9. <span data-ttu-id="61401-123">你可以执行使用像通常那样调试[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="61401-123">You can perform debugging as usual with [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61401-124">为获得最佳结果，应该在全局程序集缓存 (GAC) 中注册 .NET 组件。</span><span class="sxs-lookup"><span data-stu-id="61401-124">For best results, the .NET component should be registered in the Global Assembly Cache (GAC).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61401-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61401-125">See Also</span></span>  
 <span data-ttu-id="61401-126">[业务流程调试器用户界面](../core/orchestration-debugger-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="61401-126">[Orchestration Debugger User Interface](../core/orchestration-debugger-user-interface.md) </span></span>  
 [<span data-ttu-id="61401-127">调试业务流程</span><span class="sxs-lookup"><span data-stu-id="61401-127">Debugging Orchestrations</span></span>](../core/debugging-orchestrations.md)