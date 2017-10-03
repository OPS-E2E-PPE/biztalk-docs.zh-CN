---
title: "如何诊断问题与 SOAP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16c93333-cb32-49bc-a1c4-9d726ab41850
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db1d495eb301f93100a6ac9a4e50c8f1c57e5f5a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-diagnose-problems-with-the-soap-adapter"></a>如何诊断 SOAP 适配器问题
本部分包含一些步骤，遵循这些步骤可帮助您诊断有关 SOAP 适配器的问题。  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a>在 IIS 服务器的 IIS 日志和 HTTPERR 日志中查找错误  
  
-   源或目标 IIS 服务器的日志文件可能会包含有助于解决 SOAP 适配器问题的信息。 默认情况下 IIS 日志文件[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]计算机都位于以下目录：  
  
     *%Windir%\\*system32\LogFiles\W3SVC1\  
  
    > [!NOTE]
    >  *%Windir%*是 IIS 服务器上的 Windows 目录的位置的占位符。  
  
     默认情况下，在基于 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 的计算机上，HTTPERR 日志文件位于下面的目录中：  
  
     *%Windir%\\*system32\LogFiles\HTTPERR\  
  
    > [!NOTE]
    >  只在 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 计算机上才有 HTTPERR 日志文件。  
  
## <a name="see-also"></a>另请参阅  
 [工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [故障排除 SOAP 适配器](../core/troubleshooting-the-soap-adapter.md)