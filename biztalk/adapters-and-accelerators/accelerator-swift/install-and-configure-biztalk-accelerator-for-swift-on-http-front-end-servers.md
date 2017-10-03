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
ms.openlocfilehash: fe0a320f9f60f72975faf903c1355b8730840b26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-http-front-end-servers"></a><span data-ttu-id="29138-102">安装和配置 BizTalk Accelerator for SWIFT HTTP 前端服务器上</span><span class="sxs-lookup"><span data-stu-id="29138-102">Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers</span></span>
<span data-ttu-id="29138-103">本部分介绍如何安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]HTTP 前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="29138-103">This section describes how to install and configure [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] on the HTTP front-end servers.</span></span> <span data-ttu-id="29138-104">这些服务器主要用于与 SWIFT 网络进行通信。</span><span class="sxs-lookup"><span data-stu-id="29138-104">These servers are mainly used to communicate with the SWIFT Network.</span></span>  
  
### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-http-front-end-server"></a><span data-ttu-id="29138-105">若要安装和配置 BizTalk Accelerator for SWIFT HTTP 前端服务器上</span><span class="sxs-lookup"><span data-stu-id="29138-105">To install and configure BizTalk Accelerator for SWIFT on the HTTP front-end server</span></span>  
  
1.  <span data-ttu-id="29138-106">执行的自定义安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="29138-106">Perform a Custom Install of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="29138-107">安装**MRSR**和**用于消息修复和新提交的 Web 组件**功能。</span><span class="sxs-lookup"><span data-stu-id="29138-107">Install the **MRSR** and **Web Components for Message Repair and New Submission** features.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="29138-108">安装完成后，将启动配置向导。</span><span class="sxs-lookup"><span data-stu-id="29138-108">After installation is complete, the Configuration Wizard starts.</span></span>  
  
2.  <span data-ttu-id="29138-109">在 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置控制台中，配置**MCRR**和**WebService**。</span><span class="sxs-lookup"><span data-stu-id="29138-109">In the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console, configure **MCRR** and **WebService**.</span></span>  
  
3.  <span data-ttu-id="29138-110">完成配置向导，在 Web 服务器上之后, 在文件夹中打开 web.config 文件\<*驱动器*>: files\microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ 在记事本中的。</span><span class="sxs-lookup"><span data-stu-id="29138-110">After completing the Configuration Wizard, on the Web servers, open the web.config file in the folder \<*Drive*>:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ in Notepad.</span></span> <span data-ttu-id="29138-111">搜索"授权"。</span><span class="sxs-lookup"><span data-stu-id="29138-111">Search for "Authorization".</span></span> <span data-ttu-id="29138-112">在**授权**部分中，将角色值设置为 A4SWIFT 用户组的名称。</span><span class="sxs-lookup"><span data-stu-id="29138-112">In the **Authorization** section, set the roles value to the name of the A4SWIFT users group.</span></span>