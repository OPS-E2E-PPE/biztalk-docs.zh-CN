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
# <a name="how-to-diagnose-problems-with-the-ftp-adapter"></a>如何诊断 FTP 适配器问题
本部分包含可帮助诊断 FTP 适配器问题的步骤。  
  
### <a name="check-the-ftp-log-files-on-the-ftp-server-for-errors"></a>检查 FTP 服务器上 FTP 日志文件的错误  
  
- 源或目标 FTP 服务器日志文件可以包含对解决 FTP 适配器问题的有用的信息。 默认情况下在 Windows Server 或 Windows XP 计算机上的 FTP 日志文件位于以下目录中：  
  
   <em>%WinDir%\\</em>system32\LogFiles\MSFTPSVC1\  
  
  > [!NOTE]
  >  *%Windir%* 是 FTP 服务器上的 Windows 目录的位置的占位符。  
  
### <a name="enable-logging-for-the-ftp-receive-location-or-send-port"></a>为 FTP 接收位置或发送端口启用日志记录  
  
-   配置 FTP 接收位置或发送端口**日志**文件夹。 FTP 适配器会将日志记录的详细的信息保存到此文件夹。 **日志**文件夹选项位于**FTP 传输属性**对话框中使用 FTP 传输类型配置接收位置或发送端口时。  
  
## <a name="see-also"></a>请参阅  
 [工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)