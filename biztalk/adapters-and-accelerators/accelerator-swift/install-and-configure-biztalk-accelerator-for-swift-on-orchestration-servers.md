---
title: 安装和配置 BizTalk Accelerator for SWIFT 业务流程服务器上 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration server, installing BizTalk Accelerator for SWIFT
- BizTalk Accelerator for SWIFT, installing on orchestration server
ms.assetid: 127113ae-46b4-4290-a2c1-6a3db04cd178
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2dcf11738d89600c190cdec99375348404f47f3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377348"
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-orchestration-servers"></a>安装和配置 BizTalk Accelerator for SWIFT 业务流程服务器上
本部分介绍如何安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]业务流程服务器上。 这些服务器主要用于运行 FIN 修复和对帐业务流程和消息修复 / 新建提交业务流程。  

### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-orchestration-server"></a>若要安装和配置 BizTalk Accelerator for SWIFT 业务流程服务器上  

1. 执行的自定义安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。 安装**MRSR**功能。  

   > [!NOTE]
   >  不需要安装用于消息修复和新提交的功能的 Web 组件，因为此服务器没有 MRSR 站点。  

   > [!NOTE]
   >  安装完成后，将启动配置向导。  

2. 在 microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置控制台中，配置**MCRR**。
