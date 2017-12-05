---
title: "安装和配置 BizTalk Accelerator for SWIFT HTTP 前端服务器上 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP server, installing BizTalk Accelerator for SWIFT
- BizTalk Accelerator for SWIFT, installing on HTTP server
ms.assetid: 1deaa5f7-9da2-4d4b-8367-2d6900065839
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8a63277ec58981f5f0f904aabe61957de66df08
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-http-front-end-servers"></a>安装和配置 BizTalk Accelerator for SWIFT HTTP 前端服务器上
本部分介绍如何安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]HTTP 前端服务器上。 这些服务器主要用于与 SWIFT 网络进行通信。  
  
### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-http-front-end-server"></a>若要安装和配置 BizTalk Accelerator for SWIFT HTTP 前端服务器上  
  
1.  执行的自定义安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。 安装**MRSR**和**用于消息修复和新提交的 Web 组件**功能。  
  
    > [!NOTE]
    >  安装完成后，将启动配置向导。  
  
2.  在 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置控制台中，配置**MCRR**和**WebService**。  
  
3.  完成配置向导，在 Web 服务器上之后, 在文件夹中打开 web.config 文件\<*驱动器*\>: files\microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ 在记事本中的。 搜索"授权"。 在**授权**部分中，将角色值设置为 A4SWIFT 用户组的名称。