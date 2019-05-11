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
# <a name="how-to-diagnose-problems-with-the-http-adapter"></a>如何诊断 HTTP 适配器的问题
本部分包含可帮助您诊断 HTTP 适配器的问题时应遵循的步骤。  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a>检查 IIS 和 HTTPERR 日志文件的 IIS 服务器有错误  
  
- 源或目标 IIS 服务器日志文件可以包含有助于解决有关 HTTP 适配器的问题的信息。 默认情况下，IIS 在 Windows Server 上的日志文件位于以下目录中：  
  
   <em>%WinDir%\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *%Windir%* 是 IIS 服务器上的 Windows 目录的位置的占位符。  
  
   默认情况下上，HTTPERR 日志文件[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]基于的计算机都位于以下目录：  
  
   <em>%WinDir%\\</em>system32\LogFiles\HTTPERR\  
  
  > [!NOTE]
  >  仅适用于才有 HTTPERR 日志文件[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]计算机。  
  
### <a name="isolate-problems-with-the-http-send-adapter-by-posting-to-the-destination-url-with-a-client-that-uses-the-systemnethttpwebrequest-class"></a>通过使用 System.Net.HttpWebRequest 类的客户端与发布的目标 URL 隔离与 HTTP 发送适配器的问题  
  
1.  如果在发布到目标 URL 的 HTTP 发送适配器生成错误，，创建使用 System.Net.HttpWebRequest 和 HttpWebResponse 类要发布到目标 URL 的客户端。 此方法将有助于确定问题是否特定于 HTTP 发送适配器，或如果一般情况下向目标 URL 发帖时遇到问题。  
  
2.  有关创建使用 System.Net.HttpWebRequest 和 HttpWebResponse 类的客户端的详细信息请参阅[如何使用新的 System.Net 类创建 HTTP 客户端](http://go.microsoft.com/fwlink/?LinkId=66987)。  
  
## <a name="see-also"></a>请参阅  
 [工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [HTTP 适配器故障排除](../core/troubleshooting-the-http-adapter.md)