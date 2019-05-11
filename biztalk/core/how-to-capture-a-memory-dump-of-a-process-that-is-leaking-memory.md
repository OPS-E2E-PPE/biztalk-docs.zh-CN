---
title: 如何捕获泄漏内存的进程的内存转储 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67404919-33a6-40ac-b1c4-09841db12fcf
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3df482776809fa9f1685d4466ca0688521c53e4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342664"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a>如何捕获泄漏内存的进程的内存转储
随着时间的推移，BizTalk 进程 BTSNTSvc.exe 被定义为具有内存泄漏时无法释放内存，它不再需要从而减少可用内存量。 可通过查看下的值来确定进程的内存使用率**Mem Usage**的列**进程**选项卡可找到**任务管理器**。 如果进程继续随时间消耗内存而不释放内存然后总体系统性能将受到负面影响。  
  
 本主题包含用于捕获可能泄漏内存，通过使用规则或通过手动捕获内存转储的 BizTalk 进程的内存转储的说明。 使用手动方法来捕获内存转储，如果内存泄漏的匹配项不是可预测。  
  
### <a name="to-capture-a-memory-dump-of-a-process-that-is-leaking-memory-by-using-a-rule"></a>若要捕获通过使用规则正在泄漏内存的进程的内存转储  
  
1.  启动调试诊断工具**启动**，**所有程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。  
  
2.  如果**选择规则类型**未显示添加规则向导对话框中，单击**工具**菜单中，选择**规则操作**，然后单击**添加规则**以显示添加规则向导。  
  
3.  选择**内存和处理泄漏**选项**选择规则类型**对话框，然后单击**下一步**。  
  
4.  选择怀疑泄漏内存，然后单击的 BTSNTSvc.exe 进程**下一步**。  
  
5.  在中**配置跟踪持续时间**对话框，请执行以下步骤：  
  
    1.  如果观察到的进程内存增长会立即发生，选中选项**启动内存跟踪立即激活规则是**。 如果观察到的进程内存增长不会立即发生，指定相应的分钟数**预热时间**启动内存跟踪将在其后的文本框。  
  
        > [!NOTE]
        >  如果某个组件加载到内存中，例如在 BizTalk 业务流程引用外部组件时，会出现内存泄漏，观察到的进程内存增长可能不会立即发生。  
  
    2.  指定相应的分钟数**跟踪时间**之后停止内存跟踪之前的文本框。 这应该是分钟数足够长，以再现内存泄漏。 经过此时间段后，将捕获进程的内存转储。  
  
    3.  选中选项**自动创建一个崩溃的规则以获取意外的进程退出的用户转储**。  
  
    4.  单击“下一步” 。  
  
6.  在中**选择转储位置和规则名称**对话框中，单击**下一步**以接受默认值。  
  
7.  在中**已完成规则**对话框中，单击**完成**若要接受默认值**立即激活规则**。  
  
8.  默认情况下，进程的内存转储将保存到 \Program Files\IIS Resources\DebugDiag\Logs\\<*崩溃规则的名称*\>目录的时间间隔后在本地计算机中指定**配置跟踪持续时间**对话框已过。  
  
### <a name="to-manually-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a>若要手动捕获泄漏内存的进程的内存转储  
  
1.  启动调试诊断工具**启动**，**所有程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。  
  
2.  如果**选择规则类型**将显示添加规则向导对话框中，单击**取消**。  
  
3.  单击此项可选择**进程**调试诊断工具的选项卡。  
  
4.  右键单击怀疑泄漏内存，然后单击的 BTSNTSvc.exe 进程**监视泄漏**。  
  
5.  监视中的进程的内存使用情况**任务管理器**和进程的内存使用率接近 BizTalk 计算机上的可用内存的 60-80%时手动捕获进程的内存转储，请右键单击进程并选择选项**创建完全用户转储**。  
  
6.  默认情况下，进程的内存转储将保存到本地计算机的 \Program Files\IIS Resources\DebugDiag\Logs\Misc\ 目录。  
  
## <a name="see-also"></a>请参阅  
 [如何使用调试诊断分析内存转储](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)