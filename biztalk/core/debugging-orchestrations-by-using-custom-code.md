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
# <a name="debugging-orchestrations-by-using-custom-code"></a>通过使用自定义代码调试业务流程
如果您的业务流程要在测试环境中执行，或者你要创建一个原型并想要修改消息字段和业务流程变量的值，可以将输出写入[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]中使用下面的代码的控制台**表达式**形状：  
  
```  
System.Diagnostics.Debug.WriteLine(iResult);  
```  
  
 需要将这**表达式**后立即执行该操作，因此可以输出调试的结果的形状的形状。  
  
 或者，您可以编写一个简单的类创建调试 DLL 的自定义调试器包括一种方法可将作为一种格式的消息在业务流程中定义和在调试 DLL 中引用的输入。 作为参数传递消息的详细信息，请参阅[如何使用表达式来创建对象和调用对象方法](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md)。  
  
 此方法可以打开一个调试对话框，其中包括一个组合框或其他控件，以允许用户修改值，编辑将该消息放回在一起，并将其返回值作为签。  
  
 设置一个布尔变量，以指示您的业务流程是否处于调试模式，然后在其中你想要能够修改值业务流程中有一个点的任何位置，您可以添加**判定**具有一个实时形状：只有在调试模式变量设置为 True，或你想要检查特定条件时运行的分支。 调用您的方法从**表达式**形状中的活动分支**判定**。 当不再需要进行调试时，你将调试模式变量设置为 False，或删除**判定**形状完全并重新编译。  
  
## <a name="to-debug-a-net-component-called-by-an-orchestration"></a>若要调试业务流程调用的.NET 组件  
 以下步骤演示如何调试业务流程调用的.NET 组件：  
  
1. 打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]为组件的项目。  
  
2. 在业务流程调用的方法在组件中设置断点。  
  
3. 单击**调试**菜单，然后选择**附加到进程...** 若要显示**附加到进程**对话框。  
  
4. 单击**选择...** 按钮旁边**将附加到：** 以显示**选择代码类型**对话框。  
  
5. 单击此项可选择的选项**调试这些代码类型：** ，然后选择**托管**，然后单击**确定**按钮。  
  
6. 单击此项可选择**BTSNTSvc.exe**进程**可用进程**，然后单击**附加**按钮。  
  
7. 将消息发送到您的业务流程通过接收端口。  
  
8. .NET 组件应该在断点处停止。  
  
9. 你可以使用像往常一样调试[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
    > [!NOTE]
    >  为获得最佳结果，.NET 组件应注册在全局程序集缓存 (GAC) 中。  
  
## <a name="see-also"></a>请参阅  
 [业务流程调试器用户界面](../core/orchestration-debugger-user-interface.md)   
 [调试业务流程](../core/debugging-orchestrations.md)