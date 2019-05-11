---
title: 使用断点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Orchestration Debugger, breakpoints
- Orchestration Debugger, suspended orchestrations
- Orchestration Debugger, Message Flow view
- Orchestration Debugger, service options
- Message Flow view [Orchestration Debugger]
ms.assetid: aad1a2b0-d705-49cd-85f7-b0ab2e473bcc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d1129e2eaa6c31a90e89e99f377f825990ee614
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398544"
---
# <a name="working-with-breakpoints"></a>使用断点
通过将附加到挂起的业务流程，或通过在类上设置断点，可以设置断点。  
  
> [!NOTE]
>  如果取消部署程序集，数据库将保留的跟踪选项和断点信息，该程序集。 如果随后部署再次在同一程序集中，将还原的选项和断点信息，该程序集。  
  
### <a name="to-attach-to-a-suspended-orchestration"></a>若要将附加到挂起的业务流程  
  
1.  选择使用挂起形状，自动挂起的业务流程，然后转到步骤 3。  
  
2.  刷新视图以检查实例现在显示处于 Suspended 状态。  
  
3.  单击**恢复为调试**。  
  
     业务流程将在断点处状态恢复。 你现在可以以交互方式调试。  
  
### <a name="to-switch-to-the-message-flow-view"></a>若要切换到消息流视图  
  
-   右键单击结果列表中的单元格并选择**消息流**从快捷菜单。  
  
## <a name="see-also"></a>请参阅  
 [使用“业务流程调试器”视图](../core/working-with-the-orchestration-debugger-view.md)