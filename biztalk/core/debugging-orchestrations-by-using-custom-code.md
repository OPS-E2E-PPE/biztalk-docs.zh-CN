---
title: 通过使用自定义代码调试业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, debugging
- building, debugging
ms.assetid: 94e569fa-8dea-4027-abb5-37b4a8015621
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8981fc1d4fc10a7a43c02d6cd815a24dd31912ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352519"
---
# <a name="debugging-orchestrations-by-using-custom-code"></a><span data-ttu-id="e6bb1-102">通过使用自定义代码调试业务流程</span><span class="sxs-lookup"><span data-stu-id="e6bb1-102">Debugging Orchestrations by using Custom Code</span></span>
<span data-ttu-id="e6bb1-103">如果您的业务流程要在测试环境中执行，或者你要创建一个原型并想要修改消息字段和业务流程变量的值，可以将输出写入[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]中使用下面的代码的控制台**表达式**形状：</span><span class="sxs-lookup"><span data-stu-id="e6bb1-103">If your orchestration is going to be exercised in a test environment or you are creating a prototype and want to modify the values of message fields and orchestration variables, you can write the output to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] console by using the following code in an **Expression** shape:</span></span>  
  
```  
System.Diagnostics.Debug.WriteLine(iResult);  
```  
  
 <span data-ttu-id="e6bb1-104">需要将这**表达式**后立即执行该操作，因此可以输出调试的结果的形状的形状。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-104">You need to place this **Expression** shape immediately after the shape that performs the operation so that you can output the result for debugging.</span></span>  
  
 <span data-ttu-id="e6bb1-105">或者，您可以编写一个简单的类创建调试 DLL 的自定义调试器包括一种方法可将作为一种格式的消息在业务流程中定义和在调试 DLL 中引用的输入。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-105">Alternatively, you can write a simple custom debugger by creating a debugging DLL with a class that includes a method which takes as input a message with a format defined in your orchestration and referenced in the debug DLL.</span></span> <span data-ttu-id="e6bb1-106">作为参数传递消息的详细信息，请参阅[如何使用表达式来创建对象和调用对象方法](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-106">For more information about passing a message as a parameter, see [How to Use Expressions to Create Objects and Call Object Methods](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md).</span></span>  
  
 <span data-ttu-id="e6bb1-107">此方法可以打开一个调试对话框，其中包括一个组合框或其他控件，以允许用户修改值，编辑将该消息放回在一起，并将其返回值作为签。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-107">This method can bring up a debug dialog that includes a combo box or other control to allow user modification of values, puts the edited message back together, and passes it back out as the return value.</span></span>  
  
 <span data-ttu-id="e6bb1-108">设置一个布尔变量，以指示您的业务流程是否处于调试模式，然后在其中你想要能够修改值业务流程中有一个点的任何位置，您可以添加**判定**具有一个实时形状：只有在调试模式变量设置为 True，或你想要检查特定条件时运行的分支。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-108">Set up a Boolean variable to indicate whether or not your orchestration is in debug mode, then wherever you have a point in your orchestration at which you would like to be able to modify values, you can add a **Decide** shape with one live branch that runs only when your debug mode variable is set to True, or when a particular condition arises that you want to examine.</span></span> <span data-ttu-id="e6bb1-109">调用您的方法从**表达式**形状中的活动分支**判定**。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-109">You call your method from an **Expression** shape in the live branch of the **Decide**.</span></span> <span data-ttu-id="e6bb1-110">当不再需要进行调试时，你将调试模式变量设置为 False，或删除**判定**形状完全并重新编译。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-110">When you no longer need to debug, you set your debug mode variable to False, or remove the **Decide** shape(s) altogether and recompile.</span></span>  
  
## <a name="to-debug-a-net-component-called-by-an-orchestration"></a><span data-ttu-id="e6bb1-111">若要调试业务流程调用的.NET 组件</span><span class="sxs-lookup"><span data-stu-id="e6bb1-111">To Debug a .NET component called by an Orchestration</span></span>  
 <span data-ttu-id="e6bb1-112">以下步骤演示如何调试业务流程调用的.NET 组件：</span><span class="sxs-lookup"><span data-stu-id="e6bb1-112">The following steps demonstrate how to debug a .NET component called by an Orchestration:</span></span>  
  
1. <span data-ttu-id="e6bb1-113">打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]为组件的项目。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-113">Open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for your component.</span></span>  
  
2. <span data-ttu-id="e6bb1-114">在业务流程调用的方法在组件中设置断点。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-114">Set a breakpoint in your component on the method that is called by the orchestration.</span></span>  
  
3. <span data-ttu-id="e6bb1-115">单击**调试**菜单，然后选择**附加到进程...**</span><span class="sxs-lookup"><span data-stu-id="e6bb1-115">Click the **Debug** menu and select **Attach to Process…**</span></span> <span data-ttu-id="e6bb1-116">若要显示**附加到进程**对话框。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-116">to display the **Attach to Process** dialog.</span></span>  
  
4. <span data-ttu-id="e6bb1-117">单击**选择...**</span><span class="sxs-lookup"><span data-stu-id="e6bb1-117">Click the **Select…**</span></span> <span data-ttu-id="e6bb1-118">按钮旁边**将附加到：** 以显示**选择代码类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-118">button next to the **Attach to:** text box to display the **Select Code Type** dialog.</span></span>  
  
5. <span data-ttu-id="e6bb1-119">单击此项可选择的选项**调试这些代码类型：** ，然后选择**托管**，然后单击**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-119">Click to select the option to **Debug these code types:** and select **Managed** and then click the **OK** button.</span></span>  
  
6. <span data-ttu-id="e6bb1-120">单击此项可选择**BTSNTSvc.exe**进程**可用进程**，然后单击**附加**按钮。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-120">Click to select the **BTSNTSvc.exe** process from **Available Processes** and then click the **Attach** button.</span></span>  
  
7. <span data-ttu-id="e6bb1-121">将消息发送到您的业务流程通过接收端口。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-121">Send a message to your orchestration through a receive port.</span></span>  
  
8. <span data-ttu-id="e6bb1-122">.NET 组件应该在断点处停止。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-122">The .NET component should be stopped in the breakpoint.</span></span>  
  
9. <span data-ttu-id="e6bb1-123">你可以使用像往常一样调试[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-123">You can perform debugging as usual with [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e6bb1-124">为获得最佳结果，.NET 组件应注册在全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="e6bb1-124">For best results, the .NET component should be registered in the Global Assembly Cache (GAC).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6bb1-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6bb1-125">See Also</span></span>  
 <span data-ttu-id="e6bb1-126">[业务流程调试器用户界面](../core/orchestration-debugger-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="e6bb1-126">[Orchestration Debugger User Interface](../core/orchestration-debugger-user-interface.md) </span></span>  
 [<span data-ttu-id="e6bb1-127">调试业务流程</span><span class="sxs-lookup"><span data-stu-id="e6bb1-127">Debugging Orchestrations</span></span>](../core/debugging-orchestrations.md)