---
title: 如何捕获内存转储进程的 Crashing |Microsoft Docs
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
ms.openlocfilehash: a425b3ca166c3de1726633b06193b2569dba34cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387039"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-crashing"></a>如何捕获 Crashing 的进程的内存转储
BizTalk 进程 BTSNTSvc.exe 被定义为**崩溃**时的进程意外终止的 Windows。 崩溃通常会出现访问冲突或堆栈溢出等过程中未处理的异常。 在这些情况下，Windows 默认调试器，灾难恢复。Watson (drwtsn32.exe) 捕获异常并终止进程。  
  
 若要捕获崩溃进程的内存转储，配置调试诊断工具来捕获未经处理的异常，通过执行以下步骤：  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-crash-dump"></a>若要配置调试诊断工具，用于捕获故障转储  
  
1.  启动调试诊断工具**启动**，**所有程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。  
  
2.  如果**选择规则类型**未显示添加规则向导对话框中，单击**工具**菜单中，选择**规则操作**，然后单击**添加规则**以显示添加规则向导。  
  
3.  选择**崩溃**选项**选择规则类型**对话框，然后单击**下一步**。  
  
4.  选择**特定的进程**中**选择目标类型**对话框，然后单击**下一步**。  
  
5.  选择的 BTSNTSvc.exe 进程中发生故障，然后单击**下一步**。  
  
6.  在中**高级配置**对话框中，单击**下一步**以接受默认值。  
  
7.  在中**选择转储位置和规则名称**对话框中，单击**下一步**以接受默认值。  
  
8.  在中**已完成规则**对话框中，单击**完成**若要接受默认值**立即激活规则**。  
  
9. 默认情况下，进程的内存转储将保存到 \Program Files\IIS Resources\DebugDiag\Logs\\<*崩溃规则的名称*\>目录下的本地计算机的时间在进程中发生未经处理的异常。  
  
## <a name="see-also"></a>请参阅  
 [如何使用调试诊断分析内存转储](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)