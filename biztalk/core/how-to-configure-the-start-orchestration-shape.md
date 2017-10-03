---
title: "如何配置开始业务流程形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f8181849b700939ba86f55cd372b80ed2ebf70e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-start-orchestration-shape"></a>如何配置开始业务流程形状
**启动 Orchestration**形状是类似于**调用 Orchestration**形状，但你调用以异步方式与其他业务流程**启动 Orchestration**形状 — 也就是说，调用该业务流程的控制流继续执行后续调用，而无需等待调用的业务流程，以完成其工作。  
  
 您可以指定将传递到被调用的业务流程的参数。 参数可以是消息、变量、端口引用、角色链接或相关集。 **启动 Orchestration**只能采用形状*中*参数; 它无法接受*出*或*ref*参数。  
  
> [!CAUTION]
>  如果将非可序列化的对象，如 XmlDocument 或 XmlNode 作为参数传递给业务流程中，文件将失败。  
  
 **启动 Orchestration**形状是在其中你可以在作为参数传递的端口调转极性的唯一形状 — 例如*使用*端口 （发送端口） 可以在传递给调用的业务流程，但调用的业务流程可以将其视为*实现*端口 （接收端口）。 请注意，只能通过使用直接绑定的端口实现这一点。  
  
 **启动 Orchestration**形状还可以用于调用另一个项目中引用的业务流程。 这允许在多个 BizTalk 项目中重复使用公用的业务流程工作流模式。 对于引用业务流程可以被调用，请确保**类型修饰符**调用的业务流程的属性设置为**公共**。 若要设置**类型修饰符**属性的业务流程**公共**，在 Microsoft 中打开业务流程[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，单击顶部的业务流程，以显示绿色启动形状**业务流程属性**对话框并设置**类型修饰符**属性**公共**。 默认值为**类型修饰符**是**私有**。  
  
 有关如何使用的示例**启动 Orchestration**形状，请从下载 SDK 示例"实现的散点图和收集模式" [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
### <a name="to-configure-a-start-orchestration-shape"></a>若要配置启动 Orchestration 形状  
  
1.  使用**Orchestration 选择**下拉列表框中，选择一个从列表中的业务流程。  
  
2.  使用**业务流程参数**网格控件中，指定要传递给业务流程自变量-中指定**Orchestration 选择**下拉列表框-，它开始。 您通过键入变量的名称或从单元格的下拉列表中单击某一变量，在“变量”列的单元格中指定这些参数，每个单元格一个变量。  
  
3.  若要配置**启动 Orchestration**调整根据服务和在对话框中指定的自变量，请单击**确定**。 若要关闭**启动业务流程配置**对话框，而不进行任何更改到**启动 Orchestration**形状，请单击**取消**。  
  
    > [!CAUTION]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不支持递归业务流程。 如果业务流程 A 调用或启动业务流程 B，则业务流程 B 既无法直接调用或启动业务流程 A，也无法调用或启动直接或间接调用业务流程 A 的任何业务流程。  
  
## <a name="orchestration-selection-drop-down-list-box"></a>“业务流程选择”下拉列表框  
 单击该下拉列表框中的下箭头可以查看可用的业务流程并进行选择。 此列表包含可从当前业务流程中启动的所有业务流程，包括引用的程序集。  
  
## <a name="orchestration-parameters-grid-control"></a>“业务流程参数”网格控件  
 指定要传递到参数化的业务流程，通过使用参数**业务流程参数**网格控件。 网格包含四列： 作用域、 参数名称、 参数类型和参数方向中的变量。 您只能对第一列进行更改；其他列是只读的。  
  
 在您选择某一有效业务流程后，其参数将自动填充该网格控件的参数名称、类型和方向列。 然后，您可以选择每一行中要作为参数传递的变量。 您从“作用域中的变量”列的各单元格上的下拉列表中选择这些变量。 此列表显示在相邻的“参数类型”单元格中指定的类型的所有可用变量。 如果该类型只有一个对象可用，将自动用该对象填充“作用域中的变量”单元格。 您还可以在“作用域中的变量”单元格中键入，以便选择在该下拉列表中提供的变量。  
  
> [!NOTE]
>  因为**启动 Orchestration**形状启动业务流程，在此对话框中选择"Orchestration Parameters"实际上指业务流程变量。  
  
 如果您正在执行的业务流程没有已定义的参数，则该对话框中的网格控件将不可用。  
  
## <a name="in-this-section"></a>本节内容  
 [如何创建接收上调用的业务流程的订阅](../core/how-to-create-receive-subscriptions-at-invoked-orchestrations.md) 
  
## <a name="see-also"></a>另请参阅  
 [如何配置调用业务流程形状](../core/how-to-configure-the-call-orchestration-shape.md)