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
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-http-front-end-servers"></a><span data-ttu-id="8ca9b-102">安装和配置 BizTalk Accelerator for SWIFT HTTP 前端服务器上</span><span class="sxs-lookup"><span data-stu-id="8ca9b-102">Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers</span></span>
<span data-ttu-id="8ca9b-103">本部分介绍如何安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]HTTP 前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="8ca9b-103">This section describes how to install and configure [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] on the HTTP front-end servers.</span></span> <span data-ttu-id="8ca9b-104">这些服务器主要用于与 SWIFT 网络进行通信。</span><span class="sxs-lookup"><span data-stu-id="8ca9b-104">These servers are mainly used to communicate with the SWIFT Network.</span></span>  

### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-http-front-end-server"></a><span data-ttu-id="8ca9b-105">若要安装和配置 BizTalk Accelerator for SWIFT HTTP 前端服务器上</span><span class="sxs-lookup"><span data-stu-id="8ca9b-105">To install and configure BizTalk Accelerator for SWIFT on the HTTP front-end server</span></span>  

1. <span data-ttu-id="8ca9b-106">执行的自定义安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8ca9b-106">Perform a Custom Install of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="8ca9b-107">安装**MRSR**并**用于消息修复和新提交的 Web 组件**功能。</span><span class="sxs-lookup"><span data-stu-id="8ca9b-107">Install the **MRSR** and **Web Components for Message Repair and New Submission** features.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="8ca9b-108">安装完成后，将启动配置向导。</span><span class="sxs-lookup"><span data-stu-id="8ca9b-108">After installation is complete, the Configuration Wizard starts.</span></span>  

2. <span data-ttu-id="8ca9b-109">在 microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置控制台中，配置**MCRR**并**WebService**。</span><span class="sxs-lookup"><span data-stu-id="8ca9b-109">In the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console, configure **MCRR** and **WebService**.</span></span>  

3. <span data-ttu-id="8ca9b-110">完成 Web 服务器上的配置向导后打开 web.config 文件的文件夹中\<*驱动器*\>: \Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ 在记事本中的。</span><span class="sxs-lookup"><span data-stu-id="8ca9b-110">After completing the Configuration Wizard, on the Web servers, open the web.config file in the folder \<*Drive*\>:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ in Notepad.</span></span> <span data-ttu-id="8ca9b-111">搜索"授权"。</span><span class="sxs-lookup"><span data-stu-id="8ca9b-111">Search for "Authorization".</span></span> <span data-ttu-id="8ca9b-112">在中**授权**部分中，将角色值设置为 A4SWIFT 用户组的名称。</span><span class="sxs-lookup"><span data-stu-id="8ca9b-112">In the **Authorization** section, set the roles value to the name of the A4SWIFT users group.</span></span>
