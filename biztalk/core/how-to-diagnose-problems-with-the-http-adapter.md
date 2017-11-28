---
title: "如何诊断问题 HTTP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91f818dd-11fa-4ea4-b904-e8e00b3e49b4
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 545e095624c30b4611c74dcfbdead13d685164ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-diagnose-problems-with-the-http-adapter"></a><span data-ttu-id="c5671-102">如何使用 HTTP 适配器诊断问题</span><span class="sxs-lookup"><span data-stu-id="c5671-102">How to Diagnose Problems with the HTTP Adapter</span></span>
<span data-ttu-id="c5671-103">本部分包含用 HTTP 适配器帮助诊断问题所要遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="c5671-103">This section contains steps that can be followed to help diagnose problems with the HTTP adapter.</span></span>  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a><span data-ttu-id="c5671-104">检查 IIS 和 HTTPERR 日志文件，在 IIS 服务器有错误</span><span class="sxs-lookup"><span data-stu-id="c5671-104">Check the IIS and HTTPERR log files of the IIS Server for errors</span></span>  
  
-   <span data-ttu-id="c5671-105">源或目标 IIS 服务器日志文件包含的信息有助于使用 HTTP 适配器进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="c5671-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the HTTP adapter.</span></span> <span data-ttu-id="c5671-106">默认情况下，Windows Server 上的 IIS 日志文件位于以下目录中：</span><span class="sxs-lookup"><span data-stu-id="c5671-106">By default the IIS log files on a Windows Server are located in the following directory:</span></span>  
  
     <span data-ttu-id="c5671-107">*%Windir%\\*system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="c5671-107">*%WinDir%\\*system32\LogFiles\W3SVC1\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c5671-108">*%Windir%*是 IIS 服务器上的 Windows 目录的位置的占位符。</span><span class="sxs-lookup"><span data-stu-id="c5671-108">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
     <span data-ttu-id="c5671-109">默认情况下，在基于 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 的计算机上，HTTPERR 日志文件位于下面的目录中：</span><span class="sxs-lookup"><span data-stu-id="c5671-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] based computer are located in the following directory:</span></span>  
  
     <span data-ttu-id="c5671-110">*%Windir%\\*system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="c5671-110">*%WinDir%\\*system32\LogFiles\HTTPERR\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c5671-111">只在 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 计算机上才有 HTTPERR 日志文件。</span><span class="sxs-lookup"><span data-stu-id="c5671-111">The HTTPERR log file is available only on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  
  
### <a name="isolate-problems-with-the-http-send-adapter-by-posting-to-the-destination-url-with-a-client-that-uses-the-systemnethttpwebrequest-class"></a><span data-ttu-id="c5671-112">利用 HTTP 发送适配器通过使用 System.Net.HttpWebRequest 类的客户端向目标 URL 进行发布来隔离问题</span><span class="sxs-lookup"><span data-stu-id="c5671-112">Isolate problems with the HTTP send adapter by posting to the destination URL with a client that uses the System.Net.HttpWebRequest class</span></span>  
  
1.  <span data-ttu-id="c5671-113">如果在向目标 URL 进行发布时 HTTP 发送适配器生成错误，则创建一个使用 System.Net.HttpWebRequest 和 HttpWebResponse 类的客户端，以便向目标 URL 进行发布。</span><span class="sxs-lookup"><span data-stu-id="c5671-113">If the HTTP send adapter is generating errors when posting to the destination URL, create a client that uses the System.Net.HttpWebRequest and HttpWebResponse classes to post to the destination URL.</span></span> <span data-ttu-id="c5671-114">通常，此方法可以帮助确定问题是否特定于 HTTP 发送适配器，或在向目标 URL 进行发布时是否有问题。</span><span class="sxs-lookup"><span data-stu-id="c5671-114">This approach will help determine if the problem is specific to the HTTP send adapter or if there is a problem posting to the destination URL in general.</span></span>  
  
2.  <span data-ttu-id="c5671-115">有关创建使用 System.Net.HttpWebRequest 和 HttpWebResponse 类的客户端的详细信息请参阅[如何使用新的 System.Net 类创建 HTTP 客户端](http://go.microsoft.com/fwlink/?LinkId=66987)。</span><span class="sxs-lookup"><span data-stu-id="c5671-115">For more information about creating a client that uses the System.Net.HttpWebRequest and HttpWebResponse classes see [How to use the new System.Net classes to create an HTTP client](http://go.microsoft.com/fwlink/?LinkId=66987).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5671-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5671-116">See Also</span></span>  
 <span data-ttu-id="c5671-117">[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="c5671-117">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="c5671-118">故障排除 HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="c5671-118">Troubleshooting the HTTP Adapter</span></span>](../core/troubleshooting-the-http-adapter.md)