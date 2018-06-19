---
title: 如何诊断问题文件适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f06089a5-4747-4879-a796-157088868dba
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0481a3abdf497c093a87d7d74ea0356c7cad0d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249037"
---
# <a name="how-to-diagnose-problems-with-the-file-adapter"></a><span data-ttu-id="b8d83-102">如何诊断文件适配器的问题</span><span class="sxs-lookup"><span data-stu-id="b8d83-102">How to Diagnose Problems with the File Adapter</span></span>
<span data-ttu-id="b8d83-103">本部分提供的步骤可帮助您诊断文件适配器问题。</span><span class="sxs-lookup"><span data-stu-id="b8d83-103">This section contains steps that can be followed to help diagnose problems with the File adapter.</span></span>  
  
### <a name="run-the-filemon-utility-to-diagnose-errors-that-occur-using-the-file-receive-or-file-send-adapter"></a><span data-ttu-id="b8d83-104">运行 FileMon 实用程序以诊断使用文件接收适配器或文件发送适配器时发生的错误</span><span class="sxs-lookup"><span data-stu-id="b8d83-104">Run the FileMon Utility to diagnose errors that occur using the File Receive or File Send Adapter</span></span>  
  
1.  <span data-ttu-id="b8d83-105">下载由 FileMon 实用程序从[www.sysinternals.com](http://go.microsoft.com/fwlink/?LinkId=66235)。</span><span class="sxs-lookup"><span data-stu-id="b8d83-105">Download the FileMon utility from [www.sysinternals.com](http://go.microsoft.com/fwlink/?LinkId=66235).</span></span>  
  
2.  <span data-ttu-id="b8d83-106">将 Filemon 实用程序安装在文件适配器正在读取或写入的文件夹或共享位置的宿主服务器上。</span><span class="sxs-lookup"><span data-stu-id="b8d83-106">Install the Filemon utility on the server that hosts the folder or share that is being read from or written to by the File Adapter.</span></span>  
  
3.  <span data-ttu-id="b8d83-107">启动 Filemon 实用程序，应用筛选器，只监视运行文件适配器处理程序（如 BTSNTSvc.exe）的 BizTalk 主机实例所进行的文件访问。</span><span class="sxs-lookup"><span data-stu-id="b8d83-107">Launch the Filemon utility and apply a filter to monitor only file accesses that are being made by the BizTalk Host instance that the file adapter handlers are running in (for example BTSNTSvc.exe).</span></span>  
  
4.  <span data-ttu-id="b8d83-108">运行引起问题的方案。</span><span class="sxs-lookup"><span data-stu-id="b8d83-108">Run the scenario that caused the problem.</span></span>  
  
5.  <span data-ttu-id="b8d83-109">在 Filemon 实用程序中禁用文件监视，然后将生成的日志文件保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="b8d83-109">Disable file monitoring in the Filemon utility, then save the generated log file to disk.</span></span>  
  
6.  <span data-ttu-id="b8d83-110">查看生成的日志文件中是否记录任何错误。</span><span class="sxs-lookup"><span data-stu-id="b8d83-110">Review the generated log file for any errors.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b8d83-111">Microsoft 不支持 FileMon，因此 Microsoft 不保证此程序的适用性。</span><span class="sxs-lookup"><span data-stu-id="b8d83-111">FileMon is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="b8d83-112">使用此程序风险自负。</span><span class="sxs-lookup"><span data-stu-id="b8d83-112">Use of this program is entirely at your own risk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8d83-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8d83-113">See Also</span></span>  
 <span data-ttu-id="b8d83-114">[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="b8d83-114">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="b8d83-115">故障排除的文件适配器</span><span class="sxs-lookup"><span data-stu-id="b8d83-115">Troubleshooting the File Adapter</span></span>](../core/troubleshooting-the-file-adapter.md)