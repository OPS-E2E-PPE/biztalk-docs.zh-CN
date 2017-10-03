---
title: "如何捕获 BizTalk 进程的内存转储 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8053fcf3-b331-4245-b3c3-21290463e0c0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f87ad0f4a3eb3a49ea789d45a707bbc8b46cb4c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-capture-a-memory-dump-of-a-biztalk-process"></a><span data-ttu-id="e7626-102">如何捕获 BizTalk 进程的内存转储</span><span class="sxs-lookup"><span data-stu-id="e7626-102">How to Capture a Memory Dump of a BizTalk Process</span></span>
<span data-ttu-id="e7626-103">在某些情况下，可能需要捕获 BizTalk Server 上运行的进程的内存转储，以对该进程执行深入分析。</span><span class="sxs-lookup"><span data-stu-id="e7626-103">Under certain circumstances it may be necessary to capture a memory dump of a process running on a BizTalk Server to perform an in depth analysis of the process.</span></span> <span data-ttu-id="e7626-104">在以下情况下可能需要对内存转储进行分析：</span><span class="sxs-lookup"><span data-stu-id="e7626-104">Situations that may require analysis of a memory dump include the following:</span></span>  
  
-   <span data-ttu-id="e7626-105">在进程无响应时。</span><span class="sxs-lookup"><span data-stu-id="e7626-105">When a process is unresponsive.</span></span>  
  
-   <span data-ttu-id="e7626-106">在进程崩溃时。</span><span class="sxs-lookup"><span data-stu-id="e7626-106">When a process is crashing.</span></span>  
  
-   <span data-ttu-id="e7626-107">在进程泄漏内存时。</span><span class="sxs-lookup"><span data-stu-id="e7626-107">When a process leaks memory.</span></span>  
  
 <span data-ttu-id="e7626-108">本部分介绍捕获适当类型的内存转储时应遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="e7626-108">This section includes the steps that should be followed to capture the appropriate type of memory dump.</span></span>  
  
## <a name="installation-of-the-iis-diagnostics-toolkit"></a><span data-ttu-id="e7626-109">安装 IIS 诊断工具包</span><span class="sxs-lookup"><span data-stu-id="e7626-109">Installation of the IIS Diagnostics Toolkit</span></span>  
 <span data-ttu-id="e7626-110">此部分中的主题的每个需要使用**调试诊断工具**IIS 诊断工具包，若要捕获内存转储。</span><span class="sxs-lookup"><span data-stu-id="e7626-110">Each of the topics in this section requires the use of the **Debug Diagnostics Tool** of the IIS Diagnostics Toolkit to capture a memory dump.</span></span> <span data-ttu-id="e7626-111">若要安装**调试诊断工具**的 IIS 诊断工具包，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="e7626-111">To install the **Debug Diagnostics Tool** of the IIS Diagnostics Toolkit follow these steps:</span></span>  
  
1.  <span data-ttu-id="e7626-112">下载 IIS 诊断工具包从[Internet 信息服务诊断工具](http://go.microsoft.com/fwlink/?LinkId=64426)。</span><span class="sxs-lookup"><span data-stu-id="e7626-112">Download the IIS Diagnostics Toolkit from [Internet Information Services Diagnostic Tools](http://go.microsoft.com/fwlink/?LinkId=64426).</span></span>  
  
2.  <span data-ttu-id="e7626-113">双击**iisdiag.msi**要启动 IIS 诊断工具包安装程序并选择包**自定义**安装类型。</span><span class="sxs-lookup"><span data-stu-id="e7626-113">Double-click the **iisdiag.msi** package to start the IIS Diagnostics Toolkit setup program and choose the **Custom** setup type.</span></span>  
  
3.  <span data-ttu-id="e7626-114">在**自定义安装**对话框中，确保的选项**调试诊断工具 1.0**已启用并完成安装程序中的步骤。</span><span class="sxs-lookup"><span data-stu-id="e7626-114">In the **Custom Setup** dialog, ensure that the option for the **Debug Diagnostics Tool 1.0** is enabled and complete the steps in the setup program.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e7626-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="e7626-115">In This Section</span></span>  
  
-   [<span data-ttu-id="e7626-116">如何捕获非响应的进程内存转储</span><span class="sxs-lookup"><span data-stu-id="e7626-116">How to Capture a Memory Dump of a Process that is Non Responsive</span></span>](../core/how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive.md)  
  
-   [<span data-ttu-id="e7626-117">如何捕获所 Crashing 进程内存转储</span><span class="sxs-lookup"><span data-stu-id="e7626-117">How to Capture a Memory Dump of a Process that is Crashing</span></span>](../core/how-to-capture-a-memory-dump-of-a-process-that-is-crashing.md)  
  
-   [<span data-ttu-id="e7626-118">如何捕获泄露内存的进程内存转储</span><span class="sxs-lookup"><span data-stu-id="e7626-118">How to Capture a Memory Dump of a Process that is Leaking Memory</span></span>](../core/how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory.md)  
  
-   [<span data-ttu-id="e7626-119">如何使用调试诊断分析内存转储</span><span class="sxs-lookup"><span data-stu-id="e7626-119">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)