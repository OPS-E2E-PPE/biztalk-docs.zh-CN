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
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-crashing"></a><span data-ttu-id="26d3a-102">如何捕获 Crashing 的进程的内存转储</span><span class="sxs-lookup"><span data-stu-id="26d3a-102">How to Capture a Memory Dump of a Process that is Crashing</span></span>
<span data-ttu-id="26d3a-103">BizTalk 进程 BTSNTSvc.exe 被定义为**崩溃**时的进程意外终止的 Windows。</span><span class="sxs-lookup"><span data-stu-id="26d3a-103">The BizTalk process BTSNTSvc.exe is defined as **crashing** when the process is unexpectedly terminated by Windows.</span></span> <span data-ttu-id="26d3a-104">崩溃通常会出现访问冲突或堆栈溢出等过程中未处理的异常。</span><span class="sxs-lookup"><span data-stu-id="26d3a-104">A crash is typically caused by an unhandled exception in the process such as an access violation or a stack overflow.</span></span> <span data-ttu-id="26d3a-105">在这些情况下，Windows 默认调试器，灾难恢复。Watson (drwtsn32.exe) 捕获异常并终止进程。</span><span class="sxs-lookup"><span data-stu-id="26d3a-105">In these situations, the Windows default debugger, Dr. Watson (drwtsn32.exe) catches the exception and terminates the process.</span></span>  
  
 <span data-ttu-id="26d3a-106">若要捕获崩溃进程的内存转储，配置调试诊断工具来捕获未经处理的异常，通过执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="26d3a-106">To capture a memory dump of a process that is crashing, configure the Debug Diagnostics tool to catch the unhandled exception by following these steps:</span></span>  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-crash-dump"></a><span data-ttu-id="26d3a-107">若要配置调试诊断工具，用于捕获故障转储</span><span class="sxs-lookup"><span data-stu-id="26d3a-107">To configure the Debug Diagnostics tool to capture a crash dump</span></span>  
  
1.  <span data-ttu-id="26d3a-108">启动调试诊断工具**启动**，**所有程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。</span><span class="sxs-lookup"><span data-stu-id="26d3a-108">Launch the Debug Diagnostics tool from **Start**, **All Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="26d3a-109">如果**选择规则类型**未显示添加规则向导对话框中，单击**工具**菜单中，选择**规则操作**，然后单击**添加规则**以显示添加规则向导。</span><span class="sxs-lookup"><span data-stu-id="26d3a-109">If the **Select Rule Type** dialog of the Add Rule Wizard is not displayed, click the **Tools** menu, select **Rule Actions**, and click **Add Rule** to display the Add Rule Wizard.</span></span>  
  
3.  <span data-ttu-id="26d3a-110">选择**崩溃**选项**选择规则类型**对话框，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="26d3a-110">Select the **Crash** option in the **Select Rule Type** dialog and click **Next**.</span></span>  
  
4.  <span data-ttu-id="26d3a-111">选择**特定的进程**中**选择目标类型**对话框，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="26d3a-111">Select **A specific process** in the **Select Target Type** dialog and click **Next**.</span></span>  
  
5.  <span data-ttu-id="26d3a-112">选择的 BTSNTSvc.exe 进程中发生故障，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="26d3a-112">Select the BTSNTSvc.exe process that is crashing and click **Next**.</span></span>  
  
6.  <span data-ttu-id="26d3a-113">在中**高级配置**对话框中，单击**下一步**以接受默认值。</span><span class="sxs-lookup"><span data-stu-id="26d3a-113">In the **Advanced Configuration** dialog click **Next** to accept the default values.</span></span>  
  
7.  <span data-ttu-id="26d3a-114">在中**选择转储位置和规则名称**对话框中，单击**下一步**以接受默认值。</span><span class="sxs-lookup"><span data-stu-id="26d3a-114">In the **Select Dump Location And Rule Name** dialog click **Next** to accept the default values.</span></span>  
  
8.  <span data-ttu-id="26d3a-115">在中**已完成规则**对话框中，单击**完成**若要接受默认值**立即激活规则**。</span><span class="sxs-lookup"><span data-stu-id="26d3a-115">In the **Rule Completed** dialog click **Finish** to accept the default value of **Activate the rule now**.</span></span>  
  
9. <span data-ttu-id="26d3a-116">默认情况下，进程的内存转储将保存到 \Program Files\IIS Resources\DebugDiag\Logs\\<*崩溃规则的名称*\>目录下的本地计算机的时间在进程中发生未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="26d3a-116">By default, a memory dump of the process will be saved to the \Program Files\IIS Resources\DebugDiag\Logs\\<*name of crash rule*\> directory of the local computer the next time that an unhandled exception occurs in the process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26d3a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="26d3a-117">See Also</span></span>  
 [<span data-ttu-id="26d3a-118">如何使用调试诊断分析内存转储</span><span class="sxs-lookup"><span data-stu-id="26d3a-118">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)