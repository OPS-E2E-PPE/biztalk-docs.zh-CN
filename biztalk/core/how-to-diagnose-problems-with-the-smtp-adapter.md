---
title: 如何诊断 SMTP 适配器问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eaf39fd8-b662-4b0c-b5e8-1af02cb4f79b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5a1f88d6d096b697f8fceb3c81f8527fa5f7342
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010310"
---
# <a name="how-to-diagnose-problems-with-the-smtp-adapter"></a><span data-ttu-id="0ae14-102">如何诊断 SMTP 适配器问题</span><span class="sxs-lookup"><span data-stu-id="0ae14-102">How to Diagnose Problems with the SMTP Adapter</span></span>
<span data-ttu-id="0ae14-103">本部分提供的步骤可帮助您诊断 SMTP 适配器问题。</span><span class="sxs-lookup"><span data-stu-id="0ae14-103">This section contains steps that can be followed to help diagnose problems with the SMTP adapter.</span></span>  
  
### <a name="check-the-smtp-log-files-of-the-smtp-server-for-errors"></a><span data-ttu-id="0ae14-104">检查 SMTP 服务器的 SMTP 日志文件是否有错误</span><span class="sxs-lookup"><span data-stu-id="0ae14-104">Check the SMTP log files of the SMTP Server for errors</span></span>  
  
- <span data-ttu-id="0ae14-105">目标 SMTP 服务器日志文件包含的信息可帮助您解决 SMTP 适配器问题。</span><span class="sxs-lookup"><span data-stu-id="0ae14-105">The target SMTP server log files can contain information that is helpful for troubleshooting problems with the SMTP adapter.</span></span> <span data-ttu-id="0ae14-106">默认情况下，[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 上的 SMTP 日志文件位于下面的目录中：</span><span class="sxs-lookup"><span data-stu-id="0ae14-106">By default the SMTP log files on [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] are located in the following directory:</span></span>  
  
   <span data-ttu-id="0ae14-107"><em>%Windir%\\</em>system32\LogFiles\SMTPSVC1\\</span><span class="sxs-lookup"><span data-stu-id="0ae14-107"><em>%WinDir%\\</em>system32\LogFiles\SMTPSVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="0ae14-108">*%Windir%* 是 SMTP 服务器上的 Windows 目录的位置的占位符。</span><span class="sxs-lookup"><span data-stu-id="0ae14-108">*%WinDir%* is a placeholder for the location of the Windows directory on the SMTP server.</span></span>  
  > 
  > [!NOTE]
  >  <span data-ttu-id="0ae14-109">默认情况下，SMTP 日志记录在 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 上处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="0ae14-109">SMTP logging is disabled by default on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].</span></span> <span data-ttu-id="0ae14-110">有关启用 SMTP 日志记录的信息，请参阅 Windows 服务器文档。</span><span class="sxs-lookup"><span data-stu-id="0ae14-110">For information about enabling logging for SMTP, see the Windows Server documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ae14-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ae14-111">See Also</span></span>  
 <span data-ttu-id="0ae14-112">[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="0ae14-112">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="0ae14-113">SMTP 适配器故障排除</span><span class="sxs-lookup"><span data-stu-id="0ae14-113">Troubleshooting the SMTP Adapter</span></span>](../core/troubleshooting-the-smtp-adapter.md)