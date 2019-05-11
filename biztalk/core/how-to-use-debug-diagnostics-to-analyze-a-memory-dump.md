---
title: 如何使用调试诊断分析内存转储 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 986a91a7-feab-4014-bbd5-e8b966b8b841
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47b8818979a9d278323d97dae2d1436c1d169829
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383412"
---
# <a name="how-to-use-debug-diagnostics-to-analyze-a-memory-dump"></a><span data-ttu-id="efd5a-102">如何使用调试诊断分析内存转储</span><span class="sxs-lookup"><span data-stu-id="efd5a-102">How to Use Debug Diagnostics to Analyze a Memory Dump</span></span>
<span data-ttu-id="efd5a-103">IIS 诊断**调试诊断工具**包含一个功能，可以提供捕获的内存转储文件的基本分析。</span><span class="sxs-lookup"><span data-stu-id="efd5a-103">The IIS Diagnostics **Debug Diagnostics Tool** includes a feature that can provide a basic analysis of a captured memory dump file.</span></span> <span data-ttu-id="efd5a-104">若要执行的内存转储文件分析，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="efd5a-104">To perform an analysis of a memory dump file follow these steps.</span></span>  
  
### <a name="to-analyze-the-dump-file"></a><span data-ttu-id="efd5a-105">若要分析转储文件</span><span class="sxs-lookup"><span data-stu-id="efd5a-105">To analyze the dump file</span></span>  
  
1.  <span data-ttu-id="efd5a-106">启动调试诊断工具**启动**，**程序**， **IIS 诊断**，**调试诊断工具**， **调试诊断工具 1.0**。</span><span class="sxs-lookup"><span data-stu-id="efd5a-106">Launch the Debug Diagnostics tool from **Start**, **Programs**, **IIS Diagnostics**, **Debug Diagnostics Tools**, **Debug Diagnostics Tool 1.0**.</span></span>  
  
2.  <span data-ttu-id="efd5a-107">单击**高级分析**选项卡。</span><span class="sxs-lookup"><span data-stu-id="efd5a-107">Click the **Advanced Analysis** tab.</span></span>  
  
3.  <span data-ttu-id="efd5a-108">下**可用分析脚本**单击此项可选择**崩溃/挂起分析器**以分析崩溃/挂起转储，或单击以选中**内存压力分析**分析内存怀疑泄漏内存的进程转储。</span><span class="sxs-lookup"><span data-stu-id="efd5a-108">Under **Available Analysis Scripts** click to select **Crash/Hang Analyzers** to analyze a crash/hang dump or click to select **Memory Pressure Analysis** to analyze a memory dump of a process suspected of leaking memory.</span></span>  
  
4.  <span data-ttu-id="efd5a-109">单击**添加数据文件**按钮以浏览到生成的转储文件，并单击**打开**按钮将转储文件添加到要分析数据文件的可能列表。</span><span class="sxs-lookup"><span data-stu-id="efd5a-109">Click the **Add Data Files** button to browse to the generated dump file and click the **Open** button to add the dump file to the possible list of data files to be analyzed.</span></span>  
  
5.  <span data-ttu-id="efd5a-110">单击以选择已添加的转储文件。</span><span class="sxs-lookup"><span data-stu-id="efd5a-110">Click to select the dump file that was added.</span></span>  
  
6.  <span data-ttu-id="efd5a-111">单击**开始分析**按钮。</span><span class="sxs-lookup"><span data-stu-id="efd5a-111">Click the **Start Analysis** button.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="efd5a-112">在分析器尝试找到并从 internet 下载适当的符号文件，如果在本地计算机上未安装符号文件。</span><span class="sxs-lookup"><span data-stu-id="efd5a-112">The analyzer attempts to locate and download the appropriate symbol files from the internet if the symbol files are not installed on the local computer.</span></span> <span data-ttu-id="efd5a-113">如果 BTSNTSvc.exe 进程中正在执行自定义代码，更新**符号搜索路径表示调试**中可用的选项**文件夹和搜索路径**选项卡**选项 （& a)设置**对话框包括相应的符号文件。</span><span class="sxs-lookup"><span data-stu-id="efd5a-113">If custom code is being executed in the BTSNTSvc.exe process, update the **Symbol Search Path For Debugging** option available in the **Folder And Search Paths** tab of the **Options & Settings** dialog to include the appropriate symbol files.</span></span> <span data-ttu-id="efd5a-114">单击**工具**菜单，然后选择**选项和设置**以显示**选项和设置**对话框。</span><span class="sxs-lookup"><span data-stu-id="efd5a-114">Click the **Tools** menu and select **Options And Settings** to display the **Options & Settings** dialog.</span></span>  
  
7.  <span data-ttu-id="efd5a-115">分析完成后一个报表以.mht 文件格式生成，并在 Internet Explorer 中显示。</span><span class="sxs-lookup"><span data-stu-id="efd5a-115">Once the analysis is complete a report is generated in .mht file format and displayed in Internet Explorer.</span></span> <span data-ttu-id="efd5a-116">默认情况下此报表将保存到本地计算机的 \Program Files\IIS Resources\DebugDiag\Reports 目录。</span><span class="sxs-lookup"><span data-stu-id="efd5a-116">By default this report is saved to the \Program Files\IIS Resources\DebugDiag\Reports directory of the local computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efd5a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="efd5a-117">See Also</span></span>  
 [<span data-ttu-id="efd5a-118">如何捕获 BizTalk 进程的内存转储</span><span class="sxs-lookup"><span data-stu-id="efd5a-118">How to Capture a Memory Dump of a BizTalk Process</span></span>](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md)