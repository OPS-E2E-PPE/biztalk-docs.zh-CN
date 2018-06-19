---
title: 如何捕获非响应的进程内存转储 |Microsoft 文档
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
ms.openlocfilehash: 520921010a8bbfd73de8c3b305a1270ca8363c46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248581"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive"></a><span data-ttu-id="66b7a-102">如何捕获非响应的进程内存转储</span><span class="sxs-lookup"><span data-stu-id="66b7a-102">How to Capture a Memory Dump of a Process that is Non Responsive</span></span>
<span data-ttu-id="66b7a-103">BTSNTSvc.exe 定义为 BizTalk 进程**悬挂**进程似乎停止响应。</span><span class="sxs-lookup"><span data-stu-id="66b7a-103">The BizTalk process BTSNTSvc.exe is defined as **hanging** when the process seems to stop responding.</span></span> <span data-ttu-id="66b7a-104">挂起进程的常见情况包括：</span><span class="sxs-lookup"><span data-stu-id="66b7a-104">Common symptoms of a process hang include:</span></span>  
  
-   <span data-ttu-id="66b7a-105">业务流程似乎要停止运行。</span><span class="sxs-lookup"><span data-stu-id="66b7a-105">Orchestrations appear to stop running.</span></span>  
  
-   <span data-ttu-id="66b7a-106">消息未处理。</span><span class="sxs-lookup"><span data-stu-id="66b7a-106">Messages aren’t being processed.</span></span>  
  
-   <span data-ttu-id="66b7a-107">发生常规超时问题。</span><span class="sxs-lookup"><span data-stu-id="66b7a-107">General timeout issues occur.</span></span>  
  
-   <span data-ttu-id="66b7a-108">BizTalk 进程 BTSNTSvc.exe 占用了 CPU 周期在中所查看的异常高量**进程**选项卡**任务管理器**。</span><span class="sxs-lookup"><span data-stu-id="66b7a-108">The BizTalk process BTSNTSvc.exe consumes an unusually high amount of CPU cycles as viewed in the **Processes** tab of **Task Manager**.</span></span>  
  
 <span data-ttu-id="66b7a-109">若要捕获挂起的 BTSNTSvc.exe 进程的内存转储，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="66b7a-109">To capture a memory dump of a hanging BTSNTSvc.exe process, follow these steps.</span></span>  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-hang-dump"></a><span data-ttu-id="66b7a-110">配置调试诊断工具以捕获挂起转储</span><span class="sxs-lookup"><span data-stu-id="66b7a-110">To configure the Debug Diagnostics tool to capture a hang dump</span></span>  
  
1.  <span data-ttu-id="66b7a-111">启动调试诊断工具从**启动**，**所有程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。</span><span class="sxs-lookup"><span data-stu-id="66b7a-111">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="66b7a-112">如果**选择规则类型**显示的规则配置向导的对话框中，单击**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="66b7a-112">If the **Select Rule Type** dialog of the Rules Configuration Wizard is displayed, click the **Cancel** button.</span></span>  
  
3.  <span data-ttu-id="66b7a-113">单击**进程**选项卡的调试诊断工具。</span><span class="sxs-lookup"><span data-stu-id="66b7a-113">Click the **Processes** tab of the Debug Diagnostic Tool.</span></span>  
  
4.  <span data-ttu-id="66b7a-114">右键单击无响应的 BTSNTSvc.exe 进程，然后选择**创建完整用户转储**。</span><span class="sxs-lookup"><span data-stu-id="66b7a-114">Right click the unresponsive BTSNTSvc.exe process and select **Create Full Userdump**.</span></span> <span data-ttu-id="66b7a-115">默认情况下，进程的内存转储将保存到本地计算机的 \Program Files\IIS Resources\DebugDiag\Logs\Misc 目录中。</span><span class="sxs-lookup"><span data-stu-id="66b7a-115">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\Misc directory of the local computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66b7a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66b7a-116">See Also</span></span>  
 [<span data-ttu-id="66b7a-117">如何使用调试诊断分析内存转储</span><span class="sxs-lookup"><span data-stu-id="66b7a-117">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)