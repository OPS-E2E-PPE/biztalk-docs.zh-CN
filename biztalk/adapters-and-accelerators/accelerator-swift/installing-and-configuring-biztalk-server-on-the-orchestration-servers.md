---
title: 上安装和配置 BizTalk Server 业务流程服务器 |Microsoft 文档
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
ms.openlocfilehash: 18a13d553e31739c959ff6baf317240c3c268ecc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004206"
---
# <a name="installing-and-configuring-biztalk-server-on-the-orchestration-servers"></a><span data-ttu-id="936a7-102">安装和配置 BizTalk Server 业务流程服务器上</span><span class="sxs-lookup"><span data-stu-id="936a7-102">Installing and Configuring BizTalk Server on the Orchestration Servers</span></span>
<span data-ttu-id="936a7-103">本部分介绍如何安装和配置 BizTalk Server 以用于与业务流程服务器运行消息修复/新建提交业务流程和 FIN 修复和对帐业务流程。</span><span class="sxs-lookup"><span data-stu-id="936a7-103">This section describes how to install and configure BizTalk Server to be used as the orchestration server for running the Message Repair/New Submission orchestration and the FIN Repair and Reconciliation orchestration.</span></span>  
  
### <a name="to-install-and-configure-biztalk-server-on-the-orchestration-server"></a><span data-ttu-id="936a7-104">若要安装和配置 BizTalk Server 业务流程服务器上</span><span class="sxs-lookup"><span data-stu-id="936a7-104">To install and configure BizTalk Server on the Orchestration Server</span></span>  
  
1.  <span data-ttu-id="936a7-105">执行的自定义安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]选择除 EDI、 人工工作流服务 （工作流服务） 和 MRSR，以外的所有功能，除非所需的其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="936a7-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing all the features except EDI, Human Workflow Services (HWS), and MRSR, unless required by other applications.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="936a7-106">在单台计算机部署中，此计算机是为运行 HTTP 前端服务和 BizTalk 消息传送服务器在同一台计算机。</span><span class="sxs-lookup"><span data-stu-id="936a7-106">In the single-computer deployment, this computer is the same computer as the one that runs the HTTP front-end service and the BizTalk Messaging server.</span></span>  
  
2.  <span data-ttu-id="936a7-107">执行配置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="936a7-107">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="936a7-108">配置 BizTalk 业务流程服务器时，请考虑以下准则：</span><span class="sxs-lookup"><span data-stu-id="936a7-108">Consider the following guidelines when configuring the BizTalk Orchestration servers:</span></span>  
  
    -   <span data-ttu-id="936a7-109">此服务器要求只有一个网络适配器连接到[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="936a7-109">This server requires only one network adapter to connect it to the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer.</span></span> <span data-ttu-id="936a7-110">它不需要另一个网络适配器，如 HTTP 前端服务器或消息服务器的公共端并这使其更利于防止黑客攻击来自 Internet 或 intranet/extranet 的企图。</span><span class="sxs-lookup"><span data-stu-id="936a7-110">It does not require another network adapter on the public side like the HTTP front-end server or the messaging server, and this makes it more secure against hacking attempts coming from the Internet or intranet/extranet.</span></span>  
  
3.  <span data-ttu-id="936a7-111">安装所需的任何其他修补程序[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]为可安装指南中。</span><span class="sxs-lookup"><span data-stu-id="936a7-111">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span>