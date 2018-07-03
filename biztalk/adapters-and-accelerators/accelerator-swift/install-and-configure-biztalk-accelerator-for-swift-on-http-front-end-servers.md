---
title: 安装和配置 BizTalk Accelerator for SWIFT HTTP 前端服务器上 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP server, installing BizTalk Accelerator for SWIFT
- BizTalk Accelerator for SWIFT, installing on HTTP server
ms.assetid: 1deaa5f7-9da2-4d4b-8367-2d6900065839
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 375f5f26c9c71554f4ad44bd688f1d715cb81b92
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973454"
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-http-front-end-servers"></a>安装和配置 BizTalk Accelerator for SWIFT HTTP 前端服务器上
本部分介绍如何安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]HTTP 前端服务器上。 这些服务器主要用于与 SWIFT 网络进行通信。  

### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-http-front-end-server"></a>若要安装和配置 BizTalk Accelerator for SWIFT HTTP 前端服务器上  

1. 执行的自定义安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。 安装**MRSR**并**用于消息修复和新提交的 Web 组件**功能。  

   > [!NOTE]
   >  安装完成后，将启动配置向导。  

2. 在 microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置控制台中，配置**MCRR**并**WebService**。  

3. 完成 Web 服务器上的配置向导后打开 web.config 文件的文件夹中\<*驱动器*\>: \Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ 在记事本中的。 搜索"授权"。 在中**授权**部分中，将角色值设置为 A4SWIFT 用户组的名称。
