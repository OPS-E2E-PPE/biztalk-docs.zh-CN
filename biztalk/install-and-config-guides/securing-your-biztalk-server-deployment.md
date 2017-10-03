---
title: "你部署的安全概述 |Microsoft 文档"
description: "有关安全性、 加密、 你的 BizTalk Server 部署中的用户组的快速链接"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1c5a000-9f6b-49db-bd87-8c694240a192
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf5ff5db17739e2db407bdb52bd3f9aad4e61b74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="securing-your-biztalk-server-deployment"></a><span data-ttu-id="f7921-103">确保 BizTalk Server 部署的安全</span><span class="sxs-lookup"><span data-stu-id="f7921-103">Securing Your BizTalk Server Deployment</span></span>
<span data-ttu-id="f7921-104">本部分中的主题提供有关配置防火墙端口、Internet 协议安全性 (IPSec)、安全套接字层 (SSL) 安全性的链接（完成了 BizTalk 的安装和配置之后）。</span><span class="sxs-lookup"><span data-stu-id="f7921-104">The topics in this section provide the links about configuring firewall ports, Internet protocol security (IPSec), and secure sockets layer (SSL) security after you have installed and configured BizTalk.</span></span>  
  
-   <span data-ttu-id="f7921-105">有关如何在 Web 服务器中实施 SSL 的详细信息，请参阅 [http://go.microsoft.com/fwlink/p/?LinkId=193059](http://go.microsoft.com/fwlink/p/?LinkId=193059)。</span><span class="sxs-lookup"><span data-stu-id="f7921-105">For more information about how to implement SSL in a Web server, see [http://go.microsoft.com/fwlink/p/?LinkId=193059](http://go.microsoft.com/fwlink/p/?LinkId=193059).</span></span>  
  
-   <span data-ttu-id="f7921-106">有关如何在 SQL Server 及其客户端（例如处理服务器和管理客户端）之间启用加密的详细信息，请参阅 [透明数据加密 (TDE)](https://msdn.microsoft.com/library/bb934049.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f7921-106">For more information about how to enable encryption between SQL Server and its clients such as processing servers and administration clients, see [Transparent Data Encryption (TDE)](https://msdn.microsoft.com/library/bb934049.aspx).</span></span>  
  
-   <span data-ttu-id="f7921-107">有关如何配置本地服务器的标识管理的详细信息，请参阅[标识管理器](https://docs.microsoft.com/microsoft-identity-manager/)。</span><span class="sxs-lookup"><span data-stu-id="f7921-107">For more information about how to configure identity management for your on-premises servers, see [Identity Manager ](https://docs.microsoft.com/microsoft-identity-manager/).</span></span>  
  
 <span data-ttu-id="f7921-108">除了本部分中的主题之外，你应该查看以下信息：</span><span class="sxs-lookup"><span data-stu-id="f7921-108">In addition to the topics in this section, you should review the following information:</span></span>  
  
-   <span data-ttu-id="f7921-109">有关规划和维护安全部署的概念信息，请参阅[规划安全性](../core/planning-for-security.md)。</span><span class="sxs-lookup"><span data-stu-id="f7921-109">For conceptual information about planning and maintaining a secure deployment, see [Planning for Security](../core/planning-for-security.md).</span></span>  
  
-   <span data-ttu-id="f7921-110">有关为管理员和系统用户配置访问权限的信息，请参阅[管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md)。</span><span class="sxs-lookup"><span data-stu-id="f7921-110">For information about configuring access for administrators and system users, see [Managing BizTalk Server Security](../core/managing-biztalk-server-security.md).</span></span>  
  
-   <span data-ttu-id="f7921-111">有关 BizTalk Server 中安全功能的详细信息，请参阅[保护你的 BizTalk 消息](../core/secure-and-protect-your-biztalk-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="f7921-111">For more information about security features in BizTalk Server, see [Secure and protect your BizTalk messages](../core/secure-and-protect-your-biztalk-messages.md).</span></span>  
  
-   <span data-ttu-id="f7921-112">有关如何实现安全消息的详细信息，请参阅[实施消息安全性](../core/implementing-message-security.md)。</span><span class="sxs-lookup"><span data-stu-id="f7921-112">For more information about how to implement secure messages, see [Implementing Message Security](../core/implementing-message-security.md).</span></span>  
  
-   <span data-ttu-id="f7921-113">有关 BizTalk Server 使用的 Windows 组和用户帐户的详细信息，请参阅 [BizTalk Server 中的 Windows 组和用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="f7921-113">For more information about Windows groups and user accounts that BizTalk Server uses, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
## <a name="additional-configuration-topics"></a><span data-ttu-id="f7921-114">其他配置主题</span><span class="sxs-lookup"><span data-stu-id="f7921-114">Additional Configuration Topics</span></span>  
 
 [<span data-ttu-id="f7921-115">配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f7921-115">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
 [<span data-ttu-id="f7921-116">在 Azure VM 上配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f7921-116">Configuring BizTalk Server on an Azure VM</span></span>](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
[<span data-ttu-id="f7921-117">在群集中配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f7921-117">Configure BizTalk Server in a Cluster</span></span>](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)
    
  
## <a name="see-also"></a><span data-ttu-id="f7921-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7921-118">See Also</span></span>  
 <span data-ttu-id="f7921-119">[访问控制和数据安全性](../core/access-control-and-data-security.md) </span><span class="sxs-lookup"><span data-stu-id="f7921-119">[Access Control and Data Security](../core/access-control-and-data-security.md) </span></span>  
 <span data-ttu-id="f7921-120">[最低安全用户权限](../core/minimum-security-user-rights.md) </span><span class="sxs-lookup"><span data-stu-id="f7921-120">[Minimum Security User Rights](../core/minimum-security-user-rights.md) </span></span>  
 <span data-ttu-id="f7921-121">[规划安全性](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="f7921-121">[Planning for Security](../core/planning-for-security.md) </span></span>  
 [<span data-ttu-id="f7921-122">设计 BizTalk Server 的系统结构</span><span class="sxs-lookup"><span data-stu-id="f7921-122">Designing the System Architectures for BizTalk Server</span></span>](../core/designing-the-system-architectures-for-biztalk-server.md)   
