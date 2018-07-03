---
title: 如何配置启动业务流程形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Start Orchestration shapes
- Start Orchestration shape [Orchestration Designer], parameters
- Start Orchestration shape [Orchestration Designer], configuring
- orchestrations, starting
- Start Orchestration shape [Orchestration Designer]
- Start Orchestration shape [Orchestration Designer], starting orchestrations
- Start Orchestration shape [Orchestration Designer], about Star Orchestration shape
ms.assetid: 9d01c41e-9bc5-4c1c-a869-b2f0df13036a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4877d775b30f7ab407f57ebf2679f8cb65a0ef08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974910"
---
# <a name="how-to-configure-the-start-orchestration-shape"></a>如何配置启动业务流程形状
**启动业务流程**形状是类似于**调用业务流程**形状，但您调用以异步方式与其他业务流程**启动业务流程**形状-即，调用该业务流程中的控制流将继续调用，而无需等待调用的业务流程完成其工作。  
  
 您可以指定将传递到被调用的业务流程的参数。 参数可以是消息、变量、端口引用、角色链接或相关集。 **启动业务流程**形状可能采用*中*参数; 它不能采用*out*或者*ref*参数。  
  
> [!CAUTION]
>  如果将 XmlDocument 或 XmlNode 之类的非可序列化对象作为参数传递给业务流程中，它将失败。  
  
 **启动业务流程**形状是仅在其中可以在作为参数传递的端口反转极性的形状 — 例如*使用*端口 （发送端口） 可以传递给调用的业务流程，但调用的业务流程可以将它视为*实现*端口 （接收端口）。 请注意，只能通过使用直接绑定的端口实现这一点。  
  
 **启动业务流程**形状还可用来调用另一个项目中引用的业务流程。 这允许在多个 BizTalk 项目中重复使用公用的业务流程工作流模式。 对于可调用的被引用业务流程，请确保**的类型修饰符**调用的业务流程的属性设置为**公共**。 若要设置**的类型修饰符**到业务流程的属性**公共**，在 Microsoft 中打开该业务流程[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，单击顶部的业务流程以显示绿色启动形状**业务流程属性**对话框并设置**的类型修饰符**属性设置为**公共**。 默认值为**的类型修饰符**是**专用**。  
  
 有关如何使用的示例**启动业务流程**形状中，从下载 SDK 示例"实现分散和收集模式" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
### <a name="to-configure-a-start-orchestration-shape"></a>若要配置启动业务流程形状  
  
1. 使用**业务流程选择**下拉列表框中，选择某一业务流程从列表中。  
  
2. 使用**业务流程参数**网格控件，指定要传递到业务流程参数-中指定的那样**业务流程选择**下拉列表框-，它开始。 您通过键入变量的名称或从单元格的下拉列表中单击某一变量，在“变量”列的单元格中指定这些参数，每个单元格一个变量。  
  
3. 若要配置**启动业务流程**形状根据服务和对话框中指定的参数，请单击**确定**。 若要关闭**启动业务流程配置**对话框，但不进行任何更改**启动业务流程**形状，请单击**取消**。  
  
   > [!CAUTION]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不支持递归业务流程。 如果业务流程 A 调用或启动业务流程 B，则业务流程 B 既无法直接调用或启动业务流程 A，也无法调用或启动直接或间接调用业务流程 A 的任何业务流程。  
  
## <a name="orchestration-selection-drop-down-list-box"></a>“业务流程选择”下拉列表框  
 单击该下拉列表框中的下箭头可以查看可用的业务流程并进行选择。 此列表包含可从当前业务流程中启动的所有业务流程，包括引用的程序集。  
  
## <a name="orchestration-parameters-grid-control"></a>“业务流程参数”网格控件  
 指定要传递到通过参数化的业务流程使用的参数**业务流程参数**网格控件。 网格具有四列： 作用域、 参数名称、 参数类型和参数方向中的变量。 您只能对第一列进行更改；其他列是只读的。  
  
 在您选择某一有效业务流程后，其参数将自动填充该网格控件的参数名称、类型和方向列。 然后，您可以选择每一行中要作为参数传递的变量。 您从“作用域中的变量”列的各单元格上的下拉列表中选择这些变量。 此列表显示在相邻的“参数类型”单元格中指定的类型的所有可用变量。 如果该类型只有一个对象可用，将自动用该对象填充“作用域中的变量”单元格。 您还可以在“作用域中的变量”单元格中键入，以便选择在该下拉列表中提供的变量。  
  
> [!NOTE]
>  因为**启动业务流程**形状将启动业务流程，在此对话框中选择"业务流程参数"实际上表示业务流程变量。  
  
 如果您正在执行的业务流程没有已定义的参数，则该对话框中的网格控件将不可用。  
  
## <a name="in-this-section"></a>本节内容  
 [如何创建接收调用的业务流程上的订阅](../core/how-to-create-receive-subscriptions-at-invoked-orchestrations.md) 
  
## <a name="see-also"></a>请参阅  
 [如何配置调用业务流程形状](../core/how-to-configure-the-call-orchestration-shape.md)