---
title: "如何捕获泄露内存的进程内存转储 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67404919-33a6-40ac-b1c4-09841db12fcf
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2999ce9a188b2d9b94df11328485e8b7440ecec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a>如何捕获泄露内存的进程内存转储
如果 BizTalk 进程 BTSNTSvc.exe 无法释放不再需要的内存，因此会随着时间减少可用内存量，则定义为内存泄漏。 可以查看下的值来确定进程的内存使用率**内存使用**列**进程**选项卡中可找到**任务管理器**。 如果进程继续随时间消耗内存而不释放内存，系统的整体性能将受到不良影响。  
  
 本主题提供了通过使用规则或手动捕获内存转储来捕获被怀疑泄漏内存的 BizTalk 进程的内存转储的说明。 如果内存泄漏不是可预测的，则使用手动方法来捕获内存转储。  
  
### <a name="to-capture-a-memory-dump-of-a-process-that-is-leaking-memory-by-using-a-rule"></a>通过使用规则捕获泄漏内存的进程的内存转储  
  
1.  启动调试诊断工具从**启动**，**所有程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。  
  
2.  如果**选择规则类型**未显示添加规则向导对话框，单击**工具**菜单上，选择**规则操作**，然后单击**添加规则**以显示添加规则向导。  
  
3.  选择**内存和处理泄漏**选项**选择规则类型**对话框，然后单击**下一步**。  
  
4.  选择 BTSNTSvc.exe 进程怀疑泄露内存和单击**下一步**。  
  
5.  在**配置跟踪的持续时间**对话框请按照下列步骤：  
  
    1.  如果观察到的进程内存增长会立即发生，请检查选项**启动跟踪立即激活规则时的内存**。 如果观察到的进程内存增长不会立即发生，指定适当数量的分钟**预热时间**后将启动内存跟踪的文本框。  
  
        > [!NOTE]
        >  如果在将某个组件加载到内存时导致内存泄漏，可能不会立即出现能观察到的进程内存增长，例如，在 BizTalk 业务流程引用外部组件时。  
  
    2.  指定适当数量的分钟**跟踪时间**内存跟踪将停止在其后的文本框。 这应该是一个足够长的分钟数，以再现内存泄漏。 进程的内存转储将在此时间段之后被捕获。  
  
    3.  检查选项**的崩溃自动创建规则以在进程意外的退出获取用户转储**。  
  
    4.  单击 **“下一步”**。  
  
6.  在**选择转储位置和规则名称**对话框中，单击**下一步**以接受默认值。  
  
7.  在**规则完成**对话框中，单击**完成**以接受默认值的**立即激活规则**。  
  
8.  默认情况下，进程的内存转储将保存到 \Program Files\IIS Resources\DebugDiag\Logs\\<*崩溃规则的名称*> 目录中指定的时间段后的本地计算机**配置跟踪的持续时间**对话框已过。  
  
### <a name="to-manually-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a>手动捕获泄漏内存的进程的内存转储  
  
1.  启动调试诊断工具从**启动**，**所有程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。  
  
2.  如果**选择规则类型**显示的添加规则向导对话框，请单击**取消**。  
  
3.  单击以选择**进程**选项卡的调试诊断工具。  
  
4.  右键单击 BTSNTSvc.exe 流程怀疑泄露内存和单击**监控泄漏**。  
  
5.  监视在进程的内存使用率**任务管理器**和进程的内存使用率接近 BizTalk 计算机; 上的可用内存的 60-80%时手动捕获进程的内存转储，请右键单击过程并选择选项**创建完整用户转储**。  
  
6.  默认情况下，进程的内存转储将保存到本地计算机的 \Program Files\IIS Resources\DebugDiag\Logs\Misc\ 目录中。  
  
## <a name="see-also"></a>另请参阅  
 [如何使用调试诊断分析内存转储](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)