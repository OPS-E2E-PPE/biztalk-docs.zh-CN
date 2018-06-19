---
title: 使用断点 |Microsoft 文档
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
ms.openlocfilehash: 60e9cee77f105b132438e621651ee90c0090c1be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289205"
---
# <a name="working-with-breakpoints"></a>使用断点
通过附加到挂起的业务流程或在类中设置断点，可以设置断点。  
  
> [!NOTE]
>  当取消部署程序集时，数据库将保持跟踪选项和该程序集的断点信息。 如果随后重新部署相同程序集，则将还原该程序集的选项和断点信息。  
  
### <a name="to-attach-to-a-suspended-orchestration"></a>附加到挂起的业务流程  
  
1.  使用挂起形状选择自动挂起的业务流程，然后转至步骤 3。  
  
2.  刷新视图，以检查实例现在是否显示为“已挂起”状态。  
  
3.  单击**恢复在调试**。  
  
     业务流程将恢复为“在断点处”状态。 现在可以进行交互调试。  
  
### <a name="to-switch-to-the-message-flow-view"></a>切换到“消息流”视图  
  
-   右键单击结果列表中的单元格，然后选择**消息流**从快捷菜单。  
  
## <a name="see-also"></a>另请参阅  
 [使用业务流程调试器视图](../core/working-with-the-orchestration-debugger-view.md)