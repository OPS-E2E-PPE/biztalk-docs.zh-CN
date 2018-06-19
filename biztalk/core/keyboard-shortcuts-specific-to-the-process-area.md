---
title: 键盘快捷方式所特有的过程区域 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- keyboard shortcuts, Orchestration Designer
- Orchestration Designer, keyboard shortcuts
ms.assetid: d993d341-99f2-4788-b1f3-6a8b911e5278
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba60b23c6c8719789e8de6903dbb538fa5088b08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262061"
---
# <a name="keyboard-shortcuts-specific-to-the-process-area"></a>过程区域特有的键盘快捷方式
下表对流程区域中可用的键盘导航进行了说明，该区域是用于定义业务流程处理流程的设计图面的中心区域：  
  
|Key|效果|  
|---------|------------|  
|向下键|将选择内容移至下方的下一条连接线或下一个形状。 如果该形状连接到下方的多个分支（与判定形状的情况类似），则选择内容将移至最左侧分支中的第一个形状。<br /><br /> 如果选择内容位于业务流程的结束形状上，则按此键不起作用，因为其下方没有其他任何形状。|  
|向上键|将选择内容移至上方的上一条连接线或上一个形状。 如果该形状连接到上方的多个分支，则选择内容将移至最左侧分支上的最后一个形状。<br /><br /> 按下此键没有时生效**启动**选择形状。|  
|向左键|如果选择内容位于发送形状或接收形状上，并且该形状连接到某端口：<br /><br /> -如果形状具有通向左端口图面中的端口的端口连接器，焦点和所选内容将移动到形状的端口连接器中。<br />-如果形状具有通向右端口图面中的端口的端口连接器，按此密钥不起作用。<br />-如果形状不具有的任何端口连接器，导航，则与任何其他形状相同。<br /><br /> 对于其他形状（或未连接到端口的发送形状或接收形状）：<br /><br /> -如果分支存在形状在其上的当前分支左侧的分支中, 进行选择后，所选内容移到最接近的形状上向左分支。<br />-密钥不起作用业务流程中的其他任何位置。|  
|向右键|与向左键相同，只是方向相反。|  
|Home|选择内容将移至从业务流程的开始形状引出的连接线。|  
|END|选择内容将移至通向业务流程的结束形状中的连接线。|  
|Num Lock + -|折叠选定的复杂形状。|  
|Num Lock + +|展开选定的复杂形状。|  
|Num Lock + *|展开选定的复杂形状，以及其包含的所有子复杂形状。|  
  
## <a name="see-also"></a>另请参阅  
 [业务流程设计器键盘快捷键](../core/orchestration-designer-keyboard-shortcuts.md)