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
ms.openlocfilehash: 28d920a7bdc61e98832fb6818f66182ab69acbf2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987214"
---
# <a name="how-to-diagnose-problems-with-the-ftp-adapter"></a>如何诊断 FTP 适配器问题
本部分中包含的步骤用于诊断 FTP 适配器的问题。  
  
### <a name="check-the-ftp-log-files-on-the-ftp-server-for-errors"></a>检查 FTP 服务器上 FTP 日志文件中是否有错误  
  
- 源 FTP 服务器或目标 FTP 服务器的日志文件中可能包含对解决 FTP 适配器问题有帮助的信息。 默认情况下，Windows Server 或 Windows XP 计算机上的 FTP 日志文件位于下列目录中：  
  
   <em>%Windir%\\</em>system32\LogFiles\MSFTPSVC1\  
  
  > [!NOTE]
  >  *%Windir%* 是 FTP 服务器上的 Windows 目录的位置的占位符。  
  
### <a name="enable-logging-for-the-ftp-receive-location-or-send-port"></a>为 FTP 接收位置或发送端口启用日志记录  
  
-   配置 FTP 接收位置或发送端口**日志**文件夹。 FTP 适配器会将详细的日志信息保存到此文件夹中。 **日志**文件夹选项位于**FTP 传输属性**对话框中使用 FTP 传输类型配置接收位置或发送端口时。  
  
## <a name="see-also"></a>请参阅  
 [工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)