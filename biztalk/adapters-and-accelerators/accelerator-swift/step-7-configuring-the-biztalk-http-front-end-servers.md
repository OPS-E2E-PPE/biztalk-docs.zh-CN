---
title: "步骤 7： 配置 BizTalk HTTP 前端服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, HTTP servers
- HTTP server, configuring
ms.assetid: 6b7e0b48-bb20-42f4-84a5-092ff3a02741
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5840099816149265711744373e08d3a9a9d91cd0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-configuring-the-biztalk-http-front-end-servers"></a><span data-ttu-id="f619a-102">步骤 7： 配置 BizTalk HTTP 前端服务器</span><span class="sxs-lookup"><span data-stu-id="f619a-102">Step 7: Configuring the BizTalk HTTP Front-End Servers</span></span>
<span data-ttu-id="f619a-103">本部分提供有关配置 Web 服务器中的准则你[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]部署。</span><span class="sxs-lookup"><span data-stu-id="f619a-103">This section provides guidelines on configuring the Web servers in your [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] deployment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f619a-104">在单台计算机部署中，此计算机是同一台计算机作为一个执行消息传送和处理。</span><span class="sxs-lookup"><span data-stu-id="f619a-104">In the single-computer deployment, this computer is the same computer as the one that does the messaging and processing.</span></span>  
  
### <a name="to-configure-the-biztalk-http-front-end-servers"></a><span data-ttu-id="f619a-105">若要配置 BizTalk HTTP 前端服务器</span><span class="sxs-lookup"><span data-stu-id="f619a-105">To configure the BizTalk HTTP front-end servers</span></span>  
  
1.  <span data-ttu-id="f619a-106">安装 Internet 信息服务 (IIS) 和 ASP.NET。</span><span class="sxs-lookup"><span data-stu-id="f619a-106">Install Internet Information Services (IIS) and ASP.NET.</span></span>  
  
2.  <span data-ttu-id="f619a-107">打开 IIS 管理器，然后选择**Web 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="f619a-107">Open IIS Manager and select **Web Service Extensions**.</span></span> <span data-ttu-id="f619a-108">确保 ASP.NET 1.1 版和 ASP.NET 2.0 版设置为**允许**。</span><span class="sxs-lookup"><span data-stu-id="f619a-108">Ensure that ASP.NET v1.1 and ASP.NET v2.0 are set to **Allowed**.</span></span>  
  
3.  <span data-ttu-id="f619a-109">确保**消息队列**与服务 (MSMQ)**路由支持**从添加/删除安装[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]下应用程序服务器/消息队列的组件。</span><span class="sxs-lookup"><span data-stu-id="f619a-109">Ensure that the **Message Queuing** service (MSMQ) with **Routing Support** is installed from the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under Application Server/Message Queuing.</span></span>  
  
4.  <span data-ttu-id="f619a-110">确保启用了网络 DTC 访问中添加/删除[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]应用程序服务器类别下的组件。</span><span class="sxs-lookup"><span data-stu-id="f619a-110">Ensure that Network DTC access is enabled in the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under the Application Server category.</span></span> <span data-ttu-id="f619a-111">在上启用网络 DTC 客户端访问[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前面步骤中的计算机。</span><span class="sxs-lookup"><span data-stu-id="f619a-111">Network DTC client access was enabled on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer in an earlier step.</span></span>  
  
5.  <span data-ttu-id="f619a-112">在你部署中，实现安全套接字层 (SSL) 协议中所述[支持安全套接字层 (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)。</span><span class="sxs-lookup"><span data-stu-id="f619a-112">Implement the Secure Sockets Layer (SSL) protocol in your deployment, as described in [Supporting Secure Sockets Layer (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md).</span></span>  
  
6.  <span data-ttu-id="f619a-113">安装和配置 Windows SharePoint Services 3.0 SP1。</span><span class="sxs-lookup"><span data-stu-id="f619a-113">Install and configure Windows SharePoint Services 3.0 SP1.</span></span>  
  
7.  <span data-ttu-id="f619a-114">安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]中所述[安装和配置 BizTalk Accelerator for HTTP 前端服务器上的 SWIFT](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="f619a-114">Install and configure [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as described in [Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md).</span></span>  
  
 <span data-ttu-id="f619a-115">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="f619a-115">This section contains:</span></span>  
  
-   [<span data-ttu-id="f619a-116">支持安全套接字层 (SSL)</span><span class="sxs-lookup"><span data-stu-id="f619a-116">Supporting Secure Sockets Layer (SSL)</span></span>](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)  
  
-   [<span data-ttu-id="f619a-117">安装和配置 BizTalk HTTP 前端服务器</span><span class="sxs-lookup"><span data-stu-id="f619a-117">Installing and Configuring BizTalk HTTP Front-End Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)  
  
-   [<span data-ttu-id="f619a-118">安装和配置 BizTalk Accelerator for SWIFT HTTP 前端服务器上</span><span class="sxs-lookup"><span data-stu-id="f619a-118">Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-http-front-end-servers.md)