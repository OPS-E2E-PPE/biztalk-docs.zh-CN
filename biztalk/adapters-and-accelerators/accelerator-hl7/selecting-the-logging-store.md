---
title: "选择日志记录存储 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- auditing, configuring
ms.assetid: 6ba64c59-3a15-4c10-b44f-18e0e432c6d3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0518b536db16d641b77a61cfeb4851990a7bca0a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="selecting-the-logging-store"></a>选择日志记录存储
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]你提供的选项来选择不同的日志记录存储的组合，如[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]Management Instrumentation (WMI) [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]，和[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]事件日志。  
  
 你使用[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器来配置日志记录存储。  
  
 使用以下过程来打开[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器和选择日志记录存储。  
  
### <a name="to-open-btahl7-configuration-explorer"></a>若要打开 BTAHL7 配置资源管理器  
  
-   单击**启动**，单击**程序**，单击**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。  
  
### <a name="to-select-the--logging-store"></a>若要选择的日志记录存储  
  
1.  在[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器，请在**全局设置**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**WMI**|如果你想要生成 BTAHL7 的 WMI 通知，请选择此选项。|  
    |**SQL**|选择此选项，如果你想要使用[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]作为日志记录存储。 **注意：** BTAHL7 自动创建所需的日志记录如果它们尚不存在的表。|  
    |**SQL Server**|类型[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]名称。 这是必需的当你选择**SQL**选项。 允许的最大长度为 64 个字符。<br /><br /> 默认服务器和数据库名称为配置的 BTAHL7 数据库。|  
    |**数据库名称**|类型[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库名称。 这是必需的当你选择**SQL**选项。 允许的最大长度为 128 个字符。|  
    |**事件日志**|选择此选项，如果你想要使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]作为日志记录存储的事件日志。 你使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]事件查看器以查看事件消息。|  
  
2.  单击 **“保存”**。  
  
    > [!NOTE]
    >  事件所记录的日志记录的事件代理的区域设置依赖于日志记录服务帐户的区域设置。  
  
    > [!NOTE]
    >  当更改日志记录服务帐户密码，则应首先更改中的密码[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsAD](../../includes/btsad-md.md)]目录服务和日志记录服务运行它的每个服务器上的日志记录服务密码更改后的然后重新启动。  
  
## <a name="see-also"></a>另请参阅  
 [消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)   
 [日志记录配置](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)