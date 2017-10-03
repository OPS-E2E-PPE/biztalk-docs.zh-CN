---
title: "如何诊断问题 HTTP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91f818dd-11fa-4ea4-b904-e8e00b3e49b4
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 545e095624c30b4611c74dcfbdead13d685164ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-diagnose-problems-with-the-http-adapter"></a>如何使用 HTTP 适配器诊断问题
本部分包含用 HTTP 适配器帮助诊断问题所要遵循的步骤。  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a>检查 IIS 和 HTTPERR 日志文件，在 IIS 服务器有错误  
  
-   源或目标 IIS 服务器日志文件包含的信息有助于使用 HTTP 适配器进行故障排除。 默认情况下，Windows Server 上的 IIS 日志文件位于以下目录中：  
  
     *%Windir%\\*system32\LogFiles\W3SVC1\  
  
    > [!NOTE]
    >  *%Windir%*是 IIS 服务器上的 Windows 目录的位置的占位符。  
  
     默认情况下，在基于 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 的计算机上，HTTPERR 日志文件位于下面的目录中：  
  
     *%Windir%\\*system32\LogFiles\HTTPERR\  
  
    > [!NOTE]
    >  只在 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 计算机上才有 HTTPERR 日志文件。  
  
### <a name="isolate-problems-with-the-http-send-adapter-by-posting-to-the-destination-url-with-a-client-that-uses-the-systemnethttpwebrequest-class"></a>利用 HTTP 发送适配器通过使用 System.Net.HttpWebRequest 类的客户端向目标 URL 进行发布来隔离问题  
  
1.  如果在向目标 URL 进行发布时 HTTP 发送适配器生成错误，则创建一个使用 System.Net.HttpWebRequest 和 HttpWebResponse 类的客户端，以便向目标 URL 进行发布。 通常，此方法可以帮助确定问题是否特定于 HTTP 发送适配器，或在向目标 URL 进行发布时是否有问题。  
  
2.  有关创建使用 System.Net.HttpWebRequest 和 HttpWebResponse 类的客户端的详细信息请参阅[如何使用新的 System.Net 类创建 HTTP 客户端](http://go.microsoft.com/fwlink/?LinkId=66987)。  
  
## <a name="see-also"></a>另请参阅  
 [工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [故障排除 HTTP 适配器](../core/troubleshooting-the-http-adapter.md)