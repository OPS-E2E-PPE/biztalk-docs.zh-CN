---
title: 安装和配置 BizTalk Accelerator for SWIFT 消息服务器上 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Accelerator for SWIFT, configuring
- BizTalk Accelerator for SWIFT, installing on Messaging servers
- BizTalk Messaging servers, installing BizTalk Accelerator for SWIFT
ms.assetid: 7a8f60aa-5ff2-4584-9d4a-dc4a0ba61aca
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 459a0fd7524b373104406a013c407a82d447966c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377423"
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers"></a><span data-ttu-id="b1707-102">安装和配置 BizTalk Accelerator for SWIFT 消息服务器上</span><span class="sxs-lookup"><span data-stu-id="b1707-102">Installing and Configuring BizTalk Accelerator for SWIFT on Messaging Servers</span></span>
<span data-ttu-id="b1707-103">本部分介绍如何安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]消息传送的服务器上。</span><span class="sxs-lookup"><span data-stu-id="b1707-103">This section describes how to install and configure [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] on the messaging servers.</span></span> <span data-ttu-id="b1707-104">这些服务器主要用于与 SWIFT 网络进行通信。</span><span class="sxs-lookup"><span data-stu-id="b1707-104">These servers are mainly used to communicate with the SWIFT Network.</span></span>  

### <a name="to-install-and-configure-biztalk-accelerator-for-a4swift-on-the-messaging-server"></a><span data-ttu-id="b1707-105">若要安装和配置 BizTalk Accelerator for A4SWIFT 消息传送服务器上</span><span class="sxs-lookup"><span data-stu-id="b1707-105">To install and configure BizTalk Accelerator for A4SWIFT on the Messaging Server</span></span>  

1. <span data-ttu-id="b1707-106">执行的自定义安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b1707-106">Perform a Custom Install of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="b1707-107">安装**MRSR**并**SWIFT 消息**功能。</span><span class="sxs-lookup"><span data-stu-id="b1707-107">Install the **MRSR** and **SWIFT Messages** features.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b1707-108">不需要安装用于消息修复和新提交的功能的 Web 组件，因为此服务器没有 MRSR 站点。</span><span class="sxs-lookup"><span data-stu-id="b1707-108">You do not need to install the Web Components for Message Repair and New Submission feature because this server does not have MRSR site.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b1707-109">安装完成后，将启动配置向导。</span><span class="sxs-lookup"><span data-stu-id="b1707-109">After installation is complete, the Configuration Wizard starts.</span></span>  

2. <span data-ttu-id="b1707-110">在 microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置控制台中，配置**MCRR**。</span><span class="sxs-lookup"><span data-stu-id="b1707-110">In the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console, configure **MCRR**.</span></span>
