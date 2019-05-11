---
title: 了解 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, about SSO
- Windows Integrated Single Sign-On
- Extranet Single Sign-On (Web SSO)
- Server-Based Intranet Single Sign-On
ms.assetid: 03f78a7b-4880-408f-9733-d07e19775d21
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c8d312c008159d5eebede8e65909b5fef9ce442
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292732"
---
# <a name="understanding-sso"></a><span data-ttu-id="18a63-102">了解 SSO</span><span class="sxs-lookup"><span data-stu-id="18a63-102">Understanding SSO</span></span>
<span data-ttu-id="18a63-103">若要了解企业单一登录，最好立即查看三种类型的单一登录服务可用：Windows 集成、 extranet 和 intranet。</span><span class="sxs-lookup"><span data-stu-id="18a63-103">To understand Enterprise Single Sign-On, it is useful to look at the three types of Single Sign-On services available today: Windows integrated, extranet, and intranet.</span></span> <span data-ttu-id="18a63-104">这些如下所述，使用企业单一登录归为第三个类别。</span><span class="sxs-lookup"><span data-stu-id="18a63-104">These are described below, with Enterprise Single Sign-On falling into the third category.</span></span>  
  
## <a name="windows-integrated-single-sign-on"></a><span data-ttu-id="18a63-105">Windows 集成单一登录</span><span class="sxs-lookup"><span data-stu-id="18a63-105">Windows Integrated Single Sign-On</span></span>  
 <span data-ttu-id="18a63-106">这些服务，你可以连接到多个网络中使用的应用程序的常见身份验证机制。</span><span class="sxs-lookup"><span data-stu-id="18a63-106">These services enable you to connect to multiple applications within your network that use a common authentication mechanism.</span></span> <span data-ttu-id="18a63-107">这些服务请求，并登录到网络，并使用你的凭据来确定可以执行的操作根据你的用户权限后，验证你的凭据。</span><span class="sxs-lookup"><span data-stu-id="18a63-107">These services request and verify your credentials after you log into the network, and use your credentials to determine the actions that you can perform based on your user rights.</span></span> <span data-ttu-id="18a63-108">例如，如果应用程序集成后系统对你的用户凭据进行身份验证使用 Kerberos，您可以访问与 Kerberos 集成的网络中的任何资源。</span><span class="sxs-lookup"><span data-stu-id="18a63-108">For example, if applications integrate using Kerberos, after the system authenticates your user credentials you can access any resource in the network that is integrated with Kerberos.</span></span>  
  
## <a name="extranet-single-sign-on-web-sso"></a><span data-ttu-id="18a63-109">Extranet 单一登录 (Web SSO)</span><span class="sxs-lookup"><span data-stu-id="18a63-109">Extranet Single Sign-On (Web SSO)</span></span>  
 <span data-ttu-id="18a63-110">这些服务，可通过使用一组用户凭据通过 Internet 访问资源。</span><span class="sxs-lookup"><span data-stu-id="18a63-110">These services enable you to access resources over the Internet by using a single set of user credentials.</span></span> <span data-ttu-id="18a63-111">用户提供的凭据登录到属于不同组织的不同网站上的一组。</span><span class="sxs-lookup"><span data-stu-id="18a63-111">The user provides a set of credentials to log on to different Web sites that belong to different organizations.</span></span> <span data-ttu-id="18a63-112">此类型的单一登录的一个示例是基于应用程序的使用者的 Windows Live ID。</span><span class="sxs-lookup"><span data-stu-id="18a63-112">An example of this type of Single Sign-On is Windows Live ID for consumer based applications.</span></span> <span data-ttu-id="18a63-113">对于联合方案，Microsoft Active Directory 联合身份验证服务启用 Web SSO。</span><span class="sxs-lookup"><span data-stu-id="18a63-113">For federated scenarios, Microsoft Active Directory Federation Services enables Web SSO.</span></span>  
  
## <a name="server-based-intranet-single-sign-on"></a><span data-ttu-id="18a63-114">基于服务器的 Intranet 单一登录</span><span class="sxs-lookup"><span data-stu-id="18a63-114">Server-Based Intranet Single Sign-On</span></span>  
 <span data-ttu-id="18a63-115">这些服务，您将多个异类应用程序和企业环境中的系统进行集成。</span><span class="sxs-lookup"><span data-stu-id="18a63-115">These services enable you to integrate multiple heterogeneous applications and systems within the enterprise environment.</span></span> <span data-ttu-id="18a63-116">这些应用程序和系统不能使用常见的身份验证。</span><span class="sxs-lookup"><span data-stu-id="18a63-116">These applications and systems may not use common authentication.</span></span> <span data-ttu-id="18a63-117">每个应用程序都有其自己的用户目录存储。</span><span class="sxs-lookup"><span data-stu-id="18a63-117">Each application has its own user directory store.</span></span> <span data-ttu-id="18a63-118">例如，在组织中，Windows 使用 Active Directory 目录服务进行身份验证的用户，而大型机则使用 IBM 的资源的访问控制工具 (RACF) 相同的用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="18a63-118">For example, in an organization, Windows uses Active Directory directory service to authenticate users, and mainframes use IBM's Resource Access Control Facility (RACF) to authenticate the same users.</span></span> <span data-ttu-id="18a63-119">在企业内中间件应用程序集成的前端和后端应用程序。</span><span class="sxs-lookup"><span data-stu-id="18a63-119">Within the enterprise, middleware applications integrate the front-end and back-end applications.</span></span> <span data-ttu-id="18a63-120">企业单一登录可使企业中用户只使用一组凭据的同时连接到前端和后端。</span><span class="sxs-lookup"><span data-stu-id="18a63-120">Enterprise Single Sign-On enables users in the enterprise to connect to both the front end and back end while using only one set of credentials.</span></span> <span data-ttu-id="18a63-121">它允许 Windows 启动的单一登录 （在其中的初始请求执行从 Windows 域环境） 和主机启动的单一登录 （在其中的初始请求执行在非 Windows 域环境中） 来访问中的资源Windows 域。</span><span class="sxs-lookup"><span data-stu-id="18a63-121">It enables both Windows Initiated Single Sign-On (in which the initial request is made from the Windows domain environment) and Host Initiated Single Sign-On (in which the initial request is made from a non-Windows domain environment) to access a resource in the Windows domain.</span></span>  
  
 <span data-ttu-id="18a63-122">此外，**密码同步**简化了管理 SSO 数据库中，并保留密码各个用户目录间保持同步。</span><span class="sxs-lookup"><span data-stu-id="18a63-122">In addition, **Password Synchronization** simplifies administration of the SSO database, and keeps passwords in sync across user directories.</span></span> <span data-ttu-id="18a63-123">这是通过使用密码同步适配器，你可以配置和使用密码同步工具进行管理。</span><span class="sxs-lookup"><span data-stu-id="18a63-123">This is done through the use of password synchronization adapters, which you can configure and manage using the Password Synchronization tools.</span></span>  
  
## <a name="the-enterprise-single-sign-on-system"></a><span data-ttu-id="18a63-124">企业单一登录系统</span><span class="sxs-lookup"><span data-stu-id="18a63-124">The Enterprise Single Sign-On System</span></span>  
 <span data-ttu-id="18a63-125">企业单一登录 (SSO) 提供的服务来存储和传输加密用户凭据跨本地和网络边界，其中包括域边界。</span><span class="sxs-lookup"><span data-stu-id="18a63-125">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local and network boundaries, including domain boundaries.</span></span> <span data-ttu-id="18a63-126">SSO 将凭据存储在 SSO 数据库中。</span><span class="sxs-lookup"><span data-stu-id="18a63-126">SSO stores the credentials in the SSO database.</span></span> <span data-ttu-id="18a63-127">由于 SSO 提供了一个泛型单一登录解决方案，中间件应用程序和自定义适配器可以利用 SSO 来安全地存储和传输整个环境的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="18a63-127">Because SSO provides a generic single sign-on solution, middleware applications and custom adapters can leverage SSO to securely store and transmit user credentials across the environment.</span></span> <span data-ttu-id="18a63-128">最终用户无需记住的不同应用程序不同的凭据。</span><span class="sxs-lookup"><span data-stu-id="18a63-128">End users do not have to remember different credentials for different applications.</span></span>  
  
 <span data-ttu-id="18a63-129">单一登录系统包含 SSO 数据库、 主密钥服务器和一个或多个单一登录服务器。</span><span class="sxs-lookup"><span data-stu-id="18a63-129">The Single Sign-On system consists of an SSO database, a master secret server, and one or more Single Sign-On servers.</span></span>  
  
 <span data-ttu-id="18a63-130">SSO 系统包含管理员定义的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="18a63-130">The SSO system contains affiliate applications that an administrator defines.</span></span> <span data-ttu-id="18a63-131">关联应用程序是表示系统或如主机、 后端系统或业务线应用程序的子系统的逻辑实体连接到使用企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="18a63-131">An affiliate application is a logical entity that represents a system or sub-system such as a host, back-end system, or line of business application to which you are connecting using Enterprise Single Sign-On.</span></span> <span data-ttu-id="18a63-132">每个关联应用程序具有多个用户映射;例如，它具有在 Active Directory 中用户的凭据和其对应的 RACF 凭据之间的映射。</span><span class="sxs-lookup"><span data-stu-id="18a63-132">Each affiliate application has multiple user mappings; for example, it has the mappings between the credentials for a user in Active Directory and their corresponding RACF credentials.</span></span>  
  
 <span data-ttu-id="18a63-133">SSO 数据库是存储有关关联应用程序，以及所有关联应用程序的所有加密的用户凭据的信息的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="18a63-133">The SSO database is the SQL Server database that stores the information about the affiliate applications, as well as all the encrypted user credentials to all the affiliate applications.</span></span>  
  
 <span data-ttu-id="18a63-134">主密钥服务器是存储主密钥的企业单一登录服务器。</span><span class="sxs-lookup"><span data-stu-id="18a63-134">The master secret server is the Enterprise Single Sign-On server that stores the master secret.</span></span> <span data-ttu-id="18a63-135">中的所有其他单一登录服务器系统从主密钥服务器获取主密钥。</span><span class="sxs-lookup"><span data-stu-id="18a63-135">All other Single Sign-On servers in the system get the master secret from the master secret server.</span></span>  
  
 <span data-ttu-id="18a63-136">SSO 系统还包含一个或多个 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="18a63-136">The SSO system also contains one or more SSO Servers.</span></span> <span data-ttu-id="18a63-137">这些服务器之间进行映射的 Windows 和后端凭据，查找在 SSO 数据库中，凭据和管理员可使用这些来维护 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="18a63-137">These servers do the mapping between the Windows and back-end credentials, look up the credentials in the SSO database, and administrators use them to maintain the SSO system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18a63-138">SSO 系统中，可以有一个主密钥服务器和一个 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="18a63-138">You can have only one master secret server and only one SSO database in your SSO system.</span></span> <span data-ttu-id="18a63-139">SSO 数据库可以是远程连接到主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="18a63-139">The SSO database can be remote to the master secret server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18a63-140">本节内容</span><span class="sxs-lookup"><span data-stu-id="18a63-140">In This Section</span></span>  
  
-   [<span data-ttu-id="18a63-141">SSO 用户组</span><span class="sxs-lookup"><span data-stu-id="18a63-141">SSO User Groups</span></span>](../core/sso-user-groups.md)  
  
-   [<span data-ttu-id="18a63-142">SSO 组件</span><span class="sxs-lookup"><span data-stu-id="18a63-142">SSO Components</span></span>](../core/sso-components.md)  
  
-   [<span data-ttu-id="18a63-143">SSO 服务器</span><span class="sxs-lookup"><span data-stu-id="18a63-143">SSO Server</span></span>](../core/sso-server.md)  
  
-   [<span data-ttu-id="18a63-144">主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="18a63-144">Master Secret Server</span></span>](../core/master-secret-server.md)  
  
-   [<span data-ttu-id="18a63-145">SSO 关联应用程序</span><span class="sxs-lookup"><span data-stu-id="18a63-145">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)  
  
-   [<span data-ttu-id="18a63-146">SSO 映射</span><span class="sxs-lookup"><span data-stu-id="18a63-146">SSO Mappings</span></span>](../core/sso-mappings.md)  
  
-   [<span data-ttu-id="18a63-147">SSO 票证</span><span class="sxs-lookup"><span data-stu-id="18a63-147">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="18a63-148">配置 SSO</span><span class="sxs-lookup"><span data-stu-id="18a63-148">Configuring SSO</span></span>](../core/configuring-sso.md)