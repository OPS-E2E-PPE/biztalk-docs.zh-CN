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
# <a name="debugging-orchestrations-by-using-custom-code"></a>使用自定义代码进行调试业务流程
如果您的业务流程要小心，在测试环境中或要创建原型并且想要修改消息字段和业务流程变量的值，你可以将输出写入到[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]控制台中使用下面的代码中**表达式**形状：  
  
```  
System.Diagnostics.Debug.WriteLine(iResult);  
```  
  
 你需要将该**表达式**立即后将执行该操作，因此你可以输出调试的结果的形状的形状。  
  
 或者，可以通过用包含方法的类创建调试 DLL 来编写简单的自定义调试器，在业务流程中定义格式并在调试 DLL 中引用该格式的情况下，该调试器会将输入理解为消息。 有关作为参数传递消息的详细信息，请参阅[如何对创建对象和调用对象方法的使用表达式](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md)。  
  
 此方法可以调出包括组合框或其他控件的调试对话框，允许用户修改值、取回编辑后的消息，并将其以返回值的形式传回。  
  
 将布尔变量设置为指示您的业务流程是否处于调试模式，然后从该处你想要能够修改值业务流程中具有的点的任何位置，你可以添加**确定**具有一个实时的形状仅在你调试模式变量设置为 True，或你想要检查的特定条件发生时运行的分支。 调用你的方法从**表达式**的实时分支中的形状**确定**。 当你不再需要进行调试时，你将你的调试模式下变量设置为 False，或删除**确定**形状一起删除并重新编译。  
  
## <a name="to-debug-a-net-component-called-by-an-orchestration"></a>调试业务流程调用的 .NET 组件  
 以下步骤演示如何调试业务流程调用的 .NET 组件：  
  
1.  打开组件的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目。  
  
2.  在业务流程所调用的组件方法上设置断点。  
  
3.  单击**调试**菜单，然后选择**附加到进程...** 若要显示**附加到进程**对话框。  
  
4.  单击**选择...** 下一步按钮**将附加到：**文本框中，用于显示**选择代码类型**对话框。  
  
5.  单击此项可选择该选项以**调试以下代码类型：**和选择**托管**，然后单击**确定**按钮。  
  
6.  单击以选择**BTSNTSvc.exe**进程**可用进程**，然后单击**附加**按钮。  
  
7.  通过接收端口将消息发送至业务流程。  
  
8.  .NET 组件应该在断点停止。  
  
9. 你可以执行使用像通常那样调试[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
    > [!NOTE]
    >  为获得最佳结果，应该在全局程序集缓存 (GAC) 中注册 .NET 组件。  
  
## <a name="see-also"></a>另请参阅  
 [业务流程调试器用户界面](../core/orchestration-debugger-user-interface.md)   
 [调试业务流程](../core/debugging-orchestrations.md)