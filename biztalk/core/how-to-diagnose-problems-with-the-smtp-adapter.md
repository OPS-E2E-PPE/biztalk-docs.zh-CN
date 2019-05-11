---
title: 如何诊断 SMTP 适配器问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eaf39fd8-b662-4b0c-b5e8-1af02cb4f79b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd84acb26dfc70f5f2d84e93bb700ab48ea2fa03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338327"
---
# <a name="how-to-diagnose-problems-with-the-smtp-adapter"></a>如何诊断 SMTP 适配器问题
本部分包含可帮助您诊断 SMTP 适配器的问题时应遵循的步骤。  
  
### <a name="check-the-smtp-log-files-of-the-smtp-server-for-errors"></a>检查错误 SMTP 服务器的 SMTP 日志文件  
  
- 目标 SMTP 服务器日志文件可以包含有助于解决 SMTP 适配器问题的信息。 默认情况下在 SMTP 日志文件[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]位于以下目录中：  
  
   <em>%WinDir%\\</em>system32\LogFiles\SMTPSVC1\  
  
  > [!NOTE]
  >  *%Windir%* 是 SMTP 服务器上的 Windows 目录的位置的占位符。  
  > 
  > [!NOTE]
  >  默认情况下上禁用 SMTP 日志记录[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]。 有关启用 SMTP 日志记录的信息，请参阅 Windows Server 文档。  
  
## <a name="see-also"></a>请参阅  
 [工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [SMTP 适配器故障排除](../core/troubleshooting-the-smtp-adapter.md)