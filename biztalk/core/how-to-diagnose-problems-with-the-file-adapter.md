---
title: 如何诊断文件适配器问题 |Microsoft Docs
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
ms.openlocfilehash: 017d9f2027a42bb804b6baf4b2a14915e4a525de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385215"
---
# <a name="how-to-diagnose-problems-with-the-file-adapter"></a><span data-ttu-id="d5629-102">如何诊断文件适配器问题</span><span class="sxs-lookup"><span data-stu-id="d5629-102">How to Diagnose Problems with the File Adapter</span></span>
<span data-ttu-id="d5629-103">本部分包含可帮助您诊断文件适配器的问题时应遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="d5629-103">This section contains steps that can be followed to help diagnose problems with the File adapter.</span></span>  
  
### <a name="run-the-filemon-utility-to-diagnose-errors-that-occur-using-the-file-receive-or-file-send-adapter"></a><span data-ttu-id="d5629-104">运行 FileMon 实用程序以诊断出现使用文件接收适配器或文件发送适配器的错误</span><span class="sxs-lookup"><span data-stu-id="d5629-104">Run the FileMon Utility to diagnose errors that occur using the File Receive or File Send Adapter</span></span>  
  
1.  <span data-ttu-id="d5629-105">下载 FileMon 实用程序从[www.sysinternals.com](http://go.microsoft.com/fwlink/?LinkId=66235)。</span><span class="sxs-lookup"><span data-stu-id="d5629-105">Download the FileMon utility from [www.sysinternals.com](http://go.microsoft.com/fwlink/?LinkId=66235).</span></span>  
  
2.  <span data-ttu-id="d5629-106">安装的 Filemon 实用程序，承载该文件夹或共享的服务器上正在读取或写入到文件适配器。</span><span class="sxs-lookup"><span data-stu-id="d5629-106">Install the Filemon utility on the server that hosts the folder or share that is being read from or written to by the File Adapter.</span></span>  
  
3.  <span data-ttu-id="d5629-107">启动 Filemon 实用程序，并应用筛选器来监视所进行的文件适配器处理程序 (如 BTSNTSvc.exe) 中运行的 BizTalk 主机实例的文件访问。</span><span class="sxs-lookup"><span data-stu-id="d5629-107">Launch the Filemon utility and apply a filter to monitor only file accesses that are being made by the BizTalk Host instance that the file adapter handlers are running in (for example BTSNTSvc.exe).</span></span>  
  
4.  <span data-ttu-id="d5629-108">运行导致问题的方案。</span><span class="sxs-lookup"><span data-stu-id="d5629-108">Run the scenario that caused the problem.</span></span>  
  
5.  <span data-ttu-id="d5629-109">禁用文件监视在 Filemon 实用程序，然后将生成的日志文件保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="d5629-109">Disable file monitoring in the Filemon utility, then save the generated log file to disk.</span></span>  
  
6.  <span data-ttu-id="d5629-110">查看生成的日志文件中的任何错误。</span><span class="sxs-lookup"><span data-stu-id="d5629-110">Review the generated log file for any errors.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5629-111">FileMon 不受 Microsoft，因此 Microsoft 不保证此程序的适用性。</span><span class="sxs-lookup"><span data-stu-id="d5629-111">FileMon is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="d5629-112">使用此程序是完全由您自己承担。</span><span class="sxs-lookup"><span data-stu-id="d5629-112">Use of this program is entirely at your own risk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5629-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5629-113">See Also</span></span>  
 <span data-ttu-id="d5629-114">[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="d5629-114">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="d5629-115">文件适配器故障排除</span><span class="sxs-lookup"><span data-stu-id="d5629-115">Troubleshooting the File Adapter</span></span>](../core/troubleshooting-the-file-adapter.md)