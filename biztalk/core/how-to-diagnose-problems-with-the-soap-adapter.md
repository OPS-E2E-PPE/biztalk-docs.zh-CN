---
title: 如何诊断 SOAP 适配器问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16c93333-cb32-49bc-a1c4-9d726ab41850
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93b0339f44827dd716afc517ed3aeb8aca9c25e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385244"
---
# <a name="how-to-diagnose-problems-with-the-soap-adapter"></a><span data-ttu-id="4c9cc-102">如何诊断 SOAP 适配器问题</span><span class="sxs-lookup"><span data-stu-id="4c9cc-102">How to Diagnose Problems with the SOAP Adapter</span></span>
<span data-ttu-id="4c9cc-103">本部分包含可帮助您诊断有关 SOAP 适配器的问题时应遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="4c9cc-103">This section contains steps that can be followed to help diagnose problems with the SOAP adapter.</span></span>  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a><span data-ttu-id="4c9cc-104">检查 IIS 日志和 HTTPERR 日志中的 IIS 服务器有错误</span><span class="sxs-lookup"><span data-stu-id="4c9cc-104">Check the IIS log and HTTPERR log of the IIS Server for errors</span></span>  
  
- <span data-ttu-id="4c9cc-105">源或目标 IIS 服务器日志文件可以包含有助于解决 SOAP 适配器的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="4c9cc-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the SOAP adapter.</span></span> <span data-ttu-id="4c9cc-106">默认情况下 IIS 日志文件[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]计算机都位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="4c9cc-106">By default the IIS log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="4c9cc-107"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="4c9cc-107"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="4c9cc-108">*%Windir%* 是 IIS 服务器上的 Windows 目录的位置的占位符。</span><span class="sxs-lookup"><span data-stu-id="4c9cc-108">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
   <span data-ttu-id="4c9cc-109">默认情况下上，HTTPERR 日志文件[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]基于的计算机都位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="4c9cc-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] based computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="4c9cc-110"><em>%WinDir%\\</em>system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="4c9cc-110"><em>%WinDir%\\</em>system32\LogFiles\HTTPERR\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="4c9cc-111">仅适用于才有 HTTPERR 日志文件[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="4c9cc-111">The HTTPERR log file is available only on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c9cc-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c9cc-112">See Also</span></span>  
 <span data-ttu-id="4c9cc-113">[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="4c9cc-113">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="4c9cc-114">SOAP 适配器故障排除</span><span class="sxs-lookup"><span data-stu-id="4c9cc-114">Troubleshooting the SOAP Adapter</span></span>](../core/troubleshooting-the-soap-adapter.md)