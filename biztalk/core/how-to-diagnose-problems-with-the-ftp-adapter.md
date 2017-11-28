---
title: "如何使用 FTP 适配器诊断问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 499d23d3-b705-4527-9929-147be157e6b3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e66be2e498449b1cdcc70e05c6195ccd8e4395d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-diagnose-problems-with-the-ftp-adapter"></a><span data-ttu-id="0f4c6-102">如何使用 FTP 适配器诊断问题</span><span class="sxs-lookup"><span data-stu-id="0f4c6-102">How to Diagnose Problems with the FTP Adapter</span></span>
<span data-ttu-id="0f4c6-103">本部分中包含的步骤用于诊断 FTP 适配器的问题。</span><span class="sxs-lookup"><span data-stu-id="0f4c6-103">This section contains steps that can be followed to help diagnose problems with the FTP adapter.</span></span>  
  
### <a name="check-the-ftp-log-files-on-the-ftp-server-for-errors"></a><span data-ttu-id="0f4c6-104">检查 FTP 服务器上 FTP 日志文件中是否有错误</span><span class="sxs-lookup"><span data-stu-id="0f4c6-104">Check the FTP log files on the FTP Server for errors</span></span>  
  
-   <span data-ttu-id="0f4c6-105">源 FTP 服务器或目标 FTP 服务器的日志文件中可能包含对解决 FTP 适配器问题有帮助的信息。</span><span class="sxs-lookup"><span data-stu-id="0f4c6-105">The source or target FTP server log files can contain information that is helpful for troubleshooting problems with the FTP adapter.</span></span> <span data-ttu-id="0f4c6-106">默认情况下，Windows Server 或 Windows XP 计算机上的 FTP 日志文件位于下列目录中：</span><span class="sxs-lookup"><span data-stu-id="0f4c6-106">By default the FTP log files on a Windows Server or Windows XP computer are located in the following directory:</span></span>  
  
     <span data-ttu-id="0f4c6-107">*%Windir%\\*system32\LogFiles\MSFTPSVC1\\</span><span class="sxs-lookup"><span data-stu-id="0f4c6-107">*%WinDir%\\*system32\LogFiles\MSFTPSVC1\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0f4c6-108">*%Windir%*是 FTP 服务器上的 Windows 目录的位置的占位符。</span><span class="sxs-lookup"><span data-stu-id="0f4c6-108">*%WinDir%* is a placeholder for the location of the Windows directory on the FTP server.</span></span>  
  
### <a name="enable-logging-for-the-ftp-receive-location-or-send-port"></a><span data-ttu-id="0f4c6-109">为 FTP 接收位置或发送端口启用日志记录</span><span class="sxs-lookup"><span data-stu-id="0f4c6-109">Enable logging for the FTP Receive location or Send Port</span></span>  
  
-   <span data-ttu-id="0f4c6-110">配置 FTP 接收位置或发送具有端口**日志**文件夹。</span><span class="sxs-lookup"><span data-stu-id="0f4c6-110">Configure the FTP receive location or send port with a **Log** folder.</span></span> <span data-ttu-id="0f4c6-111">FTP 适配器会将详细的日志信息保存到此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0f4c6-111">The FTP adapter will save detailed logging information to this folder.</span></span> <span data-ttu-id="0f4c6-112">**日志**在文件夹选项才可用**FTP 传输属性**对话框中使用的 FTP 传输类型配置接收位置或发送端口时。</span><span class="sxs-lookup"><span data-stu-id="0f4c6-112">The **Log** folder option is available on the **FTP Transport Properties** dialog box when configuring a receive location or send port with the FTP transport type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f4c6-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f4c6-113">See Also</span></span>  
 [<span data-ttu-id="0f4c6-114">工具和实用程序用于故障排除</span><span class="sxs-lookup"><span data-stu-id="0f4c6-114">Tools and Utilities to Use for Troubleshooting</span></span>](../core/tools-and-utilities-to-use-for-troubleshooting.md)