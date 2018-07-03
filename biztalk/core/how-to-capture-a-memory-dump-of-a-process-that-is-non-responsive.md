---
title: 如何捕获的非响应进程的内存转储 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ad53376-2fab-4dee-8a6a-a44d157390f2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f79cbc492611a6a1271e45b4198401b3d17452e7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016184"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive"></a>如何捕获的非响应进程的内存转储
BizTalk 进程 BTSNTSvc.exe 被定义为**悬挂**过程似乎停止响应。 挂起进程的常见情况包括：  
  
- 业务流程似乎要停止运行。  
  
- 消息未处理。  
  
- 发生常规超时问题。  
  
- BizTalk 进程 BTSNTSvc.exe 消耗异常高的 CPU 周期中查看**进程**选项卡**任务管理器**。  
  
  若要捕获挂起的 BTSNTSvc.exe 进程的内存转储，请执行以下步骤。  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-hang-dump"></a>配置调试诊断工具以捕获挂起转储  
  
1.  启动调试诊断工具**启动**，**所有程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。  
  
2.  如果**选择规则类型**显示的规则配置向导的对话框中，单击**取消**按钮。  
  
3.  单击**进程**调试诊断工具的选项卡。  
  
4.  右键单击无响应的 BTSNTSvc.exe 进程，然后选择**创建完全用户转储**。 默认情况下，进程的内存转储将保存到本地计算机的 \Program Files\IIS Resources\DebugDiag\Logs\Misc 目录中。  
  
## <a name="see-also"></a>请参阅  
 [如何使用调试诊断分析内存转储](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)