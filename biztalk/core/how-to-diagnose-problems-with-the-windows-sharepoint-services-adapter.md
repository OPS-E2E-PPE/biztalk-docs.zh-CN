---
title: 如何诊断问题与 Windows SharePoint Services 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55c29569-3814-43a7-93f8-a39c3464a831
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67aa43628e8db4384a411fd1cc4696b7955b3752
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248997"
---
# <a name="how-to-diagnose-problems-with-the-windows-sharepoint-services-adapter"></a>如何诊断 Windows SharePoint Services 适配器问题
本部分包含一些步骤，遵循这些步骤可帮助您诊断有关 Windows Sharepoint Services 适配器的问题。  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a>检查 IIS 和 HTTPERR 日志文件，在 IIS 服务器有错误  
  
-   源 IIS 服务器或目标 IIS 服务器的日志文件可能会包含有助于解决 Windows Sharepoint Services 适配器问题的信息。 默认情况下 IIS 日志文件[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]计算机都位于以下目录：  
  
     *%Windir%\\*system32\LogFiles\W3SVC1\  
  
    > [!NOTE]
    >  *%Windir%* 是 IIS 服务器上的 Windows 目录的位置的占位符。  
  
-   默认情况下，在基于 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 的计算机上，HTTPERR 日志文件位于下面的目录中：  
  
     *%Windir%\\*system32\LogFiles\HTTPERR\  
  
    > [!NOTE]
    >  HTTPERR 日志文件才可在上找到[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]计算机。  
  
## <a name="see-also"></a>另请参阅  
 [工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [故障排除 Windows SharePoint Services Adapter](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)