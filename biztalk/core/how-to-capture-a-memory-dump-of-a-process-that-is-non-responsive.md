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
ms.openlocfilehash: ea2310f38c221147efdba5b1e2980a548fabfa86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387047"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive"></a><span data-ttu-id="bd903-102">如何捕获的非响应进程的内存转储</span><span class="sxs-lookup"><span data-stu-id="bd903-102">How to Capture a Memory Dump of a Process that is Non Responsive</span></span>
<span data-ttu-id="bd903-103">BizTalk 进程 BTSNTSvc.exe 被定义为**悬挂**过程似乎停止响应。</span><span class="sxs-lookup"><span data-stu-id="bd903-103">The BizTalk process BTSNTSvc.exe is defined as **hanging** when the process seems to stop responding.</span></span> <span data-ttu-id="bd903-104">挂起进程的常见情况包括：</span><span class="sxs-lookup"><span data-stu-id="bd903-104">Common symptoms of a process hang include:</span></span>  
  
- <span data-ttu-id="bd903-105">业务流程似乎要停止运行。</span><span class="sxs-lookup"><span data-stu-id="bd903-105">Orchestrations appear to stop running.</span></span>  
  
- <span data-ttu-id="bd903-106">未处理消息。</span><span class="sxs-lookup"><span data-stu-id="bd903-106">Messages aren’t being processed.</span></span>  
  
- <span data-ttu-id="bd903-107">发生常规超时问题。</span><span class="sxs-lookup"><span data-stu-id="bd903-107">General timeout issues occur.</span></span>  
  
- <span data-ttu-id="bd903-108">BizTalk 进程 BTSNTSvc.exe 消耗异常高的 CPU 周期中查看**进程**选项卡**任务管理器**。</span><span class="sxs-lookup"><span data-stu-id="bd903-108">The BizTalk process BTSNTSvc.exe consumes an unusually high amount of CPU cycles as viewed in the **Processes** tab of **Task Manager**.</span></span>  
  
  <span data-ttu-id="bd903-109">若要捕获内存转储的挂起的 BTSNTSvc.exe 进程，请按照这些步骤。</span><span class="sxs-lookup"><span data-stu-id="bd903-109">To capture a memory dump of a hanging BTSNTSvc.exe process, follow these steps.</span></span>  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-hang-dump"></a><span data-ttu-id="bd903-110">若要配置调试诊断工具，用于捕获挂起转储</span><span class="sxs-lookup"><span data-stu-id="bd903-110">To configure the Debug Diagnostics tool to capture a hang dump</span></span>  
  
1.  <span data-ttu-id="bd903-111">启动调试诊断工具**启动**，**所有程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。</span><span class="sxs-lookup"><span data-stu-id="bd903-111">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="bd903-112">如果**选择规则类型**显示的规则配置向导的对话框中，单击**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="bd903-112">If the **Select Rule Type** dialog of the Rules Configuration Wizard is displayed, click the **Cancel** button.</span></span>  
  
3.  <span data-ttu-id="bd903-113">单击**进程**调试诊断工具的选项卡。</span><span class="sxs-lookup"><span data-stu-id="bd903-113">Click the **Processes** tab of the Debug Diagnostic Tool.</span></span>  
  
4.  <span data-ttu-id="bd903-114">右键单击无响应的 BTSNTSvc.exe 进程，然后选择**创建完全用户转储**。</span><span class="sxs-lookup"><span data-stu-id="bd903-114">Right click the unresponsive BTSNTSvc.exe process and select **Create Full Userdump**.</span></span> <span data-ttu-id="bd903-115">默认情况下，进程的内存转储将保存到本地计算机的 \Program Files\IIS Resources\DebugDiag\Logs\Misc 目录。</span><span class="sxs-lookup"><span data-stu-id="bd903-115">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\Misc directory of the local computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd903-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd903-116">See Also</span></span>  
 [<span data-ttu-id="bd903-117">如何使用调试诊断分析内存转储</span><span class="sxs-lookup"><span data-stu-id="bd903-117">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)