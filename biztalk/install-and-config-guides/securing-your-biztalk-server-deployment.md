---
title: 你部署的安全概述 |Microsoft Docs
description: 有关安全、 加密、 BizTalk Server 部署中的用户组的快速链接
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1c5a000-9f6b-49db-bd87-8c694240a192
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cd2a0d0b298a395aaf05a8f00192d2a6e860804
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399375"
---
# <a name="securing-your-biztalk-server-deployment"></a><span data-ttu-id="8d801-103">保护 BizTalk Server 部署</span><span class="sxs-lookup"><span data-stu-id="8d801-103">Securing Your BizTalk Server Deployment</span></span>
<span data-ttu-id="8d801-104">已安装并配置 BizTalk 后，在本部分中的主题提供有关配置防火墙端口、 Internet 协议安全性 (IPSec) 和安全套接字层 (SSL) 安全的链接。</span><span class="sxs-lookup"><span data-stu-id="8d801-104">The topics in this section provide the links about configuring firewall ports, Internet protocol security (IPSec), and secure sockets layer (SSL) security after you have installed and configured BizTalk.</span></span>  
  
- <span data-ttu-id="8d801-105">有关如何在 Web 服务器中实施 SSL 的详细信息，请参阅[ http://go.microsoft.com/fwlink/p/?LinkId=193059 ](http://go.microsoft.com/fwlink/p/?LinkId=193059)。</span><span class="sxs-lookup"><span data-stu-id="8d801-105">For more information about how to implement SSL in a Web server, see [http://go.microsoft.com/fwlink/p/?LinkId=193059](http://go.microsoft.com/fwlink/p/?LinkId=193059).</span></span>  
  
- <span data-ttu-id="8d801-106">有关如何启用 SQL Server 及其客户端，例如处理服务器和管理客户端之间的加密的详细信息，请参阅[透明数据加密 (TDE)](https://msdn.microsoft.com/library/bb934049.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8d801-106">For more information about how to enable encryption between SQL Server and its clients such as processing servers and administration clients, see [Transparent Data Encryption (TDE)](https://msdn.microsoft.com/library/bb934049.aspx).</span></span>  
  
- <span data-ttu-id="8d801-107">有关如何配置你的本地服务器的身份管理的详细信息，请参阅[Identity Manager ](https://docs.microsoft.com/microsoft-identity-manager/)。</span><span class="sxs-lookup"><span data-stu-id="8d801-107">For more information about how to configure identity management for your on-premises servers, see [Identity Manager ](https://docs.microsoft.com/microsoft-identity-manager/).</span></span>  
  
  <span data-ttu-id="8d801-108">除了此部分中的主题，则应该查看以下信息：</span><span class="sxs-lookup"><span data-stu-id="8d801-108">In addition to the topics in this section, you should review the following information:</span></span>  
  
- <span data-ttu-id="8d801-109">有关规划和维护安全部署的概念信息，请参阅[Planning for Security](../core/planning-for-security.md)。</span><span class="sxs-lookup"><span data-stu-id="8d801-109">For conceptual information about planning and maintaining a secure deployment, see [Planning for Security](../core/planning-for-security.md).</span></span>  
  
- <span data-ttu-id="8d801-110">为管理员和系统用户配置访问权限的信息，请参阅[管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md)。</span><span class="sxs-lookup"><span data-stu-id="8d801-110">For information about configuring access for administrators and system users, see [Managing BizTalk Server Security](../core/managing-biztalk-server-security.md).</span></span>  
  
- <span data-ttu-id="8d801-111">有关 BizTalk Server 中的安全功能的详细信息，请参阅[安全和保护你的 BizTalk 消息](../core/secure-and-protect-your-biztalk-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8d801-111">For more information about security features in BizTalk Server, see [Secure and protect your BizTalk messages](../core/secure-and-protect-your-biztalk-messages.md).</span></span>  
  
- <span data-ttu-id="8d801-112">有关如何实现安全消息的详细信息，请参阅[实施消息安全性](../core/implementing-message-security.md)。</span><span class="sxs-lookup"><span data-stu-id="8d801-112">For more information about how to implement secure messages, see [Implementing Message Security](../core/implementing-message-security.md).</span></span>  
  
- <span data-ttu-id="8d801-113">有关 Windows 组和 BizTalk Server 使用的用户帐户的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8d801-113">For more information about Windows groups and user accounts that BizTalk Server uses, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
## <a name="additional-configuration-topics"></a><span data-ttu-id="8d801-114">其他配置主题</span><span class="sxs-lookup"><span data-stu-id="8d801-114">Additional Configuration Topics</span></span>  
 
 [<span data-ttu-id="8d801-115">配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8d801-115">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
 [<span data-ttu-id="8d801-116">在 Azure VM 上配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8d801-116">Configuring BizTalk Server on an Azure VM</span></span>](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
[<span data-ttu-id="8d801-117">在群集中配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8d801-117">Configure BizTalk Server in a Cluster</span></span>](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)
    
  
## <a name="see-also"></a><span data-ttu-id="8d801-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d801-118">See Also</span></span>  
 <span data-ttu-id="8d801-119">[访问控制和数据安全性](../core/access-control-and-data-security.md) </span><span class="sxs-lookup"><span data-stu-id="8d801-119">[Access Control and Data Security](../core/access-control-and-data-security.md) </span></span>  
 <span data-ttu-id="8d801-120">[最低安全用户权限](../core/minimum-security-user-rights.md) </span><span class="sxs-lookup"><span data-stu-id="8d801-120">[Minimum Security User Rights](../core/minimum-security-user-rights.md) </span></span>  
 <span data-ttu-id="8d801-121">[规划安全性](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="8d801-121">[Planning for Security](../core/planning-for-security.md) </span></span>  
 [<span data-ttu-id="8d801-122">为 BizTalk Server 设计系统体系结构</span><span class="sxs-lookup"><span data-stu-id="8d801-122">Designing the System Architectures for BizTalk Server</span></span>](../core/designing-the-system-architectures-for-biztalk-server.md)   
