---
title: 调试业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b0e1ad8529e3f91f5b34ad60585677892989368
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390441"
---
# <a name="debugging-an-orchestration"></a>调试业务流程
业务流程调试器，您可以在形状的形状的基础上跟踪单个业务流程实例的活动。 它将显示在业务流程设计器中创建的业务流程的呈现的视图。  
  
 访问 BizTalk Server 管理控制台中组概述页中的业务流程调试器。  这是通过快捷菜单的跟踪查询输出中，请右键单击任一服务或业务流程类型与实例相关联的消息。 您可以在我此页上，您可以来回切换之间业务流程调试器和消息流视图。  
  
 业务流程调试器提供了以下功能：  
  
- 显示可以在其中重播特定业务流程的每个处理步骤的业务流程的呈现的视图。  
  
- 可以是任何业务流程形状之前设置断点并继续执行。  
  
- 使您能够查看特定的变量和消息数据。  
  
- 自动启用的所有特定业务流程实例的跟踪选项时该实例将在业务流程调试器中打开。  
  
- 这样，可以继续，请恢复为调试，然后终止特定业务流程实例的功能。  
  
  > [!NOTE]
  >  如果取消部署程序集，数据库将保留的跟踪选项和取消部署程序集的断点信息。 如果随后部署相同程序集，将还原的选项和断点信息，该程序集。  
  
  使用业务流程调试器的两种模式是：  
  
- [业务流程调试器中的“报告”模式](../core/reporting-mode-in-orchestration-debugger.md)  
  
- [业务流程调试器中的“交互”模式](../core/interactive-mode-in-orchestration-debugger.md)  
  
  功能不同，具体取决于服务的状态。 您可以执行交互式调试通过调用当前在在断点处状态，从任意视图中的任何服务实例。 有关调试业务流程的信息，请参阅[如何调用业务流程调试器和消息流视图](../core/how-to-invoke-the-orchestration-debugger-and-the-message-flow-views.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [业务流程调试器用户界面](../core/orchestration-debugger-user-interface.md)  
  
-   [使用业务流程调试器时的注意事项](../core/considerations-when-using-orchestration-debugger.md)  
  
-   [使用“业务流程调试器”视图](../core/working-with-the-orchestration-debugger-view.md)