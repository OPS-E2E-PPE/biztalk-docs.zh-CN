---
title: 如何诊断问题与 SMTP 适配器 |Microsoft 文档
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
ms.openlocfilehash: 1a41a347534c07b522de5fc073933758870bf8a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249669"
---
# <a name="how-to-diagnose-problems-with-the-smtp-adapter"></a>如何诊断与 SMTP 适配器问题
本部分提供的步骤可帮助您诊断 SMTP 适配器问题。  
  
### <a name="check-the-smtp-log-files-of-the-smtp-server-for-errors"></a>检查 SMTP 服务器的 SMTP 日志文件是否有错误  
  
-   目标 SMTP 服务器日志文件包含的信息可帮助您解决 SMTP 适配器问题。 默认情况下，[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 上的 SMTP 日志文件位于下面的目录中：  
  
     *%Windir%\\*system32\LogFiles\SMTPSVC1\  
  
    > [!NOTE]
    >  *%Windir%* 是 SMTP 服务器上的 Windows 目录的位置的占位符。  
  
    > [!NOTE]
    >  默认情况下，SMTP 日志记录在 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 上处于禁用状态。 有关启用 SMTP 日志记录的信息，请参阅 Windows 服务器文档。  
  
## <a name="see-also"></a>另请参阅  
 [工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [故障排除 SMTP 适配器](../core/troubleshooting-the-smtp-adapter.md)