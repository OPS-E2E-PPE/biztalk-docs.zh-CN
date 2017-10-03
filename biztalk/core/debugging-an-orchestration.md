---
title: "调试业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging, Orchestration Debugger
- debugging, orchestrations
- Orchestration Debugger, about Orchestration Debugger
- Orchestrations Debugger
- orchestrations, debugging
- debugging, HAT
- HAT, debugging
ms.assetid: aae99cfd-d3dd-41c8-ae7a-b2733352cd69
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c231513ad75520fcadd88e5dd7d88104ddeeced5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="debugging-an-orchestration"></a>调试业务流程
使用业务流程调试器可以按每个形状来跟踪单个业务流程实例的活动。 业务流程调试器显示在业务流程设计器中创建的业务流程的呈现视图。  
  
 您可以在 BizTalk Server 管理控制台中访问“组概述”页中的业务流程调试器。  此操作通过快捷菜单从跟踪查询的输出中完成，方法是右键单击与业务流程类型关联的任一服务或消息实例。 进入此页后，您可以在业务流程调试器和“消息流”视图之间来回切换。  
  
 业务流程调试器提供以下功能：  
  
-   显示业务流程的呈现视图，可以在其中重新执行特定业务流程的每个处理步骤。  
  
-   使用业务流程调试器可以在任何业务流程形状之前设置断点并继续执行。  
  
-   使用业务流程调试器可以查看特定的变量和消息数据。  
  
-   在业务流程调试器中打开特定业务流程实例时，将自动启用该实例的所有跟踪选项。  
  
-   使用业务流程调试器可以继续、恢复为调试、终止特定业务流程实例。  
  
    > [!NOTE]
    >  取消部署程序集时，数据库将保留该程序集的跟踪选项和断点信息。 如果随后部署相同程序集，则将还原该程序集的选项和断点信息。  
  
 使用业务流程调试器的两种模式包括：  
  
-   [报告在业务流程调试器中的模式](../core/reporting-mode-in-orchestration-debugger.md)  
  
-   [在调试器中业务流程交互模式](../core/interactive-mode-in-orchestration-debugger.md)  
  
 取决于服务的状态，功能各不相同。 通过调用当前处于“在断点处”状态的任意服务实例，可以从任意视图执行交互调试。 有关调试业务流程的信息，请参阅[如何调用业务流程调试器和消息流视图](../core/how-to-invoke-the-orchestration-debugger-and-the-message-flow-views.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [业务流程调试器用户界面](../core/orchestration-debugger-user-interface.md)  
  
-   [使用业务流程调试器时的注意事项](../core/considerations-when-using-orchestration-debugger.md)  
  
-   [使用业务流程调试器视图](../core/working-with-the-orchestration-debugger-view.md)