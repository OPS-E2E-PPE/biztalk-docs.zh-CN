---
title: 管理 BizTalk Server 安全性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, security
- security, user accounts
- security, passwords
- certificates, security
- security, certificates
- security, BizTalk Server
- passwords, security
- user accounts, security
ms.assetid: adc89b0a-9846-4c99-b0fc-a32fc56ed769
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61612cced50d634f3ca4d71b5e29ebd3c1781009
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531152"
---
# <a name="managing-biztalk-server-security"></a><span data-ttu-id="1dfd6-102">管理 BizTalk Server 安全性</span><span class="sxs-lookup"><span data-stu-id="1dfd6-102">Managing BizTalk Server Security</span></span>
<span data-ttu-id="1dfd6-103">维护一个安全的 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境需要管理帐户、 证书和密码。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-103">Maintaining a secure Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment requires that you manage accounts, certificates, and passwords.</span></span> <span data-ttu-id="1dfd6-104">为帮助确保由 BizTalk Server 处理的业务文档的安全性，BizTalk Server 管理员管理以下帐户和证书：</span><span class="sxs-lookup"><span data-stu-id="1dfd6-104">To help ensure the security of the business documents handled by BizTalk Server, BizTalk Server administrators manage the following accounts and certificates:</span></span>  
  
- <span data-ttu-id="1dfd6-105">**BizTalk Server Administrators 组**。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-105">**BizTalk Server Administrators group**.</span></span> <span data-ttu-id="1dfd6-106">对于执行管理任务通过 BizTalk 管理控制台或通过使用 Microsoft Windows Management Instrumentation (WMI) 提供程序的用户，他们必须获得 Microsoft SQL Server 和 Microsoft Windows 中适当的权限。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-106">For users to perform administrative tasks either through the BizTalk Administration console or by using the Microsoft Windows Management Instrumentation (WMI) provider, they must be granted the proper privileges in Microsoft SQL Server and Microsoft Windows.</span></span> <span data-ttu-id="1dfd6-107">有关管理任务的权限的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-107">For more information about the privileges for administrative tasks, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span>  
  
   <span data-ttu-id="1dfd6-108">有关将用户添加到 BizTalk Server Administrators 组或从 BizTalk Server Administrators 组中删除用户的信息，请参阅[如何管理 BizTalk Server Administrators 组](../core/how-to-manage-the-biztalk-server-administrators-group.md)。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-108">For information about adding users to the BizTalk Server Administrators group or removing users from the BizTalk Server Administrators group, see [How to Manage the BizTalk Server Administrators Group](../core/how-to-manage-the-biztalk-server-administrators-group.md).</span></span>  
  
   <span data-ttu-id="1dfd6-109">有关企业单一登录的详细信息，请参阅[使用 SSO](../core/using-sso.md)。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-109">For more information about Enterprise Single Sign-On, see [Using SSO](../core/using-sso.md).</span></span>  
  
- <span data-ttu-id="1dfd6-110">**BizTalk Server Operators 组**。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-110">**BizTalk Server Operators group**.</span></span> <span data-ttu-id="1dfd6-111">BizTalk Server 操作员是仅有权访问监视和故障排除操作的低权限的角色。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-111">The BizTalk Server Operator is a low privileged role that only has access to monitoring and troubleshooting actions.</span></span>  
  
   <span data-ttu-id="1dfd6-112">BizTalk Server Operators 组的成员可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1dfd6-112">Members of the BizTalk Server Operators group can do the following:</span></span>  
  
  - <span data-ttu-id="1dfd6-113">查看服务状态和消息流。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-113">View service state and message flow.</span></span>  
  
  - <span data-ttu-id="1dfd6-114">启动或停止应用程序。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-114">Start or stop applications.</span></span>  
  
  - <span data-ttu-id="1dfd6-115">启动或停止业务流程。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-115">Start or stop orchestrations.</span></span>  
  
  - <span data-ttu-id="1dfd6-116">启动或停止发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-116">Start or stop send ports or send port groups.</span></span>  
  
  - <span data-ttu-id="1dfd6-117">启用或禁用接收位置。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-117">Enable or disable receive locations.</span></span> <span data-ttu-id="1dfd6-118">更改不会生效直到下一步的缓存刷新间隔为 60 秒，这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-118">The changes do not take effect until the next cache refresh interval of 60 seconds, which is the default.</span></span> <span data-ttu-id="1dfd6-119">在 BizTalk Server 组级别设置缓存刷新间隔。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-119">The cache refresh interval is set at the BizTalk Server group level.</span></span>  
  
  - <span data-ttu-id="1dfd6-120">终止和恢复服务实例。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-120">Terminate and resume service instances.</span></span>  
  
    <span data-ttu-id="1dfd6-121">BizTalk Server Operators 组的成员不能执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1dfd6-121">Members of the BizTalk Server Operators group cannot do the following:</span></span>  
  
  - <span data-ttu-id="1dfd6-122">修改 BizTalk Server 的配置。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-122">Modify the configuration for BizTalk Server.</span></span>  
  
  - <span data-ttu-id="1dfd6-123">查看被归类为个人身份信息 (PII) 或消息正文的消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-123">View message context properties classified as Personally Identifiable Information (PII) or message bodies.</span></span>  
  
  - <span data-ttu-id="1dfd6-124">修改消息路由，例如删除或将新的订阅添加到正在运行的系统，包括能够将消息发布到 BizTalk Server 运行时的过程。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-124">Modify the course of message routing, such as removing or adding new subscriptions to the running system, including the ability to publish messages into the BizTalk Server runtime.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="1dfd6-125">如果 BizTalk Server Operators 组的成员的用户也是运行 BizTalk Server 的计算机上的本地管理员，此用户可以访问这些计算机上的操作员组的角色之外的数据。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-125">If a user who is a member of the BizTalk Server Operators group is also a local administrator on the computers running BizTalk Server, this user can access data beyond the role of the Operators group on these computers.</span></span> <span data-ttu-id="1dfd6-126">有关详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-126">For more information, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="1dfd6-127">如果你想要允许的用户是要监控远程 BizTalk 服务器的 BizTalk Server Operators 组的成员，此用户还必须是远程计算机上的本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-127">If you want to allow a user who is a member of the BizTalk Server Operators group to monitor remote BizTalk servers, this user must also be a member of the local Administrators group on the remote computers.</span></span>  
  
- <span data-ttu-id="1dfd6-128">**主机和服务帐户**。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-128">**Hosts and service accounts**.</span></span> <span data-ttu-id="1dfd6-129">创建主机和其关联的主机实例时，必须提供主机和每个主机实例服务帐户凭据的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-129">When creating a host and its associated host instances, you must provide the Windows group for the host and the service account credentials for each host instance.</span></span> <span data-ttu-id="1dfd6-130">您必须确保主机实例服务帐户是主机 Windows 组的成员。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-130">You must ensure that the host instance service accounts are members of the Windows group for the host.</span></span>  
  
- <span data-ttu-id="1dfd6-131">**签名证书**。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-131">**Signing certificates**.</span></span> <span data-ttu-id="1dfd6-132">为 BizTalk 组指定签名证书 （私钥证书）。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-132">Signing certificates (private key certificates) are specified for the BizTalk group.</span></span> <span data-ttu-id="1dfd6-133">这些是可选的可以由 BizTalk Server 管理员随时更改。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-133">These are optional and can be changed at any time by a BizTalk Server administrator.</span></span>  
  
  <span data-ttu-id="1dfd6-134">有关 BizTalk Server 使用的 Windows 帐户的更完整信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1dfd6-134">For more complete information about Windows accounts that BizTalk Server uses, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1dfd6-135">本节内容</span><span class="sxs-lookup"><span data-stu-id="1dfd6-135">In This Section</span></span>  
  
-   [<span data-ttu-id="1dfd6-136">管理 Windows 组和用户帐户的最佳做法</span><span class="sxs-lookup"><span data-stu-id="1dfd6-136">Best Practices for Managing Windows Groups and User Accounts</span></span>](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)  
  
-   [<span data-ttu-id="1dfd6-137">管理证书的最佳做法</span><span class="sxs-lookup"><span data-stu-id="1dfd6-137">Best Practices for Managing Certificates</span></span>](../core/best-practices-for-managing-certificates1.md)  
  
-   [<span data-ttu-id="1dfd6-138">管理 Windows 组和用户帐户</span><span class="sxs-lookup"><span data-stu-id="1dfd6-138">Managing Windows Groups and User Accounts</span></span>](../core/managing-windows-groups-and-user-accounts.md)