---
title: 步骤 6：配置 BizTalk 业务流程服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration server, configuring
- configuring, orchestration servers
ms.assetid: 1eb38fac-264d-4730-b16b-572dbb6fabd9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59b1eea5ca26e951f25ebda75a09941afba6fabf
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530105"
---
# <a name="step-6-configuring-the-biztalk-orchestration-servers"></a><span data-ttu-id="5f4cd-102">步骤 6：配置 BizTalk 业务流程服务器</span><span class="sxs-lookup"><span data-stu-id="5f4cd-102">Step 6: Configuring the BizTalk Orchestration Servers</span></span>
<span data-ttu-id="5f4cd-103">本部分提供有关配置 BizTalk 业务流程服务器的指导原则。</span><span class="sxs-lookup"><span data-stu-id="5f4cd-103">This section provides guidelines on configuring the BizTalk Orchestration servers.</span></span>  
  
### <a name="to-configure-the-biztalk-orchestration-servers"></a><span data-ttu-id="5f4cd-104">若要配置 BizTalk 业务流程服务器</span><span class="sxs-lookup"><span data-stu-id="5f4cd-104">To configure the BizTalk Orchestration servers</span></span>  
  
1. <span data-ttu-id="5f4cd-105">通过选择添加/删除从启用网络分布式事务处理协调器 (DTC) 访问[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]类别下的应用程序服务器组件。</span><span class="sxs-lookup"><span data-stu-id="5f4cd-105">Enable Network Distributed Transaction Coordinator (DTC) access by selecting it from the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under the Application Server category.</span></span> <span data-ttu-id="5f4cd-106">已启用网络 DTC 客户端访问在[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前面步骤中的计算机。</span><span class="sxs-lookup"><span data-stu-id="5f4cd-106">Network DTC client access was enabled on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer in an earlier step.</span></span> <span data-ttu-id="5f4cd-107">有关 DTC 问题故障排除信息 Microsoft 帮助和支持网站上，请参阅以下知识库文章：</span><span class="sxs-lookup"><span data-stu-id="5f4cd-107">See the following Knowledge Base articles on the Microsoft Help and Support Web site for information about troubleshooting DTC issues:</span></span>  
  
   - <span data-ttu-id="5f4cd-108">如何为进行故障排除 MS DTC 防火墙问题，位于[ http://go.microsoft.com/fwlink/?linkid=48870 ](http://go.microsoft.com/fwlink/?linkid=48870)。</span><span class="sxs-lookup"><span data-stu-id="5f4cd-108">How To Troubleshoot MS DTC Firewall Issues, located at [http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870).</span></span>  
  
   - <span data-ttu-id="5f4cd-109">如何使用 DTCTester 工具，位于[ http://go.microsoft.com/fwlink/?linkid=48871 ](http://go.microsoft.com/fwlink/?linkid=48871)。</span><span class="sxs-lookup"><span data-stu-id="5f4cd-109">How To Use DTCTester Tool, located at [http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871).</span></span>  
  
   - <span data-ttu-id="5f4cd-110">如果 DTC 防火墙后面，请参阅配置 Microsoft 分布式事务处理协调器 (DTC) 为通过防火墙工作，位于[ http://go.microsoft.com/fwlink/?linkid=48872 ](http://go.microsoft.com/fwlink/?linkid=48872)。</span><span class="sxs-lookup"><span data-stu-id="5f4cd-110">If DTC is behind a firewall, see Configuring Microsoft Distributed Transaction Coordinator (DTC) to Work Through a Firewall, located at [http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872).</span></span>  
  
2. <span data-ttu-id="5f4cd-111">安装 BizTalk Server 的其他软件必备组件安装和配置 BizTalk Server 中所述[安装和业务流程服务器上配置 BizTalk Server](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="5f4cd-111">Install additional software prerequisites for BizTalk Server, and install and configure BizTalk Server, as described in [Installing and Configuring BizTalk Server on the Orchestration Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md).</span></span>  
  
3. <span data-ttu-id="5f4cd-112">安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]安装中所述和[安装和配置 BizTalk Accelerator for SWIFT 消息传送服务器上](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="5f4cd-112">Install and configure [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as described in Installing and [Installing and Configuring BizTalk Accelerator for SWIFT on Messaging Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).</span></span>  
  
   <span data-ttu-id="5f4cd-113">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="5f4cd-113">This section contains:</span></span>  
  
-   [<span data-ttu-id="5f4cd-114">在业务流程服务器上安装和配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="5f4cd-114">Installing and Configuring BizTalk Server on the Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)  
  
-   [<span data-ttu-id="5f4cd-115">在业务流程服务器上安装和配置 BizTalk Accelerator for SWIFT</span><span class="sxs-lookup"><span data-stu-id="5f4cd-115">Installing and Configuring BizTalk Accelerator for SWIFT on Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-orchestration-servers.md)