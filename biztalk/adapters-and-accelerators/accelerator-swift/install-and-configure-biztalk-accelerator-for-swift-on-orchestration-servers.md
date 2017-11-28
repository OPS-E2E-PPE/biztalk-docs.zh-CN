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
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-orchestration-servers"></a><span data-ttu-id="83134-102">安装和配置 BizTalk Accelerator for SWIFT Orchestration 服务器上</span><span class="sxs-lookup"><span data-stu-id="83134-102">Installing and Configuring BizTalk Accelerator for SWIFT on Orchestration Servers</span></span>
<span data-ttu-id="83134-103">本部分介绍如何安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]orchestration 服务器上。</span><span class="sxs-lookup"><span data-stu-id="83134-103">This section describes how to install and configure [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] on the orchestration servers.</span></span> <span data-ttu-id="83134-104">这些服务器主要用于运行 FIN 修复和调节业务流程和消息修复/新建提交业务流程。</span><span class="sxs-lookup"><span data-stu-id="83134-104">These servers are mainly used to run the FIN Repair and Reconciliation orchestration and the Message Repair/New Submission orchestration.</span></span>  
  
### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-orchestration-server"></a><span data-ttu-id="83134-105">若要安装和配置 BizTalk Accelerator for SWIFT orchestration 服务器上</span><span class="sxs-lookup"><span data-stu-id="83134-105">To install and configure BizTalk Accelerator for SWIFT on the orchestration server</span></span>  
  
1.  <span data-ttu-id="83134-106">执行的自定义安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="83134-106">Perform a Custom Install of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="83134-107">安装**MRSR**功能。</span><span class="sxs-lookup"><span data-stu-id="83134-107">Install the **MRSR** feature.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83134-108">不需要安装 Web 组件消息修复和新提交功能，因为此服务器没有 MRSR 站点。</span><span class="sxs-lookup"><span data-stu-id="83134-108">You do not need to install the Web Components for Message Repair and New Submission feature because this server does not have MRSR site.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83134-109">安装完成后，将启动配置向导。</span><span class="sxs-lookup"><span data-stu-id="83134-109">After installation is complete, the Configuration Wizard starts.</span></span>  
  
2.  <span data-ttu-id="83134-110">在 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置控制台中，配置**MCRR**。</span><span class="sxs-lookup"><span data-stu-id="83134-110">In the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console, configure **MCRR**.</span></span>