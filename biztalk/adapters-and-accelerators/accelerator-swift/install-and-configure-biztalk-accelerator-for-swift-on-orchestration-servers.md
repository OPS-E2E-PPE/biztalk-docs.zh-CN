---
title: "安装和配置 BizTalk Accelerator for SWIFT Orchestration 服务器上 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestration server, installing BizTalk Accelerator for SWIFT
- BizTalk Accelerator for SWIFT, installing on orchestration server
ms.assetid: 127113ae-46b4-4290-a2c1-6a3db04cd178
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 384548de9fb0b7a5ee4ce440869c42fdfa1e93ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-orchestration-servers"></a>安装和配置 BizTalk Accelerator for SWIFT Orchestration 服务器上
本部分介绍如何安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]orchestration 服务器上。 这些服务器主要用于运行 FIN 修复和调节业务流程和消息修复/新建提交业务流程。  
  
### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-orchestration-server"></a>若要安装和配置 BizTalk Accelerator for SWIFT orchestration 服务器上  
  
1.  执行的自定义安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。 安装**MRSR**功能。  
  
    > [!NOTE]
    >  不需要安装 Web 组件消息修复和新提交功能，因为此服务器没有 MRSR 站点。  
  
    > [!NOTE]
    >  安装完成后，将启动配置向导。  
  
2.  在 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置控制台中，配置**MCRR**。