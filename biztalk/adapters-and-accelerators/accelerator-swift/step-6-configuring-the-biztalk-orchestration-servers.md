---
title: "步骤 6： 配置 BizTalk 业务流程服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestration server, configuring
- configuring, orchestration servers
ms.assetid: 1eb38fac-264d-4730-b16b-572dbb6fabd9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e495be91cc80e072f58a1e8149feb64773f1e51
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="step-6-configuring-the-biztalk-orchestration-servers"></a><span data-ttu-id="90afa-102">步骤 6： 配置 BizTalk 业务流程服务器</span><span class="sxs-lookup"><span data-stu-id="90afa-102">Step 6: Configuring the BizTalk Orchestration Servers</span></span>
<span data-ttu-id="90afa-103">本节提供有关将 BizTalk 业务流程服务器配置的准则。</span><span class="sxs-lookup"><span data-stu-id="90afa-103">This section provides guidelines on configuring the BizTalk Orchestration servers.</span></span>  
  
### <a name="to-configure-the-biztalk-orchestration-servers"></a><span data-ttu-id="90afa-104">若要配置 BizTalk 业务流程服务器</span><span class="sxs-lookup"><span data-stu-id="90afa-104">To configure the BizTalk Orchestration servers</span></span>  
  
1.  <span data-ttu-id="90afa-105">通过选择添加/删除从启用网络分布式事务处理协调器 (DTC) 访问[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]应用程序服务器类别下的组件。</span><span class="sxs-lookup"><span data-stu-id="90afa-105">Enable Network Distributed Transaction Coordinator (DTC) access by selecting it from the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under the Application Server category.</span></span> <span data-ttu-id="90afa-106">在上启用网络 DTC 客户端访问[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前面步骤中的计算机。</span><span class="sxs-lookup"><span data-stu-id="90afa-106">Network DTC client access was enabled on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer in an earlier step.</span></span> <span data-ttu-id="90afa-107">请参阅以下知识库文章[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]有关 DTC 问题疑难解答信息的帮助和支持网站：</span><span class="sxs-lookup"><span data-stu-id="90afa-107">See the following Knowledge Base articles on the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Help and Support Web site for information about troubleshooting DTC issues:</span></span>  
  
    -   <span data-ttu-id="90afa-108">如何为解决 MS DTC 防火墙问题，位于[http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870)。</span><span class="sxs-lookup"><span data-stu-id="90afa-108">How To Troubleshoot MS DTC Firewall Issues, located at [http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870).</span></span>  
  
    -   <span data-ttu-id="90afa-109">如何为使用 DTCTester 工具，位于[http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871)。</span><span class="sxs-lookup"><span data-stu-id="90afa-109">How To Use DTCTester Tool, located at [http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871).</span></span>  
  
    -   <span data-ttu-id="90afa-110">如果 DTC 位于防火墙后面，请参阅配置[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]分布式事务处理协调器 (DTC) 到工作通过防火墙，位于[http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872)。</span><span class="sxs-lookup"><span data-stu-id="90afa-110">If DTC is behind a firewall, see Configuring [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Distributed Transaction Coordinator (DTC) to Work Through a Firewall, located at [http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872).</span></span>  
  
2.  <span data-ttu-id="90afa-111">安装其他软件的先决条件 BizTalk Server 中，以及安装和配置 BizTalk Server 中所述[安装和业务流程服务器上配置 BizTalk Server](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="90afa-111">Install additional software prerequisites for BizTalk Server, and install and configure BizTalk Server, as described in [Installing and Configuring BizTalk Server on the Orchestration Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md).</span></span>  
  
3.  <span data-ttu-id="90afa-112">安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]安装中所述和[安装和配置 BizTalk Accelerator for 消息传送服务器上的 SWIFT](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="90afa-112">Install and configure [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as described in Installing and [Installing and Configuring BizTalk Accelerator for SWIFT on Messaging Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).</span></span>  
  
 <span data-ttu-id="90afa-113">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="90afa-113">This section contains:</span></span>  
  
-   [<span data-ttu-id="90afa-114">在业务流程服务器上安装和配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="90afa-114">Installing and Configuring BizTalk Server on the Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)  
  
-   [<span data-ttu-id="90afa-115">在业务流程服务器上安装和配置 BizTalk Accelerator for SWIFT</span><span class="sxs-lookup"><span data-stu-id="90afa-115">Installing and Configuring BizTalk Accelerator for SWIFT on Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-orchestration-servers.md)