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
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a><span data-ttu-id="4b685-102">如何捕获泄漏内存的进程的内存转储</span><span class="sxs-lookup"><span data-stu-id="4b685-102">How to Capture a Memory Dump of a Process that is Leaking Memory</span></span>
<span data-ttu-id="4b685-103">随着时间的推移，BizTalk 进程 BTSNTSvc.exe 被定义为具有内存泄漏时无法释放内存，它不再需要从而减少可用内存量。</span><span class="sxs-lookup"><span data-stu-id="4b685-103">The BizTalk process BTSNTSvc.exe is defined as having a memory leak when it fails to release memory that it no longer needs, thereby reducing the amount of available memory over time.</span></span> <span data-ttu-id="4b685-104">可通过查看下的值来确定进程的内存使用率**Mem Usage**的列**进程**选项卡可找到**任务管理器**。</span><span class="sxs-lookup"><span data-stu-id="4b685-104">The memory usage of the process can be determined by viewing the value under the **Mem Usage** column of the **Processes** tab available in **Task Manager**.</span></span> <span data-ttu-id="4b685-105">如果进程继续随时间消耗内存而不释放内存然后总体系统性能将受到负面影响。</span><span class="sxs-lookup"><span data-stu-id="4b685-105">If the process continues to consume memory over time without releasing memory then overall system performance will be adversely impacted.</span></span>  
  
 <span data-ttu-id="4b685-106">本主题包含用于捕获可能泄漏内存，通过使用规则或通过手动捕获内存转储的 BizTalk 进程的内存转储的说明。</span><span class="sxs-lookup"><span data-stu-id="4b685-106">This topic contains instructions for capturing a memory dump of a BizTalk process that is suspected of leaking memory by using a Rule or by manually capturing the memory dump.</span></span> <span data-ttu-id="4b685-107">使用手动方法来捕获内存转储，如果内存泄漏的匹配项不是可预测。</span><span class="sxs-lookup"><span data-stu-id="4b685-107">Use the manual method of capturing a memory dump if the occurrence of the memory leak is not predictable.</span></span>  
  
### <a name="to-capture-a-memory-dump-of-a-process-that-is-leaking-memory-by-using-a-rule"></a><span data-ttu-id="4b685-108">若要捕获通过使用规则正在泄漏内存的进程的内存转储</span><span class="sxs-lookup"><span data-stu-id="4b685-108">To capture a memory dump of a process that is leaking memory by using a rule</span></span>  
  
1.  <span data-ttu-id="4b685-109">启动调试诊断工具**启动**，**所有程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。</span><span class="sxs-lookup"><span data-stu-id="4b685-109">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="4b685-110">如果**选择规则类型**未显示添加规则向导对话框中，单击**工具**菜单中，选择**规则操作**，然后单击**添加规则**以显示添加规则向导。</span><span class="sxs-lookup"><span data-stu-id="4b685-110">If the **Select Rule Type** dialog of the Add Rule Wizard is not displayed, click the **Tools** menu, select **Rule Actions**, and click **Add Rule** to display the Add Rule Wizard.</span></span>  
  
3.  <span data-ttu-id="4b685-111">选择**内存和处理泄漏**选项**选择规则类型**对话框，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4b685-111">Select the **Memory and Handle Leak** option in the **Select Rule Type** dialog and click **Next**.</span></span>  
  
4.  <span data-ttu-id="4b685-112">选择怀疑泄漏内存，然后单击的 BTSNTSvc.exe 进程**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4b685-112">Select the BTSNTSvc.exe process that is suspected of leaking memory and click **Next**.</span></span>  
  
5.  <span data-ttu-id="4b685-113">在中**配置跟踪持续时间**对话框，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4b685-113">In the **Configure Tracking Duration** dialog follow these steps:</span></span>  
  
    1.  <span data-ttu-id="4b685-114">如果观察到的进程内存增长会立即发生，选中选项**启动内存跟踪立即激活规则是**。</span><span class="sxs-lookup"><span data-stu-id="4b685-114">If the observed process memory growth occurs immediately, check the option to **Start memory tracking immediately when rule is activated**.</span></span> <span data-ttu-id="4b685-115">如果观察到的进程内存增长不会立即发生，指定相应的分钟数**预热时间**启动内存跟踪将在其后的文本框。</span><span class="sxs-lookup"><span data-stu-id="4b685-115">If the observed process memory growth doesn't occur immediately, specify an appropriate number of minutes in the **Warm-up time** text box after which memory tracking will start.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="4b685-116">如果某个组件加载到内存中，例如在 BizTalk 业务流程引用外部组件时，会出现内存泄漏，观察到的进程内存增长可能不会立即发生。</span><span class="sxs-lookup"><span data-stu-id="4b685-116">The observed process memory growth may not occur immediately if the memory leak is caused when loading a particular component into memory, for example when a BizTalk orchestration references an external component.</span></span>  
  
    2.  <span data-ttu-id="4b685-117">指定相应的分钟数**跟踪时间**之后停止内存跟踪之前的文本框。</span><span class="sxs-lookup"><span data-stu-id="4b685-117">Specify an appropriate number of minutes in the **Tracking time** text box after which memory tracking will stop.</span></span> <span data-ttu-id="4b685-118">这应该是分钟数足够长，以再现内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="4b685-118">This should be a number of minutes long enough to reproduce the memory leak.</span></span> <span data-ttu-id="4b685-119">经过此时间段后，将捕获进程的内存转储。</span><span class="sxs-lookup"><span data-stu-id="4b685-119">A memory dump of the process will be captured after this time period has elapsed.</span></span>  
  
    3.  <span data-ttu-id="4b685-120">选中选项**自动创建一个崩溃的规则以获取意外的进程退出的用户转储**。</span><span class="sxs-lookup"><span data-stu-id="4b685-120">Check the option to **Auto-create a crash rule to get userdump on unexpected process exit**.</span></span>  
  
    4.  <span data-ttu-id="4b685-121">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="4b685-121">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="4b685-122">在中**选择转储位置和规则名称**对话框中，单击**下一步**以接受默认值。</span><span class="sxs-lookup"><span data-stu-id="4b685-122">In the **Select Dump Location And Rule Name** dialog click **Next** to accept the default values.</span></span>  
  
7.  <span data-ttu-id="4b685-123">在中**已完成规则**对话框中，单击**完成**若要接受默认值**立即激活规则**。</span><span class="sxs-lookup"><span data-stu-id="4b685-123">In the **Rule Completed** dialog click **Finish** to accept the default value of **Activate the rule now**.</span></span>  
  
8.  <span data-ttu-id="4b685-124">默认情况下，进程的内存转储将保存到 \Program Files\IIS Resources\DebugDiag\Logs\\<*崩溃规则的名称*\>目录的时间间隔后在本地计算机中指定**配置跟踪持续时间**对话框已过。</span><span class="sxs-lookup"><span data-stu-id="4b685-124">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\\<*name of crash rule*\> directory of the local computer after the time intervals specified in the **Configure Tracking Duration** dialog has elapsed.</span></span>  
  
### <a name="to-manually-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a><span data-ttu-id="4b685-125">若要手动捕获泄漏内存的进程的内存转储</span><span class="sxs-lookup"><span data-stu-id="4b685-125">To manually capture a memory dump of a process that is leaking memory</span></span>  
  
1.  <span data-ttu-id="4b685-126">启动调试诊断工具**启动**，**所有程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。</span><span class="sxs-lookup"><span data-stu-id="4b685-126">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="4b685-127">如果**选择规则类型**将显示添加规则向导对话框中，单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="4b685-127">If the **Select Rule Type** dialog of the Add Rule Wizard is displayed, click **Cancel**.</span></span>  
  
3.  <span data-ttu-id="4b685-128">单击此项可选择**进程**调试诊断工具的选项卡。</span><span class="sxs-lookup"><span data-stu-id="4b685-128">Click to select the **Processes** tab of the Debug Diagnostic Tool.</span></span>  
  
4.  <span data-ttu-id="4b685-129">右键单击怀疑泄漏内存，然后单击的 BTSNTSvc.exe 进程**监视泄漏**。</span><span class="sxs-lookup"><span data-stu-id="4b685-129">Right-click the BTSNTSvc.exe process that is suspected of leaking memory and click **Monitor For Leaks**.</span></span>  
  
5.  <span data-ttu-id="4b685-130">监视中的进程的内存使用情况**任务管理器**和进程的内存使用率接近 BizTalk 计算机上的可用内存的 60-80%时手动捕获进程的内存转储，请右键单击进程并选择选项**创建完全用户转储**。</span><span class="sxs-lookup"><span data-stu-id="4b685-130">Monitor the memory usage of the process in **Task Manager** and when the memory usage of the process approaches 60-80% of the memory available on the BizTalk computer; manually capture a memory dump of the process by right-clicking the process and selecting the option to **Create Full Userdump**.</span></span>  
  
6.  <span data-ttu-id="4b685-131">默认情况下，进程的内存转储将保存到本地计算机的 \Program Files\IIS Resources\DebugDiag\Logs\Misc\ 目录。</span><span class="sxs-lookup"><span data-stu-id="4b685-131">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\Misc\ directory of the local computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b685-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b685-132">See Also</span></span>  
 [<span data-ttu-id="4b685-133">如何使用调试诊断分析内存转储</span><span class="sxs-lookup"><span data-stu-id="4b685-133">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)