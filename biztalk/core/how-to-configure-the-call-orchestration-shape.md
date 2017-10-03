---
title: "如何配置调用业务流程形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Call Orchestration shape [Orchestration Designer], parameters
- Call Orchestration shape [Orchestration Designer], configuring
- Call Orchestration shape [Orchestration Designer], about Call Orchestration shapes
- configuring [Orchestration Designer], Call Orchestration shapes
- Call Orchestration shape [Orchestration Designer]
- nonserializable objects
- orchestrations, nonserializable objects
- Call Orchestration shape [Orchestration Designer], referencing orchestrations
- orchestrations, parameters
ms.assetid: 718ce2a0-ac08-4662-8b4e-1be279dbc749
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dabb73b3bed616f17c69923799169a7c6ca2b6d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-call-orchestration-shape"></a>如何配置调用业务流程形状
**调用 Orchestration**形状可以用于以同步方式调用另一个项目中引用的业务流程。 这允许在多个 BizTalk 项目中重复使用公用的业务流程工作流模式。 当调用另一个嵌套的业务流程的情况下同步**调用 Orchestration**封闭业务流程等待嵌套的业务流程，在继续之前完成的形状。  
  
 您可以指定将传递到嵌套的业务流程的参数。 参数可以是消息、变量、端口引用、角色链接或相关集。 传入的端口引用、 角色链接和关联集所有执行操作时像自寻址包络线： 提供可用于将信息发送回封闭业务流程的嵌套的业务流程信息。  
  
> [!CAUTION]
>  如果您将不可序列化的对象（例如 XmlDocument 或 XmlNode）作为参数传递到某一业务流程，它将失败。  
  
 有关如何使用的示例**调用 Orchestration**形状，请参阅[CallOrchestration （BizTalk Server 示例）](../core/callorchestration-biztalk-server-sample.md)。  
  
### <a name="to-configure-a-call-orchestration-shape"></a>配置调用业务流程形状  
  
1.  使用**Orchestration 选择**下拉列表框中，选择一个从列表中的业务流程。  
  
2.  使用**业务流程参数**网格控件中，指定要传递给业务流程自变量-中指定**Orchestration 选择**下拉列表框-调用的。 您通过键入变量的名称或从单元格的下拉列表中单击某一变量，在“变量”列的单元格中指定这些参数，每个单元格一个变量。  
  
3.  若要配置**调用 Orchestration**调整根据服务和在对话框中指定的自变量，请单击**确定**。 若要关闭**调用业务流程配置**对话框，而不进行任何更改到**调用 Orchestration**形状，请单击**取消**。  
  
    > [!CAUTION]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不支持递归业务流程。 如果业务流程 A 调用或启动业务流程 B，则业务流程 B 既无法直接调用或启动业务流程 A，也无法调用或启动直接或间接调用业务流程 A 的任何业务流程。  
  
## <a name="referenced-orchestrations"></a>引用的业务流程  
 为使引用的业务流程可调用，请确保为调用的业务流程配置以下属性：  
  
-   设置**类型修饰符**属性**公共**调用业务流程。 若要设置**类型修饰符**属性的业务流程**公共**，在 Microsoft 中打开业务流程[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，单击顶部的业务流程，以显示绿色启动形状**业务流程属性**对话框并设置**类型修饰符**属性**公共**。  
  
-   设置**激活**属性中的业务流程的初始接收形状**False**。  
  
## <a name="orchestration-selection-drop-down-list-box"></a>“业务流程选择”下拉列表框  
 单击该下拉列表框中的下箭头可以查看可用服务并进行选择。 下表包含可从当前业务流程中调用的所有服务，包括引用的程序集。  
  
## <a name="orchestration-parameters-grid-control"></a>“业务流程参数”网格控件  
 指定要传递到参数化的业务流程，通过使用参数**业务流程参数**网格控件。 网格包含四列： 作用域、 参数名称、 参数类型和参数方向中的变量。 您只能对第一列进行更改；其他列是只读的。  
  
 当你选择有效的业务流程时，其参数填充参数名称、 类型和方向列的网格控件。 然后，您可以选择每一行中要作为参数传递的变量。 您从“作用域中的变量”列的各单元格上的下拉列表中选择这些变量。 此列表显示在相邻的“参数类型”单元格中指定的类型的所有可用变量。 如果该类型只有一个对象可用，将自动用该对象填充“作用域中的变量”单元格。 您还可以在“作用域中的变量”单元格中键入，以便选择在该下拉列表中提供的变量。  
  
> [!NOTE]
>  因为**调用 Orchestration**形状调用业务流程，在此对话框中选择"Orchestration Parameters"实际上指业务流程变量。  
  
 如果您在调用的业务流程没有定义的参数，则该对话框中的网格控件将不可用。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置开始业务流程形状](../core/how-to-configure-the-start-orchestration-shape.md)