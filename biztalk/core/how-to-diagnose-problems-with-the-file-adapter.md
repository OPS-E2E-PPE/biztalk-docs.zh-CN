---
title: 如何诊断问题文件适配器 |Microsoft 文档
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
ms.openlocfilehash: f0481a3abdf497c093a87d7d74ea0356c7cad0d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249037"
---
# <a name="how-to-diagnose-problems-with-the-file-adapter"></a>如何诊断文件适配器的问题
本部分提供的步骤可帮助您诊断文件适配器问题。  
  
### <a name="run-the-filemon-utility-to-diagnose-errors-that-occur-using-the-file-receive-or-file-send-adapter"></a>运行 FileMon 实用程序以诊断使用文件接收适配器或文件发送适配器时发生的错误  
  
1.  下载由 FileMon 实用程序从[www.sysinternals.com](http://go.microsoft.com/fwlink/?LinkId=66235)。  
  
2.  将 Filemon 实用程序安装在文件适配器正在读取或写入的文件夹或共享位置的宿主服务器上。  
  
3.  启动 Filemon 实用程序，应用筛选器，只监视运行文件适配器处理程序（如 BTSNTSvc.exe）的 BizTalk 主机实例所进行的文件访问。  
  
4.  运行引起问题的方案。  
  
5.  在 Filemon 实用程序中禁用文件监视，然后将生成的日志文件保存到磁盘。  
  
6.  查看生成的日志文件中是否记录任何错误。  
  
    > [!NOTE]
    >  Microsoft 不支持 FileMon，因此 Microsoft 不保证此程序的适用性。 使用此程序风险自负。  
  
## <a name="see-also"></a>另请参阅  
 [工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [故障排除的文件适配器](../core/troubleshooting-the-file-adapter.md)