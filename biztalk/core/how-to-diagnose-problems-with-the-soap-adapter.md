---
title: 如何诊断问题与 SOAP 适配器 |Microsoft 文档
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
ms.openlocfilehash: db1d495eb301f93100a6ac9a4e50c8f1c57e5f5a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249469"
---
# <a name="how-to-diagnose-problems-with-the-soap-adapter"></a><span data-ttu-id="8ab5b-102">如何诊断 SOAP 适配器问题</span><span class="sxs-lookup"><span data-stu-id="8ab5b-102">How to Diagnose Problems with the SOAP Adapter</span></span>
<span data-ttu-id="8ab5b-103">本部分包含一些步骤，遵循这些步骤可帮助您诊断有关 SOAP 适配器的问题。</span><span class="sxs-lookup"><span data-stu-id="8ab5b-103">This section contains steps that can be followed to help diagnose problems with the SOAP adapter.</span></span>  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a><span data-ttu-id="8ab5b-104">在 IIS 服务器的 IIS 日志和 HTTPERR 日志中查找错误</span><span class="sxs-lookup"><span data-stu-id="8ab5b-104">Check the IIS log and HTTPERR log of the IIS Server for errors</span></span>  
  
-   <span data-ttu-id="8ab5b-105">源或目标 IIS 服务器的日志文件可能会包含有助于解决 SOAP 适配器问题的信息。</span><span class="sxs-lookup"><span data-stu-id="8ab5b-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the SOAP adapter.</span></span> <span data-ttu-id="8ab5b-106">默认情况下 IIS 日志文件[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]计算机都位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="8ab5b-106">By default the IIS log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] computer are located in the following directory:</span></span>  
  
     <span data-ttu-id="8ab5b-107">*%Windir%\\*system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="8ab5b-107">*%WinDir%\\*system32\LogFiles\W3SVC1\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8ab5b-108">*%Windir%* 是 IIS 服务器上的 Windows 目录的位置的占位符。</span><span class="sxs-lookup"><span data-stu-id="8ab5b-108">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
     <span data-ttu-id="8ab5b-109">默认情况下，在基于 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 的计算机上，HTTPERR 日志文件位于下面的目录中：</span><span class="sxs-lookup"><span data-stu-id="8ab5b-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] based computer are located in the following directory:</span></span>  
  
     <span data-ttu-id="8ab5b-110">*%Windir%\\*system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="8ab5b-110">*%WinDir%\\*system32\LogFiles\HTTPERR\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8ab5b-111">只在 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 计算机上才有 HTTPERR 日志文件。</span><span class="sxs-lookup"><span data-stu-id="8ab5b-111">The HTTPERR log file is available only on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ab5b-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ab5b-112">See Also</span></span>  
 <span data-ttu-id="8ab5b-113">[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="8ab5b-113">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="8ab5b-114">故障排除 SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="8ab5b-114">Troubleshooting the SOAP Adapter</span></span>](../core/troubleshooting-the-soap-adapter.md)