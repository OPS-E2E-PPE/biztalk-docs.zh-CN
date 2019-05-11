---
title: 如何诊断 FTP 适配器问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 499d23d3-b705-4527-9929-147be157e6b3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b7b090ee9d77754cb6ed3e1f1fb5d4ae4938658
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338460"
---
# <a name="how-to-diagnose-problems-with-the-ftp-adapter"></a><span data-ttu-id="8a301-102">如何诊断 FTP 适配器问题</span><span class="sxs-lookup"><span data-stu-id="8a301-102">How to Diagnose Problems with the FTP Adapter</span></span>
<span data-ttu-id="8a301-103">本部分包含可帮助诊断 FTP 适配器问题的步骤。</span><span class="sxs-lookup"><span data-stu-id="8a301-103">This section contains steps that can be followed to help diagnose problems with the FTP adapter.</span></span>  
  
### <a name="check-the-ftp-log-files-on-the-ftp-server-for-errors"></a><span data-ttu-id="8a301-104">检查 FTP 服务器上 FTP 日志文件的错误</span><span class="sxs-lookup"><span data-stu-id="8a301-104">Check the FTP log files on the FTP Server for errors</span></span>  
  
- <span data-ttu-id="8a301-105">源或目标 FTP 服务器日志文件可以包含对解决 FTP 适配器问题的有用的信息。</span><span class="sxs-lookup"><span data-stu-id="8a301-105">The source or target FTP server log files can contain information that is helpful for troubleshooting problems with the FTP adapter.</span></span> <span data-ttu-id="8a301-106">默认情况下在 Windows Server 或 Windows XP 计算机上的 FTP 日志文件位于以下目录中：</span><span class="sxs-lookup"><span data-stu-id="8a301-106">By default the FTP log files on a Windows Server or Windows XP computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="8a301-107"><em>%WinDir%\\</em>system32\LogFiles\MSFTPSVC1\\</span><span class="sxs-lookup"><span data-stu-id="8a301-107"><em>%WinDir%\\</em>system32\LogFiles\MSFTPSVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="8a301-108">*%Windir%* 是 FTP 服务器上的 Windows 目录的位置的占位符。</span><span class="sxs-lookup"><span data-stu-id="8a301-108">*%WinDir%* is a placeholder for the location of the Windows directory on the FTP server.</span></span>  
  
### <a name="enable-logging-for-the-ftp-receive-location-or-send-port"></a><span data-ttu-id="8a301-109">为 FTP 接收位置或发送端口启用日志记录</span><span class="sxs-lookup"><span data-stu-id="8a301-109">Enable logging for the FTP Receive location or Send Port</span></span>  
  
-   <span data-ttu-id="8a301-110">配置 FTP 接收位置或发送端口**日志**文件夹。</span><span class="sxs-lookup"><span data-stu-id="8a301-110">Configure the FTP receive location or send port with a **Log** folder.</span></span> <span data-ttu-id="8a301-111">FTP 适配器会将日志记录的详细的信息保存到此文件夹。</span><span class="sxs-lookup"><span data-stu-id="8a301-111">The FTP adapter will save detailed logging information to this folder.</span></span> <span data-ttu-id="8a301-112">**日志**文件夹选项位于**FTP 传输属性**对话框中使用 FTP 传输类型配置接收位置或发送端口时。</span><span class="sxs-lookup"><span data-stu-id="8a301-112">The **Log** folder option is available on the **FTP Transport Properties** dialog box when configuring a receive location or send port with the FTP transport type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a301-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a301-113">See Also</span></span>  
 [<span data-ttu-id="8a301-114">工具和实用程序用于故障排除</span><span class="sxs-lookup"><span data-stu-id="8a301-114">Tools and Utilities to Use for Troubleshooting</span></span>](../core/tools-and-utilities-to-use-for-troubleshooting.md)