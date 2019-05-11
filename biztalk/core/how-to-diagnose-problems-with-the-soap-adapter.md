---
title: 如何诊断 SOAP 适配器问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16c93333-cb32-49bc-a1c4-9d726ab41850
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93b0339f44827dd716afc517ed3aeb8aca9c25e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385244"
---
# <a name="how-to-diagnose-problems-with-the-soap-adapter"></a>如何诊断 SOAP 适配器问题
本部分包含可帮助您诊断有关 SOAP 适配器的问题时应遵循的步骤。  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a>检查 IIS 日志和 HTTPERR 日志中的 IIS 服务器有错误  
  
- 源或目标 IIS 服务器日志文件可以包含有助于解决 SOAP 适配器的问题的信息。 默认情况下 IIS 日志文件[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]计算机都位于以下目录：  
  
   <em>%WinDir%\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *%Windir%* 是 IIS 服务器上的 Windows 目录的位置的占位符。  
  
   默认情况下上，HTTPERR 日志文件[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]基于的计算机都位于以下目录：  
  
   <em>%WinDir%\\</em>system32\LogFiles\HTTPERR\  
  
  > [!NOTE]
  >  仅适用于才有 HTTPERR 日志文件[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]计算机。  
  
## <a name="see-also"></a>请参阅  
 [工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [SOAP 适配器故障排除](../core/troubleshooting-the-soap-adapter.md)