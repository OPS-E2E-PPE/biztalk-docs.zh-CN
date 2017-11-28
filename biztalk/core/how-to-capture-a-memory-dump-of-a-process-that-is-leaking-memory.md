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
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a><span data-ttu-id="6565d-102">如何捕获泄露内存的进程内存转储</span><span class="sxs-lookup"><span data-stu-id="6565d-102">How to Capture a Memory Dump of a Process that is Leaking Memory</span></span>
<span data-ttu-id="6565d-103">如果 BizTalk 进程 BTSNTSvc.exe 无法释放不再需要的内存，因此会随着时间减少可用内存量，则定义为内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="6565d-103">The BizTalk process BTSNTSvc.exe is defined as having a memory leak when it fails to release memory that it no longer needs, thereby reducing the amount of available memory over time.</span></span> <span data-ttu-id="6565d-104">可以查看下的值来确定进程的内存使用率**内存使用**列**进程**选项卡中可找到**任务管理器**。</span><span class="sxs-lookup"><span data-stu-id="6565d-104">The memory usage of the process can be determined by viewing the value under the **Mem Usage** column of the **Processes** tab available in **Task Manager**.</span></span> <span data-ttu-id="6565d-105">如果进程继续随时间消耗内存而不释放内存，系统的整体性能将受到不良影响。</span><span class="sxs-lookup"><span data-stu-id="6565d-105">If the process continues to consume memory over time without releasing memory then overall system performance will be adversely impacted.</span></span>  
  
 <span data-ttu-id="6565d-106">本主题提供了通过使用规则或手动捕获内存转储来捕获被怀疑泄漏内存的 BizTalk 进程的内存转储的说明。</span><span class="sxs-lookup"><span data-stu-id="6565d-106">This topic contains instructions for capturing a memory dump of a BizTalk process that is suspected of leaking memory by using a Rule or by manually capturing the memory dump.</span></span> <span data-ttu-id="6565d-107">如果内存泄漏不是可预测的，则使用手动方法来捕获内存转储。</span><span class="sxs-lookup"><span data-stu-id="6565d-107">Use the manual method of capturing a memory dump if the occurrence of the memory leak is not predictable.</span></span>  
  
### <a name="to-capture-a-memory-dump-of-a-process-that-is-leaking-memory-by-using-a-rule"></a><span data-ttu-id="6565d-108">通过使用规则捕获泄漏内存的进程的内存转储</span><span class="sxs-lookup"><span data-stu-id="6565d-108">To capture a memory dump of a process that is leaking memory by using a rule</span></span>  
  
1.  <span data-ttu-id="6565d-109">启动调试诊断工具从**启动**，**所有程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。</span><span class="sxs-lookup"><span data-stu-id="6565d-109">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="6565d-110">如果**选择规则类型**未显示添加规则向导对话框，单击**工具**菜单上，选择**规则操作**，然后单击**添加规则**以显示添加规则向导。</span><span class="sxs-lookup"><span data-stu-id="6565d-110">If the **Select Rule Type** dialog of the Add Rule Wizard is not displayed, click the **Tools** menu, select **Rule Actions**, and click **Add Rule** to display the Add Rule Wizard.</span></span>  
  
3.  <span data-ttu-id="6565d-111">选择**内存和处理泄漏**选项**选择规则类型**对话框，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6565d-111">Select the **Memory and Handle Leak** option in the **Select Rule Type** dialog and click **Next**.</span></span>  
  
4.  <span data-ttu-id="6565d-112">选择 BTSNTSvc.exe 进程怀疑泄露内存和单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6565d-112">Select the BTSNTSvc.exe process that is suspected of leaking memory and click **Next**.</span></span>  
  
5.  <span data-ttu-id="6565d-113">在**配置跟踪的持续时间**对话框请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="6565d-113">In the **Configure Tracking Duration** dialog follow these steps:</span></span>  
  
    1.  <span data-ttu-id="6565d-114">如果观察到的进程内存增长会立即发生，请检查选项**启动跟踪立即激活规则时的内存**。</span><span class="sxs-lookup"><span data-stu-id="6565d-114">If the observed process memory growth occurs immediately, check the option to **Start memory tracking immediately when rule is activated**.</span></span> <span data-ttu-id="6565d-115">如果观察到的进程内存增长不会立即发生，指定适当数量的分钟**预热时间**后将启动内存跟踪的文本框。</span><span class="sxs-lookup"><span data-stu-id="6565d-115">If the observed process memory growth doesn't occur immediately, specify an appropriate number of minutes in the **Warm-up time** text box after which memory tracking will start.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="6565d-116">如果在将某个组件加载到内存时导致内存泄漏，可能不会立即出现能观察到的进程内存增长，例如，在 BizTalk 业务流程引用外部组件时。</span><span class="sxs-lookup"><span data-stu-id="6565d-116">The observed process memory growth may not occur immediately if the memory leak is caused when loading a particular component into memory, for example when a BizTalk orchestration references an external component.</span></span>  
  
    2.  <span data-ttu-id="6565d-117">指定适当数量的分钟**跟踪时间**内存跟踪将停止在其后的文本框。</span><span class="sxs-lookup"><span data-stu-id="6565d-117">Specify an appropriate number of minutes in the **Tracking time** text box after which memory tracking will stop.</span></span> <span data-ttu-id="6565d-118">这应该是一个足够长的分钟数，以再现内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="6565d-118">This should be a number of minutes long enough to reproduce the memory leak.</span></span> <span data-ttu-id="6565d-119">进程的内存转储将在此时间段之后被捕获。</span><span class="sxs-lookup"><span data-stu-id="6565d-119">A memory dump of the process will be captured after this time period has elapsed.</span></span>  
  
    3.  <span data-ttu-id="6565d-120">检查选项**的崩溃自动创建规则以在进程意外的退出获取用户转储**。</span><span class="sxs-lookup"><span data-stu-id="6565d-120">Check the option to **Auto-create a crash rule to get userdump on unexpected process exit**.</span></span>  
  
    4.  <span data-ttu-id="6565d-121">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="6565d-121">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="6565d-122">在**选择转储位置和规则名称**对话框中，单击**下一步**以接受默认值。</span><span class="sxs-lookup"><span data-stu-id="6565d-122">In the **Select Dump Location And Rule Name** dialog click **Next** to accept the default values.</span></span>  
  
7.  <span data-ttu-id="6565d-123">在**规则完成**对话框中，单击**完成**以接受默认值的**立即激活规则**。</span><span class="sxs-lookup"><span data-stu-id="6565d-123">In the **Rule Completed** dialog click **Finish** to accept the default value of **Activate the rule now**.</span></span>  
  
8.  <span data-ttu-id="6565d-124">默认情况下，进程的内存转储将保存到 \Program Files\IIS Resources\DebugDiag\Logs\\<*崩溃规则的名称*> 目录中指定的时间段后的本地计算机**配置跟踪的持续时间**对话框已过。</span><span class="sxs-lookup"><span data-stu-id="6565d-124">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\\<*name of crash rule*> directory of the local computer after the time intervals specified in the **Configure Tracking Duration** dialog has elapsed.</span></span>  
  
### <a name="to-manually-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a><span data-ttu-id="6565d-125">手动捕获泄漏内存的进程的内存转储</span><span class="sxs-lookup"><span data-stu-id="6565d-125">To manually capture a memory dump of a process that is leaking memory</span></span>  
  
1.  <span data-ttu-id="6565d-126">启动调试诊断工具从**启动**，**所有程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。</span><span class="sxs-lookup"><span data-stu-id="6565d-126">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="6565d-127">如果**选择规则类型**显示的添加规则向导对话框，请单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="6565d-127">If the **Select Rule Type** dialog of the Add Rule Wizard is displayed, click **Cancel**.</span></span>  
  
3.  <span data-ttu-id="6565d-128">单击以选择**进程**选项卡的调试诊断工具。</span><span class="sxs-lookup"><span data-stu-id="6565d-128">Click to select the **Processes** tab of the Debug Diagnostic Tool.</span></span>  
  
4.  <span data-ttu-id="6565d-129">右键单击 BTSNTSvc.exe 流程怀疑泄露内存和单击**监控泄漏**。</span><span class="sxs-lookup"><span data-stu-id="6565d-129">Right-click the BTSNTSvc.exe process that is suspected of leaking memory and click **Monitor For Leaks**.</span></span>  
  
5.  <span data-ttu-id="6565d-130">监视在进程的内存使用率**任务管理器**和进程的内存使用率接近 BizTalk 计算机; 上的可用内存的 60-80%时手动捕获进程的内存转储，请右键单击过程并选择选项**创建完整用户转储**。</span><span class="sxs-lookup"><span data-stu-id="6565d-130">Monitor the memory usage of the process in **Task Manager** and when the memory usage of the process approaches 60-80% of the memory available on the BizTalk computer; manually capture a memory dump of the process by right-clicking the process and selecting the option to **Create Full Userdump**.</span></span>  
  
6.  <span data-ttu-id="6565d-131">默认情况下，进程的内存转储将保存到本地计算机的 \Program Files\IIS Resources\DebugDiag\Logs\Misc\ 目录中。</span><span class="sxs-lookup"><span data-stu-id="6565d-131">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\Misc\ directory of the local computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6565d-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6565d-132">See Also</span></span>  
 [<span data-ttu-id="6565d-133">如何使用调试诊断分析内存转储</span><span class="sxs-lookup"><span data-stu-id="6565d-133">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)