---
title: 安装和配置 BizTalk Server 业务流程服务器上 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on orchestration server
- orchestration server, installing BizTalk Server
ms.assetid: 72376a80-1377-4058-9478-fee668b804d0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecd5e9e4be9c9274a402b54a5bf6a2eba4ed73cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984094"
---
# <a name="installing-and-configuring-biztalk-server-on-the-orchestration-servers"></a><span data-ttu-id="3170f-102">安装和配置 BizTalk Server 业务流程服务器上</span><span class="sxs-lookup"><span data-stu-id="3170f-102">Installing and Configuring BizTalk Server on the Orchestration Servers</span></span>
<span data-ttu-id="3170f-103">本部分介绍如何安装和配置 BizTalk Server 以便用作运行消息修复 / 新建提交业务流程以及 FIN 修复和对帐业务流程的业务流程服务器。</span><span class="sxs-lookup"><span data-stu-id="3170f-103">This section describes how to install and configure BizTalk Server to be used as the orchestration server for running the Message Repair/New Submission orchestration and the FIN Repair and Reconciliation orchestration.</span></span>  

### <a name="to-install-and-configure-biztalk-server-on-the-orchestration-server"></a><span data-ttu-id="3170f-104">若要安装和配置 BizTalk Server 业务流程服务器上</span><span class="sxs-lookup"><span data-stu-id="3170f-104">To install and configure BizTalk Server on the Orchestration Server</span></span>  

1. <span data-ttu-id="3170f-105">执行的自定义安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]选择除 EDI、 工作流服务 (HWS) 和 MRSR，之外的所有功能，除非所需的其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="3170f-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing all the features except EDI, Human Workflow Services (HWS), and MRSR, unless required by other applications.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3170f-106">在单台计算机部署中，此计算机是运行 HTTP 前端服务和 BizTalk 消息传送服务器所在的计算机。</span><span class="sxs-lookup"><span data-stu-id="3170f-106">In the single-computer deployment, this computer is the same computer as the one that runs the HTTP front-end service and the BizTalk Messaging server.</span></span>  

2. <span data-ttu-id="3170f-107">执行的配置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3170f-107">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3170f-108">配置 BizTalk 业务流程服务器时，请考虑以下准则：</span><span class="sxs-lookup"><span data-stu-id="3170f-108">Consider the following guidelines when configuring the BizTalk Orchestration servers:</span></span>  

   - <span data-ttu-id="3170f-109">此服务器要求只有一个网络适配器，以将其连接到[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="3170f-109">This server requires only one network adapter to connect it to the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer.</span></span> <span data-ttu-id="3170f-110">它不需要像 HTTP 前端服务器或消息服务器的公共一端的另一个网络适配器并这使其更加安全，免受黑客攻击企图来自 Internet 或内部和外部。</span><span class="sxs-lookup"><span data-stu-id="3170f-110">It does not require another network adapter on the public side like the HTTP front-end server or the messaging server, and this makes it more secure against hacking attempts coming from the Internet or intranet/extranet.</span></span>  

3. <span data-ttu-id="3170f-111">安装所需的任何其他修补程序[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]安装指南中为可用。</span><span class="sxs-lookup"><span data-stu-id="3170f-111">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span>
