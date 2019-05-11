---
title: 如何诊断问题的 Windows SharePoint Services 适配器 |Microsoft Docs
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
ms.openlocfilehash: 3c5451a4fffd4c75b52f46741b1e7228dacf9f6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385214"
---
# <a name="how-to-diagnose-problems-with-the-windows-sharepoint-services-adapter"></a>如何诊断 Windows SharePoint Services 适配器问题
本部分包含可帮助您诊断有关 Windows Sharepoint Services 适配器的问题时应遵循的步骤。  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a>检查 IIS 和 HTTPERR 日志文件的 IIS 服务器有错误  
  
- 源或目标 IIS 服务器日志文件可以包含有助于解决 Windows Sharepoint Services 适配器问题的信息。 默认情况下 IIS 日志文件[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]计算机都位于以下目录：  
  
   <em>%WinDir%\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *%Windir%* 是 IIS 服务器上的 Windows 目录的位置的占位符。  
  
- 默认情况下上，HTTPERR 日志文件[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]基于的计算机都位于以下目录：  
  
   <em>%WinDir%\\</em>system32\LogFiles\HTTPERR\  
  
  > [!NOTE]
  >  上才有 HTTPERR 日志文件[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]计算机。  
  
## <a name="see-also"></a>请参阅  
 [工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [Windows SharePoint Services 适配器故障排除](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)