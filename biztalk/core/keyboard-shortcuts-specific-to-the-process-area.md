---
title: 键盘快捷方式特定于流程区域 |Microsoft Docs
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
ms.openlocfilehash: 0dc59da751ee8acb68ff4d38f42b08020ae94b66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329464"
---
# <a name="keyboard-shortcuts-specific-to-the-process-area"></a>过程区域专用的键盘快捷方式
下表描述了在流程区域，用于定义的处理流程的业务流程设计图面中心区域中可用的键盘导航。  
  
|Key|效果|  
|---------|------------|  
|向下键|将所选内容移动到一条连接线或形状下面。 如果该形状连接到多个分支下 （如中所示的判定形状的情况下），所选内容移到最左边的分支中的第一个形状。<br /><br /> 如果选择内容位于业务流程的结束形状上，按此键无效，因为其下方没有其他任何形状。|  
|向上键|将所选内容移动到一条连接线或形状更高版本。 如果该形状连接到更高版本的多个分支中，选择内容将移到最后一个形状上最左边的分支。<br /><br /> 按此键没有时生效**启动**选择形状。|  
|向左键|如果所选内容上发送或接收形状，并且该形状连接到端口：<br /><br /> -如果该形状具有通向左侧端口图面中的端口的端口连接线，则焦点和选择内容移至端口连接线的形状中。<br />-如果该形状具有通向右侧端口图面中的端口的端口连接线，按此键无效。<br />-如果该形状具有没有端口连接线，导航将是与使用其他任何形状相同。<br /><br /> 对于其他形状 （或未连接到端口的发送或接收形状）：<br /><br /> -如果所选内容中一个分支，并且分支存在包含形状左侧的 current branch，所选内容移至左侧分支上最近的形状。<br />-键没有任何影响业务流程中的其他任何位置。|  
|向右键|相同向左箭头键，但在相反的方向。|  
|Home|选择更改会导致从业务流程的开始形状连接线。|  
|END|所选内容更改为通向业务流程的结束形状的连接器。|  
|NUM LOCK +-|折叠选定的复杂形状。|  
|NUM LOCK + +|展开选定的复杂形状。|  
|NUM LOCK + *|展开所选的复杂形状，以及可能具有的所有子复杂形状。|  
  
## <a name="see-also"></a>请参阅  
 [业务流程设计器键盘快捷方式](../core/orchestration-designer-keyboard-shortcuts.md)