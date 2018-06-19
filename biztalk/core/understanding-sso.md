---
title: 了解 SSO |Microsoft 文档
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
ms.openlocfilehash: 736fee720f2abf0dd051b1f754dd0fd6b8c42ab6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286981"
---
# <a name="understanding-sso"></a><span data-ttu-id="8983d-102">了解 SSO</span><span class="sxs-lookup"><span data-stu-id="8983d-102">Understanding SSO</span></span>
<span data-ttu-id="8983d-103">若要了解企业单一登录，最好今天查看上单一登录服务可用的三种类型： Windows 集成的 extranet 和 intranet。</span><span class="sxs-lookup"><span data-stu-id="8983d-103">To understand Enterprise Single Sign-On, it is useful to look at the three types of Single Sign-On services available today: Windows integrated, extranet, and intranet.</span></span> <span data-ttu-id="8983d-104">下面对这三种类型进行了说明，其中将企业单一登录归为第三个类别。</span><span class="sxs-lookup"><span data-stu-id="8983d-104">These are described below, with Enterprise Single Sign-On falling into the third category.</span></span>  
  
## <a name="windows-integrated-single-sign-on"></a><span data-ttu-id="8983d-105">Windows 集成单一登录</span><span class="sxs-lookup"><span data-stu-id="8983d-105">Windows Integrated Single Sign-On</span></span>  
 <span data-ttu-id="8983d-106">通过这些服务，您可以连接到网络中使用通用验证机制的多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="8983d-106">These services enable you to connect to multiple applications within your network that use a common authentication mechanism.</span></span> <span data-ttu-id="8983d-107">在您登录到网络后，这些服务将请求并验证您的凭据，并使用这些凭据来基于用户权限确定您可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="8983d-107">These services request and verify your credentials after you log into the network, and use your credentials to determine the actions that you can perform based on your user rights.</span></span> <span data-ttu-id="8983d-108">例如，如果应用程序使用 Kerberos 进行集成，则在系统对用户凭据进行验证后，您可以访问网络中与 Kerberos 集成的任何资源。</span><span class="sxs-lookup"><span data-stu-id="8983d-108">For example, if applications integrate using Kerberos, after the system authenticates your user credentials you can access any resource in the network that is integrated with Kerberos.</span></span>  
  
## <a name="extranet-single-sign-on-web-sso"></a><span data-ttu-id="8983d-109">Extranet 单一登录 (Web SSO)</span><span class="sxs-lookup"><span data-stu-id="8983d-109">Extranet Single Sign-On (Web SSO)</span></span>  
 <span data-ttu-id="8983d-110">通过这些服务，您可以使用单独的一组用户凭据来通过 Internet 访问资源。</span><span class="sxs-lookup"><span data-stu-id="8983d-110">These services enable you to access resources over the Internet by using a single set of user credentials.</span></span> <span data-ttu-id="8983d-111">用户提供一组凭据以登录到属于不同组织的不同网站。</span><span class="sxs-lookup"><span data-stu-id="8983d-111">The user provides a set of credentials to log on to different Web sites that belong to different organizations.</span></span> <span data-ttu-id="8983d-112">此类单一登录的一个示例是基于使用者的应用程序的 Windows Live ID。</span><span class="sxs-lookup"><span data-stu-id="8983d-112">An example of this type of Single Sign-On is Windows Live ID for consumer based applications.</span></span> <span data-ttu-id="8983d-113">对于联合方案，Microsoft Active Directory 联合服务将启用 Web SSO。</span><span class="sxs-lookup"><span data-stu-id="8983d-113">For federated scenarios, Microsoft Active Directory Federation Services enables Web SSO.</span></span>  
  
## <a name="server-based-intranet-single-sign-on"></a><span data-ttu-id="8983d-114">基于服务器的 Intranet 单一登录</span><span class="sxs-lookup"><span data-stu-id="8983d-114">Server-Based Intranet Single Sign-On</span></span>  
 <span data-ttu-id="8983d-115">通过这些服务，您可以在企业环境内集成多个不同类型的应用程序和系统。</span><span class="sxs-lookup"><span data-stu-id="8983d-115">These services enable you to integrate multiple heterogeneous applications and systems within the enterprise environment.</span></span> <span data-ttu-id="8983d-116">这些应用程序和系统可能不使用通用的验证机制。</span><span class="sxs-lookup"><span data-stu-id="8983d-116">These applications and systems may not use common authentication.</span></span> <span data-ttu-id="8983d-117">每个应用程序都具有其自己的用户目录存储区。</span><span class="sxs-lookup"><span data-stu-id="8983d-117">Each application has its own user directory store.</span></span> <span data-ttu-id="8983d-118">例如，在某个组织中，Windows 使用 Active Directory 目录服务来对用户进行验证，而大型机则使用 IBM 的资源访问控制工具 (RACF) 来验证相同的用户。</span><span class="sxs-lookup"><span data-stu-id="8983d-118">For example, in an organization, Windows uses Active Directory directory service to authenticate users, and mainframes use IBM's Resource Access Control Facility (RACF) to authenticate the same users.</span></span> <span data-ttu-id="8983d-119">在该企业中，中间件应用程序将前端应用程序和后端应用程序集成在一起。</span><span class="sxs-lookup"><span data-stu-id="8983d-119">Within the enterprise, middleware applications integrate the front-end and back-end applications.</span></span> <span data-ttu-id="8983d-120">通过企业单一登录，该企业内的用户可以在仅使用一组凭据的情况下同时连接到前端和后端。</span><span class="sxs-lookup"><span data-stu-id="8983d-120">Enterprise Single Sign-On enables users in the enterprise to connect to both the front end and back end while using only one set of credentials.</span></span> <span data-ttu-id="8983d-121">使用企业单一登录，Windows 启动的单一登录（其中的初始请求是从 Windows 域环境中生成的）和主机启动的单一登录（其中的初始请求是从非 Windows 域环境中生成的）都可以访问 Windows 域中的资源。</span><span class="sxs-lookup"><span data-stu-id="8983d-121">It enables both Windows Initiated Single Sign-On (in which the initial request is made from the Windows domain environment) and Host Initiated Single Sign-On (in which the initial request is made from a non-Windows domain environment) to access a resource in the Windows domain.</span></span>  
  
 <span data-ttu-id="8983d-122">此外，**密码同步**，来简化管理 SSO 数据库中，并保留密码跨用户目录同步。</span><span class="sxs-lookup"><span data-stu-id="8983d-122">In addition, **Password Synchronization** simplifies administration of the SSO database, and keeps passwords in sync across user directories.</span></span> <span data-ttu-id="8983d-123">此功能是通过使用密码同步适配器实现的，您可以使用密码同步工具配置和管理这些适配器。</span><span class="sxs-lookup"><span data-stu-id="8983d-123">This is done through the use of password synchronization adapters, which you can configure and manage using the Password Synchronization tools.</span></span>  
  
## <a name="the-enterprise-single-sign-on-system"></a><span data-ttu-id="8983d-124">企业单一登录系统</span><span class="sxs-lookup"><span data-stu-id="8983d-124">The Enterprise Single Sign-On System</span></span>  
 <span data-ttu-id="8983d-125">使用企业单一登录 (SSO) 提供的服务，可以跨本地和网络边界（包括域边界）存储和传输加密的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="8983d-125">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local and network boundaries, including domain boundaries.</span></span> <span data-ttu-id="8983d-126">SSO 将凭据存储在 SSO 数据库中。</span><span class="sxs-lookup"><span data-stu-id="8983d-126">SSO stores the credentials in the SSO database.</span></span> <span data-ttu-id="8983d-127">由于 SSO 提供了通用的单一登录解决方案，因此中间件应用程序和自定义适配器可以利用 SSO 来跨环境安全地存储和传输用户凭据。</span><span class="sxs-lookup"><span data-stu-id="8983d-127">Because SSO provides a generic single sign-on solution, middleware applications and custom adapters can leverage SSO to securely store and transmit user credentials across the environment.</span></span> <span data-ttu-id="8983d-128">最终用户不必为不同的应用程序记住不同的凭据。</span><span class="sxs-lookup"><span data-stu-id="8983d-128">End users do not have to remember different credentials for different applications.</span></span>  
  
 <span data-ttu-id="8983d-129">单一登录系统由以下部分组成：SSO 数据库、主密钥服务器以及一个或多个单一登录服务器。</span><span class="sxs-lookup"><span data-stu-id="8983d-129">The Single Sign-On system consists of an SSO database, a master secret server, and one or more Single Sign-On servers.</span></span>  
  
 <span data-ttu-id="8983d-130">SSO 系统包含管理员定义的 关联应用程序 。</span><span class="sxs-lookup"><span data-stu-id="8983d-130">The SSO system contains affiliate applications that an administrator defines.</span></span> <span data-ttu-id="8983d-131">关联应用程序 是用于表示使用企业单一登录连接到的诸如主机、后端系统或业务应用程序之类的系统或子系统的逻辑实体。</span><span class="sxs-lookup"><span data-stu-id="8983d-131">An affiliate application is a logical entity that represents a system or sub-system such as a host, back-end system, or line of business application to which you are connecting using Enterprise Single Sign-On.</span></span> <span data-ttu-id="8983d-132">每个关联应用程序都具有多个用户映射；例如，关联应用程序具有 Active Directory 中的用户凭据与其对应的 RACF 凭据之间的映射。</span><span class="sxs-lookup"><span data-stu-id="8983d-132">Each affiliate application has multiple user mappings; for example, it has the mappings between the credentials for a user in Active Directory and their corresponding RACF credentials.</span></span>  
  
 <span data-ttu-id="8983d-133">SSO 数据库是用于存储有关关联应用程序的信息以及用于所有关联应用程序的全部加密用户凭据的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="8983d-133">The SSO database is the SQL Server database that stores the information about the affiliate applications, as well as all the encrypted user credentials to all the affiliate applications.</span></span>  
  
 <span data-ttu-id="8983d-134">主密钥服务器 是存储主密钥的企业单一登录服务器。</span><span class="sxs-lookup"><span data-stu-id="8983d-134">The master secret server is the Enterprise Single Sign-On server that stores the master secret.</span></span> <span data-ttu-id="8983d-135">系统中的其他所有单一登录服务器都从主密钥服务器中获取主密钥。</span><span class="sxs-lookup"><span data-stu-id="8983d-135">All other Single Sign-On servers in the system get the master secret from the master secret server.</span></span>  
  
 <span data-ttu-id="8983d-136">SSO 系统还包含一个或多个 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="8983d-136">The SSO system also contains one or more SSO Servers.</span></span> <span data-ttu-id="8983d-137">这些服务器在 Windows 凭据和后端凭据之间进行映射，并在 SSO 数据库中查找凭据，管理员可使用这些服务器来维护 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="8983d-137">These servers do the mapping between the Windows and back-end credentials, look up the credentials in the SSO database, and administrators use them to maintain the SSO system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8983d-138">在 SSO 系统中，只能包含一个主密钥服务器和一个 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="8983d-138">You can have only one master secret server and only one SSO database in your SSO system.</span></span> <span data-ttu-id="8983d-139">SSO 数据库可以不位于主密钥服务器上。</span><span class="sxs-lookup"><span data-stu-id="8983d-139">The SSO database can be remote to the master secret server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8983d-140">本节内容</span><span class="sxs-lookup"><span data-stu-id="8983d-140">In This Section</span></span>  
  
-   [<span data-ttu-id="8983d-141">SSO 用户组</span><span class="sxs-lookup"><span data-stu-id="8983d-141">SSO User Groups</span></span>](../core/sso-user-groups.md)  
  
-   [<span data-ttu-id="8983d-142">SSO 组件</span><span class="sxs-lookup"><span data-stu-id="8983d-142">SSO Components</span></span>](../core/sso-components.md)  
  
-   [<span data-ttu-id="8983d-143">SSO 服务器</span><span class="sxs-lookup"><span data-stu-id="8983d-143">SSO Server</span></span>](../core/sso-server.md)  
  
-   [<span data-ttu-id="8983d-144">主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="8983d-144">Master Secret Server</span></span>](../core/master-secret-server.md)  
  
-   [<span data-ttu-id="8983d-145">SSO 关联应用程序</span><span class="sxs-lookup"><span data-stu-id="8983d-145">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)  
  
-   [<span data-ttu-id="8983d-146">SSO 映射</span><span class="sxs-lookup"><span data-stu-id="8983d-146">SSO Mappings</span></span>](../core/sso-mappings.md)  
  
-   [<span data-ttu-id="8983d-147">SSO 票证</span><span class="sxs-lookup"><span data-stu-id="8983d-147">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="8983d-148">配置 SSO</span><span class="sxs-lookup"><span data-stu-id="8983d-148">Configuring SSO</span></span>](../core/configuring-sso.md)