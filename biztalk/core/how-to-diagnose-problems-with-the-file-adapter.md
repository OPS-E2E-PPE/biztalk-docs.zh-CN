---
title: 如何诊断文件适配器问题 |Microsoft Docs
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
ms.openlocfilehash: 017d9f2027a42bb804b6baf4b2a14915e4a525de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385215"
---
# <a name="how-to-diagnose-problems-with-the-file-adapter"></a>如何诊断文件适配器问题
本部分包含可帮助您诊断文件适配器的问题时应遵循的步骤。  
  
### <a name="run-the-filemon-utility-to-diagnose-errors-that-occur-using-the-file-receive-or-file-send-adapter"></a>运行 FileMon 实用程序以诊断出现使用文件接收适配器或文件发送适配器的错误  
  
1.  下载 FileMon 实用程序从[www.sysinternals.com](http://go.microsoft.com/fwlink/?LinkId=66235)。  
  
2.  安装的 Filemon 实用程序，承载该文件夹或共享的服务器上正在读取或写入到文件适配器。  
  
3.  启动 Filemon 实用程序，并应用筛选器来监视所进行的文件适配器处理程序 (如 BTSNTSvc.exe) 中运行的 BizTalk 主机实例的文件访问。  
  
4.  运行导致问题的方案。  
  
5.  禁用文件监视在 Filemon 实用程序，然后将生成的日志文件保存到磁盘。  
  
6.  查看生成的日志文件中的任何错误。  
  
    > [!NOTE]
    >  FileMon 不受 Microsoft，因此 Microsoft 不保证此程序的适用性。 使用此程序是完全由您自己承担。  
  
## <a name="see-also"></a>请参阅  
 [工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [文件适配器故障排除](../core/troubleshooting-the-file-adapter.md)