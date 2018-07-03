---
title: 如何配置接收形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- filter expressions, Receive shape [Orchestration Designer]
- Receive shape [Orchestration Designer], about Receive shape
- configuring [Orchestration Designer], Receive shapes
- Receive shape [Orchestration Designer]
- Receive shape [Orchestration Designer], filter expressions
ms.assetid: 15aadee4-fa05-4edd-a191-e4d191c1ea22
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60d2a0913e6921b5868a16c58c7ed2c7ae3d46e4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989702"
---
# <a name="how-to-configure-the-receive-shape"></a>如何配置接收形状
![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")  
接收形状  

 一个**接收**形状可用于启动业务流程。 如果您设置**激活**属性设置为**True**，运行时引擎将测试传入消息以查看是否属于正确的类型，如果应用了筛选器，筛选器表达式是满足的条件。 如果满足消息接收条件，运行时引擎创建并运行新的业务流程实例，并**接收**形状将接收该消息。  

> [!NOTE]
>  如果**激活**接收形状的属性设置为 True，**接收**必须在业务流程中的第一个操作。  

> [!NOTE]
>  如果**激活**属性设置为 False 上所有**接收**形状，您的业务流程必须调用由另一个业务流程才能运行。  

> [!NOTE]
>  如果将放**接收**内具有的作用域形状**激活**属性设置为**True**，然后将.NET 类变量而无需更改添加到您的业务流程变量的**使用默认构造函数**属性设置为**False**，则激活接收语句将在生成的 XLANG/S 代码中，范围之外但设计图面上也会继续对将其显示为正在该范围中。  

 每个业务流程必须至少一个**接收**形状和**激活**属性设置为**True**。  

 对于以前已发送的消息，如果希望接收到间接或异步响应（不在请求-响应端口上），则需要将该消息与当前正在运行的业务流程实例相关联，以便响应者可以获得对正确实例的响应。 如果您计划继续对传入消息中的值进行关联，则可以对接收形状应用初始化相关集，或者您也可以应用沿用相关集，以便使用以前初始化的相关集进行关联。 有关详细信息，请参阅[业务流程中使用相关性](../core/using-correlations-in-orchestrations.md)。  

### <a name="to-configure-a-receive-shape"></a>配置接收形状  

1.  设置消息和端口操作。  

    1.  在“业务流程视图”窗口中，确认您的业务流程具有消息以及为要接收的消息类型定义的端口操作。  

         在属性窗口中，选择要从接收的消息**消息**属性下拉列表。  

    2.  在属性窗口中，选择要接收的消息的端口操作**操作**下拉列表。  

         -或-  

         将从接收连接器拖**接收**形状将接收该消息的端口套接字。  

2.  指定的**接收**接收形状将激活业务流程。  

3.  在“属性”窗口中，将“激活”属性设置为 True。  

    1.  在属性窗口中，单击**省略号**(**...**) 按钮以创建一个筛选器以限制的消息的筛选器表达式属性，此**接收**接收形状接受。  

         -或-  

         右键单击**接收**形状，然后单击**编辑筛选器表达式**。  

    2.  **筛选器表达式**对话框随即出现。 使用该对话框可以创建一个或多个筛选器表达式。  

        > [!NOTE]
        >  必须定义消息类型，并将其分配给**接收**形状之前可以向其应用筛选器。  

4.  指定相关集来限制的消息**接收**接收形状接受。  

    -   你想要按照每个相关集，请检查该相关集从下拉列表**沿用相关集**属性。  

    -   有关每个相关集要用于初始化，检查该相关集从下拉列表**初始化相关集**属性。  

## <a name="filter-expression-grid-control"></a>筛选器表达式网格控件  
 您可以通过使用此网格控件来定义构成表达式的谓词，生成筛选器表达式。 您还可以从网格的单元格中添加、编辑和删除谓词。 此网格控件具有四列： 属性、 运算符、 值和分组。  

- **属性。** 您可以键入某一属性引用，或者从单元格的下拉列表中选择一个属性。 该列表包含传入消息的属性。  

- **运算符。** 您可以在此单元格中键入某一运算符，或者从下拉列表中选择一个运算符。 可能的选项包括：  


  | 操作数 |           含义           |
  |---------|-----------------------------|
  |   ==    |         等于         |
  |   !=    |       不等于       |
  |    <    |        小于         |
  |   \<=   |  小于或等于   |
  |    >    |       大于       |
  |   \>=   | 大于或等于 |
  | Exists  |           Exists            |


- **值。** 中的单元格**值**列所能容纳您键入的任何常量： 字符串文本、 整数文字，则为 null。  

  > [!NOTE]
  >  如果选择的属性为字符串类型，则需要用引号将该值括起来。 例如 SMTP.From = "MyServer"。  

- **分组。** 使用此列可控制谓词分组。 筛选器表达式始终用析取范式 (DNF) 形式表示，因此可以自动确定分组。 AND 表示谓词要与其后的谓词分在一组，而 OR 表示该谓词与下一行中的谓词相互独立。 将谓词组合在一起后，网格控件的左侧将显示灰色括号。 谓词组不能嵌套。 如果您不在此单元格中指定值，则该单元格默认的值为 AND。  

  例如，您可以创建如下所示的表达式：  

  `MSMQ.MsgID = 1`  

  使用此筛选器，发送端口组将只订阅 MSMQ 消息 ID 为 1 的消息。  

  您可以创建其他表达式，并指定该表达式与其他表达式有 AND 或 OR 关系，例如：  

  `MSMQ.MsgID = 1 OR`  

  `SMTP.From = "MyServer"`  

  在这种情况下，发送端口组将订阅 MSMQ 消息 ID 为 1 或发自名为 MyServer 的 SMTP 服务器的所有消息。  

## <a name="hint-label"></a>提示标签  
 该字段提供用户指导。 标签文本将根据包含活动单元格的列而变化。 标签文本将显示列名称，后随如下指导文本：  

-   **属性。** 请从列表中选择传入消息的属性。  

-   **运算符。** 选择用于将属性与值进行比较的运算符。  

-   **值。** 从列表中选择某一消息属性，或者键入文本值。  

-   **分组。** 指定此行要如何与下一行组合在一起。 “AND”将连接行，而“OR”将分隔行。  

## <a name="move-up-button"></a>“上移”按钮  
 单击此按钮可以将所选行上移。 (首次通过单击选择行*向右箭头*(**>)** 按钮位于左侧和右侧的网格控件。)  

## <a name="move-down-button"></a>“下移”按钮  
 单击此按钮可以将所选行下移。 (首次通过单击选择行*向右箭头*(**>)** 按钮位于左侧和右侧的网格控件。)  

## <a name="filter-expression-created-field"></a>“创建的筛选器表达式”字段  
 此只读文本框将随着您生成表达式而显示该表达式。  

## <a name="in-this-section"></a>本节内容  
 [使用带接收消息形状的筛选器](../core/using-filters-with-the-receive-message-shape.md)