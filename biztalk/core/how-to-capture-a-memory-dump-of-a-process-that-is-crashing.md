---
title: 如何捕获所 Crashing 进程内存转储 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f436b72-2b6a-4519-acc3-e7ba978651fe
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e87664180b7ad4d5fdcd121542974a08b8634d55
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969563"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-crashing"></a>如何捕获所 Crashing 进程内存转储
BTSNTSvc.exe 定义为 BizTalk 进程**崩溃**进程由 Windows 的意外终止时。 崩溃通常是由进程中未处理的异常（如访问冲突或堆栈溢出）引起的。 在这些情况下，Windows 默认调试器，灾难恢复。Watson (drwtsn32.exe) 捕获异常并终止进程。  
  
 若要捕获崩溃进程的内存转储，可按照下面的这些步骤配置调试诊断工具来捕获未处理的异常：  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-crash-dump"></a>若要配置调试诊断工具，以捕获的故障转储  
  
1.  启动调试诊断工具从**启动**，**所有程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。  
  
2.  如果**选择规则类型**未显示添加规则向导对话框，单击**工具**菜单上，选择**规则操作**，然后单击**添加规则**以显示添加规则向导。  
  
3.  选择**崩溃**选项**选择规则类型**对话框，然后单击**下一步**。  
  
4.  选择**特定进程**中**选择目标类型**对话框，然后单击**下一步**。  
  
5.  选择所发生故障，然后单击的 BTSNTSvc.exe 进程**下一步**。  
  
6.  在**高级配置**对话框中，单击**下一步**以接受默认值。  
  
7.  在**选择转储位置和规则名称**对话框中，单击**下一步**以接受默认值。  
  
8.  在**规则完成**对话框中，单击**完成**以接受默认值的**立即激活规则**。  
  
9. 默认情况下，进程的内存转储将保存到 \Program Files\IIS Resources\DebugDiag\Logs\\<*崩溃规则的名称*\>的本地计算机下一步目录时间在过程中发生未处理的异常。  
  
## <a name="see-also"></a>另请参阅  
 [如何使用调试诊断分析内存转储](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)