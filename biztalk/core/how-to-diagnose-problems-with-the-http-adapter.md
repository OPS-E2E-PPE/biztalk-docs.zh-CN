---
title: 如何诊断 HTTP 适配器的问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91f818dd-11fa-4ea4-b904-e8e00b3e49b4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1496ed936629a502d9274800455fd79334260f51
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385254"
---
# <a name="how-to-diagnose-problems-with-the-http-adapter"></a><span data-ttu-id="63732-102">如何诊断 HTTP 适配器的问题</span><span class="sxs-lookup"><span data-stu-id="63732-102">How to Diagnose Problems with the HTTP Adapter</span></span>
<span data-ttu-id="63732-103">本部分包含可帮助您诊断 HTTP 适配器的问题时应遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="63732-103">This section contains steps that can be followed to help diagnose problems with the HTTP adapter.</span></span>  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a><span data-ttu-id="63732-104">检查 IIS 和 HTTPERR 日志文件的 IIS 服务器有错误</span><span class="sxs-lookup"><span data-stu-id="63732-104">Check the IIS and HTTPERR log files of the IIS Server for errors</span></span>  
  
- <span data-ttu-id="63732-105">源或目标 IIS 服务器日志文件可以包含有助于解决有关 HTTP 适配器的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="63732-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the HTTP adapter.</span></span> <span data-ttu-id="63732-106">默认情况下，IIS 在 Windows Server 上的日志文件位于以下目录中：</span><span class="sxs-lookup"><span data-stu-id="63732-106">By default the IIS log files on a Windows Server are located in the following directory:</span></span>  
  
   <span data-ttu-id="63732-107"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="63732-107"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="63732-108">*%Windir%* 是 IIS 服务器上的 Windows 目录的位置的占位符。</span><span class="sxs-lookup"><span data-stu-id="63732-108">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
   <span data-ttu-id="63732-109">默认情况下上，HTTPERR 日志文件[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]基于的计算机都位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="63732-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] based computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="63732-110"><em>%WinDir%\\</em>system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="63732-110"><em>%WinDir%\\</em>system32\LogFiles\HTTPERR\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="63732-111">仅适用于才有 HTTPERR 日志文件[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="63732-111">The HTTPERR log file is available only on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  
  
### <a name="isolate-problems-with-the-http-send-adapter-by-posting-to-the-destination-url-with-a-client-that-uses-the-systemnethttpwebrequest-class"></a><span data-ttu-id="63732-112">通过使用 System.Net.HttpWebRequest 类的客户端与发布的目标 URL 隔离与 HTTP 发送适配器的问题</span><span class="sxs-lookup"><span data-stu-id="63732-112">Isolate problems with the HTTP send adapter by posting to the destination URL with a client that uses the System.Net.HttpWebRequest class</span></span>  
  
1.  <span data-ttu-id="63732-113">如果在发布到目标 URL 的 HTTP 发送适配器生成错误，，创建使用 System.Net.HttpWebRequest 和 HttpWebResponse 类要发布到目标 URL 的客户端。</span><span class="sxs-lookup"><span data-stu-id="63732-113">If the HTTP send adapter is generating errors when posting to the destination URL, create a client that uses the System.Net.HttpWebRequest and HttpWebResponse classes to post to the destination URL.</span></span> <span data-ttu-id="63732-114">此方法将有助于确定问题是否特定于 HTTP 发送适配器，或如果一般情况下向目标 URL 发帖时遇到问题。</span><span class="sxs-lookup"><span data-stu-id="63732-114">This approach will help determine if the problem is specific to the HTTP send adapter or if there is a problem posting to the destination URL in general.</span></span>  
  
2.  <span data-ttu-id="63732-115">有关创建使用 System.Net.HttpWebRequest 和 HttpWebResponse 类的客户端的详细信息请参阅[如何使用新的 System.Net 类创建 HTTP 客户端](http://go.microsoft.com/fwlink/?LinkId=66987)。</span><span class="sxs-lookup"><span data-stu-id="63732-115">For more information about creating a client that uses the System.Net.HttpWebRequest and HttpWebResponse classes see [How to use the new System.Net classes to create an HTTP client](http://go.microsoft.com/fwlink/?LinkId=66987).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63732-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="63732-116">See Also</span></span>  
 <span data-ttu-id="63732-117">[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="63732-117">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="63732-118">HTTP 适配器故障排除</span><span class="sxs-lookup"><span data-stu-id="63732-118">Troubleshooting the HTTP Adapter</span></span>](../core/troubleshooting-the-http-adapter.md)