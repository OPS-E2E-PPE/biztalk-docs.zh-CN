---
title: 在多服务器 BizTalk 安装上实现 Active Directory 权限的指南 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 315e25c4-b21d-4b5f-a1d2-1e2777b57f9e
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d8fbd37438ef41c29ec2503a384fb3afff1545e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006782"
---
# <a name="guidelines-for-implementing-active-directory-permissions-on-multi-server-biztalk-installations"></a><span data-ttu-id="fce8a-102">准则用于实现在多服务器 BizTalk 安装在 Active Directory 权限</span><span class="sxs-lookup"><span data-stu-id="fce8a-102">Guidelines for Implementing Active Directory Permissions on Multi Server BizTalk Installations</span></span>
<span data-ttu-id="fce8a-103">本主题介绍用于创建 Active Directory 组织单位的准则，Active Directory 组织单位由在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装中使用的用户帐户和组构成。</span><span class="sxs-lookup"><span data-stu-id="fce8a-103">This topic describes guidelines for creating Active Directory Organizational Units, which consist of the user accounts and groups that you use in a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span>  
  
 <span data-ttu-id="fce8a-104">此处创建的这些帐户不需要在域中具有超出普通用户的权限。</span><span class="sxs-lookup"><span data-stu-id="fce8a-104">The accounts created herein do not need permissions in the domain beyond those of ordinary users.</span></span> <span data-ttu-id="fce8a-105">域帐户可能需要在包括以下项的信任边界内的提升的权限：</span><span class="sxs-lookup"><span data-stu-id="fce8a-105">The domain accounts may need elevated privileges within the trust boundary that includes:</span></span>  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- <span data-ttu-id="fce8a-106">Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]（在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务器上）</span><span class="sxs-lookup"><span data-stu-id="fce8a-106">Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] (on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] server)</span></span>  
  
- <span data-ttu-id="fce8a-107">Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fce8a-107">Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]</span></span>  
  
- <span data-ttu-id="fce8a-108">外部数据库 1</span><span class="sxs-lookup"><span data-stu-id="fce8a-108">External Database One</span></span>  
  
- <span data-ttu-id="fce8a-109">外部数据库 2</span><span class="sxs-lookup"><span data-stu-id="fce8a-109">External Database Two</span></span>  
  
- <span data-ttu-id="fce8a-110">外部数据库*N*</span><span class="sxs-lookup"><span data-stu-id="fce8a-110">External Database *N*</span></span>  
  
  <span data-ttu-id="fce8a-111">例如，可能需要授予某个域帐户对作为外部数据库宿主的系统执行某些操作的权限。</span><span class="sxs-lookup"><span data-stu-id="fce8a-111">For example, a domain account may need to be granted rights to perform certain actions on the systems hosting external databases.</span></span> <span data-ttu-id="fce8a-112">在其他情况下，某个帐户可能需要将某一文件写入文件存放文件夹，因此要求对该文件夹具有写访问权限。</span><span class="sxs-lookup"><span data-stu-id="fce8a-112">In another case, an account may need to write a file to a file drop folder, requiring write access to the folder.</span></span>  
  
  <span data-ttu-id="fce8a-113">使用**Active Directory 用户和计算机**控制台来创建和管理域用户和组帐户。</span><span class="sxs-lookup"><span data-stu-id="fce8a-113">Use the **Active Directory Users and Computers** console to create and manage domain user and group accounts.</span></span> <span data-ttu-id="fce8a-114">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Active Directory 用户和计算机**到启动**Active Directory 用户和计算机**控制台。</span><span class="sxs-lookup"><span data-stu-id="fce8a-114">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Active Directory Users and Computers** to start the **Active Directory Users and Computers** console.</span></span>  
  
## <a name="biztalk-server-installation-and-configuration-account"></a><span data-ttu-id="fce8a-115">BizTalk Server 安装和配置帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-115">BizTalk Server Installation and Configuration Account</span></span>  
 <span data-ttu-id="fce8a-116">在开发环境中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装程序和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置向导要求使用对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 系统具有管理权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="fce8a-116">In the development environment, the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation program and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Wizard require the use of an account with administrative rights on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] systems.</span></span> <span data-ttu-id="fce8a-117">一旦设置和配置完成，可以立即吊销权限或禁用帐户。</span><span class="sxs-lookup"><span data-stu-id="fce8a-117">Rights can be revoked or the account disabled as soon as setup and configuration are complete.</span></span> <span data-ttu-id="fce8a-118">帐户必须还属于若干 BizTalk 组，下面的几节中将对此予以介绍。</span><span class="sxs-lookup"><span data-stu-id="fce8a-118">The account must also belong to several BizTalk groups, covered in the following sections.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fce8a-119">如果用于安装的帐户与服务器不属于同一 Active Directory 目录林，您将无法配置 SSO 组件。</span><span class="sxs-lookup"><span data-stu-id="fce8a-119">You will not be able to configure SSO components if the account used for installation belongs to a different Active Directory forest than the server.</span></span> <span data-ttu-id="fce8a-120">如果还没有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序帐户，请使用本地管理员帐户进行 SSO 配置。</span><span class="sxs-lookup"><span data-stu-id="fce8a-120">If you do not have a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installer account, use a local administrator account for SSO configuration.</span></span> <span data-ttu-id="fce8a-121">此方法可能会在安装期间造成其他问题，例如，需要使用不同凭据登录到资源。</span><span class="sxs-lookup"><span data-stu-id="fce8a-121">This methodology may create other issues during installation, such as the need to log on to resources using different credentials.</span></span>  
  
## <a name="biztalk-server-development-accounts"></a><span data-ttu-id="fce8a-122">BizTalk Server 开发帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-122">BizTalk Server Development Accounts</span></span>  
 <span data-ttu-id="fce8a-123">执行操作的个人[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发需要能够访问适配器、 接收和发送处理程序，并接收位置。</span><span class="sxs-lookup"><span data-stu-id="fce8a-123">Individuals doing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development require access to adapters, receive and send handlers, and receive locations.</span></span> <span data-ttu-id="fce8a-124">这一访问要求域开发人员组的成员**BizTalk Server Administrators**并**SSO Affiliate Administrators**组。</span><span class="sxs-lookup"><span data-stu-id="fce8a-124">This access requires the domain developer group to be members of the **BizTalk Server Administrators** and **SSO Affiliate Administrators** groups.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fce8a-125">Active Directory 对可以包含外来域用户的组的类型具有限制，并且对可在其他组中包含的组类型具有限制。</span><span class="sxs-lookup"><span data-stu-id="fce8a-125">Active Directory has restrictions regarding the types of groups that can contain foreign domain users, and the types of groups that can be contained in other groups.</span></span> <span data-ttu-id="fce8a-126">下面创建的组和帐户在单个域上的多服务器环境中进行了测试。</span><span class="sxs-lookup"><span data-stu-id="fce8a-126">The groups and accounts created below are tested in a multiserver environment on a single domain.</span></span>  
  
## <a name="biztalk-server-deployment-accounts"></a><span data-ttu-id="fce8a-127">BizTalk Server 部署帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-127">BizTalk Server Deployment Accounts</span></span>  
 <span data-ttu-id="fce8a-128">部署的个人[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序将需要是本地系统上的管理员，并且可能需要在环境中的其他权限。</span><span class="sxs-lookup"><span data-stu-id="fce8a-128">Individuals deploying [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications will need to be administrators on the local systems and may require other permissions in the environment.</span></span> <span data-ttu-id="fce8a-129">本主题中为此目的而引用了 BizTalk Server 部署帐户。</span><span class="sxs-lookup"><span data-stu-id="fce8a-129">A BizTalk Server deployment account is referenced in this topic for this purpose.</span></span>  
  
 <span data-ttu-id="fce8a-130">这一访问要求域部署组的成员**BizTalk Server Administrators**并**SSO Affiliate Administrators**组。</span><span class="sxs-lookup"><span data-stu-id="fce8a-130">This access requires the domain deployment group to be members of the **BizTalk Server Administrators** and **SSO Affiliate Administrators** groups.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fce8a-131">如果用于安装的帐户与服务器不属于同一 Active Directory 目录林，您将无法配置 SSO 组件。</span><span class="sxs-lookup"><span data-stu-id="fce8a-131">You will not be able to configure SSO components if the account used for installation belongs to a different Active Directory forest than the server.</span></span> <span data-ttu-id="fce8a-132">如果您不具有 BizTalk Server 部署帐户，则使用本地管理员帐户进行 SSO 配置。</span><span class="sxs-lookup"><span data-stu-id="fce8a-132">If you do not have a BizTalk Server deployment account, use a local administrator account for SSO configuration.</span></span> <span data-ttu-id="fce8a-133">此方法可能会在安装期间造成其他问题，例如，需要使用不同凭据登录到资源。</span><span class="sxs-lookup"><span data-stu-id="fce8a-133">This methodology may create other issues during installation, such as the need to log on to resources using different credentials.</span></span>  
  
## <a name="biztalk-server-support-accounts"></a><span data-ttu-id="fce8a-134">BizTalk Server 支持帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-134">BizTalk Server Support Accounts</span></span>  
 <span data-ttu-id="fce8a-135">支持 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序的个体将需要是本地系统上的管理员。</span><span class="sxs-lookup"><span data-stu-id="fce8a-135">Individuals supporting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications will need to be administrators on the local systems.</span></span> <span data-ttu-id="fce8a-136">本主题中为此目的而引用了 BizTalk 支持帐户。</span><span class="sxs-lookup"><span data-stu-id="fce8a-136">A BizTalk support account is referenced in this topic for this purpose.</span></span>  
  
 <span data-ttu-id="fce8a-137">这一访问要求域支持组的成员**BizTalk Server Administrators**组。</span><span class="sxs-lookup"><span data-stu-id="fce8a-137">This access requires the domain support group to be members of the **BizTalk Server Administrators** group.</span></span>  
  
## <a name="sql-server-service-accounts"></a><span data-ttu-id="fce8a-138">SQL Server 服务帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-138">SQL Server Service Accounts</span></span>  
 <span data-ttu-id="fce8a-139">运行 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 实例的服务必须与安装、开发和部署 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组件的帐户属于同一 Active Directory 域。</span><span class="sxs-lookup"><span data-stu-id="fce8a-139">The service running the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance must belong to the same Active Directory domain as the accounts installing, developing, and deploying [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components.</span></span>  
  
- <span data-ttu-id="fce8a-140">使用**SQLAdmin**执行管理功能 （交互式登录）。</span><span class="sxs-lookup"><span data-stu-id="fce8a-140">Use **SQLAdmin** for administrative functions (interactive logon).</span></span>  
  
- <span data-ttu-id="fce8a-141">使用**SQLService**管理服务 （无交互式登录）。</span><span class="sxs-lookup"><span data-stu-id="fce8a-141">Use **SQLService** to manage the service (no interactive logon).</span></span>  
  
- <span data-ttu-id="fce8a-142">使用**SQLAccess**访问外部数据库。</span><span class="sxs-lookup"><span data-stu-id="fce8a-142">Use **SQLAccess** to access external databases.</span></span>  
  
- <span data-ttu-id="fce8a-143">SQLAdmin 必须是 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 系统上本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="fce8a-143">SQLAdmin must be a member of the local Administrators group on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] system.</span></span>  
  
- <span data-ttu-id="fce8a-144">SQLService 必须是本地 Administrators 组的成员上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]系统，需要授予**作为服务登录**用户权限。</span><span class="sxs-lookup"><span data-stu-id="fce8a-144">SQLService must be a member of the local Administrators group on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] system and needs to be granted the **Log on as a service** user right.</span></span>  
  
- <span data-ttu-id="fce8a-145">SQLAccess 需要对远程数据库服务器具有适当的权限。</span><span class="sxs-lookup"><span data-stu-id="fce8a-145">SQLAccess needs appropriate rights on the remote database servers.</span></span>  
  
  <span data-ttu-id="fce8a-146">**SQL 帐户：**</span><span class="sxs-lookup"><span data-stu-id="fce8a-146">**SQL Accounts:**</span></span>  
  
|<span data-ttu-id="fce8a-147">**用户名**</span><span class="sxs-lookup"><span data-stu-id="fce8a-147">**User name**</span></span>|<span data-ttu-id="fce8a-148">**First Name**</span><span class="sxs-lookup"><span data-stu-id="fce8a-148">**First Name**</span></span>|<span data-ttu-id="fce8a-149">**Last Name**</span><span class="sxs-lookup"><span data-stu-id="fce8a-149">**Last Name**</span></span>|<span data-ttu-id="fce8a-150">**全名**</span><span class="sxs-lookup"><span data-stu-id="fce8a-150">**Full Name**</span></span>|  
|-------------------|--------------------|-------------------|-------------------|  
|<span data-ttu-id="fce8a-151">SQLService</span><span class="sxs-lookup"><span data-stu-id="fce8a-151">SQLService</span></span>|<span data-ttu-id="fce8a-152">SQL</span><span class="sxs-lookup"><span data-stu-id="fce8a-152">SQL</span></span>|<span data-ttu-id="fce8a-153">SQLService</span><span class="sxs-lookup"><span data-stu-id="fce8a-153">SQLService</span></span>|<span data-ttu-id="fce8a-154">SQL 服务帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-154">SQL Service Account</span></span>|  
|<span data-ttu-id="fce8a-155">SQLAdmin</span><span class="sxs-lookup"><span data-stu-id="fce8a-155">SQLAdmin</span></span>|<span data-ttu-id="fce8a-156">管理员</span><span class="sxs-lookup"><span data-stu-id="fce8a-156">Admin</span></span>|<span data-ttu-id="fce8a-157">SQLService</span><span class="sxs-lookup"><span data-stu-id="fce8a-157">SQLService</span></span>|<span data-ttu-id="fce8a-158">SQL 管理员帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-158">SQL Admin Account</span></span>|  
|<span data-ttu-id="fce8a-159">SQLAccess</span><span class="sxs-lookup"><span data-stu-id="fce8a-159">SQLAccess</span></span>|<span data-ttu-id="fce8a-160">访问</span><span class="sxs-lookup"><span data-stu-id="fce8a-160">Access</span></span>|<span data-ttu-id="fce8a-161">SQLService</span><span class="sxs-lookup"><span data-stu-id="fce8a-161">SQLService</span></span>|<span data-ttu-id="fce8a-162">SQL 访问帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-162">SQL Access Account</span></span>|  
  
 <span data-ttu-id="fce8a-163">根据公司标准设置帐户密码。</span><span class="sxs-lookup"><span data-stu-id="fce8a-163">Set account passwords according to company standards.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fce8a-164">在运行 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的计算机上，修改 SQL Server 和 SQLServerAgent 服务的启动参数，以便使用 SQLService 帐户和凭据。</span><span class="sxs-lookup"><span data-stu-id="fce8a-164">On the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], modify the startup parameters for the SQL Server and SQLServerAgent services to use the SQLService account and credentials.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="fce8a-165">用户名字段是示例；您可能需要更改这些名称以避免与其他 Active Directory 帐户冲突。</span><span class="sxs-lookup"><span data-stu-id="fce8a-165">The Username fields are samples; you may need to change the names to avoid conflicting with other Active Directory accounts.</span></span>  
  
## <a name="windows-sharepoint-services-account"></a><span data-ttu-id="fce8a-166">Windows SharePoint Services 帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-166">Windows SharePoint Services Account</span></span>  
 <span data-ttu-id="fce8a-167">Windows SharePoint Services 帐户必须在安装 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 前创建。</span><span class="sxs-lookup"><span data-stu-id="fce8a-167">The Windows SharePoint Services accounts must be created prior to installing [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fce8a-168">有关建议和说明[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]帐户：</span><span class="sxs-lookup"><span data-stu-id="fce8a-168">Recommendations and notes on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] account:</span></span>  
  
- <span data-ttu-id="fce8a-169">使用 SharePoint 管理员帐户 (SPAdmin) 执行管理功能、SharePoint 定时服务和所有 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 访问。</span><span class="sxs-lookup"><span data-stu-id="fce8a-169">Use the SharePoint Admin Account (SPAdmin) for administrative functions, SharePoint Timer Service and all [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] access.</span></span>  
  
- <span data-ttu-id="fce8a-170">SPAdmin 是站点所有者并且将需要电子邮件别名。</span><span class="sxs-lookup"><span data-stu-id="fce8a-170">SPAdmin is the site owner and will need an e-mail alias.</span></span>  
  
- <span data-ttu-id="fce8a-171">SPAdmin 必须是本地 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上的本地管理员组的成员（Windows SharePoint Services 安装程序执行此要求）。</span><span class="sxs-lookup"><span data-stu-id="fce8a-171">SPAdmin must be a member of the local administrators group on the local [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer (Windows SharePoint Services setup does this).</span></span>  
  
- <span data-ttu-id="fce8a-172">SPAdmin 必须在 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 计算机上具有安全管理员和数据库创建者角色（Windows SharePoint Services 安装程序执行此要求）。</span><span class="sxs-lookup"><span data-stu-id="fce8a-172">SPAdmin must have the security administrator and database creator roles on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer (Windows SharePoint Services setup does this).</span></span>  
  
  <span data-ttu-id="fce8a-173">**Sharepoint 帐户：**</span><span class="sxs-lookup"><span data-stu-id="fce8a-173">**Sharepoint Accounts:**</span></span>  
  
|<span data-ttu-id="fce8a-174">**用户名**</span><span class="sxs-lookup"><span data-stu-id="fce8a-174">**User name**</span></span>|<span data-ttu-id="fce8a-175">**First Name**</span><span class="sxs-lookup"><span data-stu-id="fce8a-175">**First Name**</span></span>|<span data-ttu-id="fce8a-176">**Last Name**</span><span class="sxs-lookup"><span data-stu-id="fce8a-176">**Last Name**</span></span>|<span data-ttu-id="fce8a-177">**全名**</span><span class="sxs-lookup"><span data-stu-id="fce8a-177">**Full Name**</span></span>|  
|-------------------|--------------------|-------------------|-------------------|  
|<span data-ttu-id="fce8a-178">SPAdmin</span><span class="sxs-lookup"><span data-stu-id="fce8a-178">SPAdmin</span></span>|<span data-ttu-id="fce8a-179">管理员</span><span class="sxs-lookup"><span data-stu-id="fce8a-179">Admin</span></span>|<span data-ttu-id="fce8a-180">SPService</span><span class="sxs-lookup"><span data-stu-id="fce8a-180">SPService</span></span>|<span data-ttu-id="fce8a-181">SharePoint 管理员帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-181">SharePoint Admin Account</span></span>|  
  
 <span data-ttu-id="fce8a-182">根据公司标准设置帐户密码，并且能够在配置过程中检索这些密码。</span><span class="sxs-lookup"><span data-stu-id="fce8a-182">Set account passwords according to company standards and be able to retrieve these passwords during the configuration steps.</span></span> <span data-ttu-id="fce8a-183">请参阅**密码**围绕问题本主题的部分生成的密码。</span><span class="sxs-lookup"><span data-stu-id="fce8a-183">Refer to the **Passwords** section of this topic for issues surrounding generated passwords.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fce8a-184">此用户名字段是个示例；您可能需要更改此名称以保护其他 AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="fce8a-184">This Username field is a sample; you may need to change this name to protect other AD accounts.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="fce8a-185">在运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机上安装 Windows SharePoint Services 后，请确认 SharePoint 定时服务的启动参数正在使用 SPAdmin 帐户和凭据。</span><span class="sxs-lookup"><span data-stu-id="fce8a-185">After installing Windows SharePoint Services on the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], confirm that the startup parameters for the SharePoint Timer Service is using the SPAdmin account and credentials.</span></span>  
  
## <a name="biztalk-groups-and-users"></a><span data-ttu-id="fce8a-186">BizTalk 组和用户</span><span class="sxs-lookup"><span data-stu-id="fce8a-186">BizTalk Groups and Users</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="fce8a-187"> 组和用户必须在运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置向导之前创建。</span><span class="sxs-lookup"><span data-stu-id="fce8a-187"> Groups and Users must be created prior to running the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Wizard.</span></span> <span data-ttu-id="fce8a-188">在单系统安装中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用配置期间创建的本地组和帐户。</span><span class="sxs-lookup"><span data-stu-id="fce8a-188">In a single-system installation, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses local groups and accounts which are created during configuration.</span></span> <span data-ttu-id="fce8a-189">但是，如果部署单独的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机或将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 安装在两个不同的计算机上，您必须使用域用户和组帐户。</span><span class="sxs-lookup"><span data-stu-id="fce8a-189">However, if separate [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hosts are deployed or if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are installed on two different computers you must use domain user and group accounts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fce8a-190">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置向导无法创建域帐户。</span><span class="sxs-lookup"><span data-stu-id="fce8a-190">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Wizard cannot create domain accounts.</span></span>  
  
 <span data-ttu-id="fce8a-191">有关 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务和用户帐户的建议和说明：</span><span class="sxs-lookup"><span data-stu-id="fce8a-191">Recommendations and notes on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] service and user accounts:</span></span>  
  
- <span data-ttu-id="fce8a-192">为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建组织单位 (OU)。</span><span class="sxs-lookup"><span data-stu-id="fce8a-192">Create an Organizational Unit (OU) for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="fce8a-193">所有帐户和组都将属于此 OU。</span><span class="sxs-lookup"><span data-stu-id="fce8a-193">All accounts and groups will belong to this OU.</span></span>  
  
- <span data-ttu-id="fce8a-194">全名应该有描述性，下面列表中的名称应该使安装人员可以在配置期间选择正确的组/帐户/用户。</span><span class="sxs-lookup"><span data-stu-id="fce8a-194">Be descriptive with full names; the names in the following lists should enable the installer to select the proper groups/accounts/users during configuration.</span></span>  
  
- <span data-ttu-id="fce8a-195">名字和姓氏是可选的；包括它们只是为了一致性。</span><span class="sxs-lookup"><span data-stu-id="fce8a-195">First name and last name are optional; included for consistency only.</span></span>  
  
- <span data-ttu-id="fce8a-196">不同之处**符 BTService**并**BTUser**指的是服务帐户 （自动） 和一般/共享人类用户。</span><span class="sxs-lookup"><span data-stu-id="fce8a-196">The differentiator **BTService** and **BTUser** refers to service accounts (automatons) and generic/shared human users.</span></span>  
  
- <span data-ttu-id="fce8a-197">创建域帐户并通过 ADSI 脚本填充它们，以便用于上游环境的用户和组帐户的创建。</span><span class="sxs-lookup"><span data-stu-id="fce8a-197">Create domain accounts and populate them via an ADSI script for user and group account creation for up line environments.</span></span>  
  
  <span data-ttu-id="fce8a-198">**BizTalk 服务帐户**</span><span class="sxs-lookup"><span data-stu-id="fce8a-198">**BizTalk Service Accounts**</span></span>  
  
|<span data-ttu-id="fce8a-199">**用户名**</span><span class="sxs-lookup"><span data-stu-id="fce8a-199">**User name**</span></span>|<span data-ttu-id="fce8a-200">**First Name**</span><span class="sxs-lookup"><span data-stu-id="fce8a-200">**First Name**</span></span>|<span data-ttu-id="fce8a-201">**Last Name**</span><span class="sxs-lookup"><span data-stu-id="fce8a-201">**Last Name**</span></span>|<span data-ttu-id="fce8a-202">**全名**</span><span class="sxs-lookup"><span data-stu-id="fce8a-202">**Full Name**</span></span>|  
|-------------------|--------------------|-------------------|-------------------|  
|<span data-ttu-id="fce8a-203">BTService</span><span class="sxs-lookup"><span data-stu-id="fce8a-203">BTService</span></span>|<span data-ttu-id="fce8a-204">BTS</span><span class="sxs-lookup"><span data-stu-id="fce8a-204">BTS</span></span>|<span data-ttu-id="fce8a-205">BTService</span><span class="sxs-lookup"><span data-stu-id="fce8a-205">BTService</span></span>|<span data-ttu-id="fce8a-206">BizTalk 服务帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-206">BizTalk Service Account</span></span>|  
|<span data-ttu-id="fce8a-207">BTServiceHost</span><span class="sxs-lookup"><span data-stu-id="fce8a-207">BTServiceHost</span></span>|<span data-ttu-id="fce8a-208">主机</span><span class="sxs-lookup"><span data-stu-id="fce8a-208">Host</span></span>|<span data-ttu-id="fce8a-209">BTService</span><span class="sxs-lookup"><span data-stu-id="fce8a-209">BTService</span></span>|<span data-ttu-id="fce8a-210">BizTalk 主机实例帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-210">BizTalk Host Instance Account</span></span>|  
|<span data-ttu-id="fce8a-211">BTServiceHostIso</span><span class="sxs-lookup"><span data-stu-id="fce8a-211">BTServiceHostIso</span></span>|<span data-ttu-id="fce8a-212">HostIso</span><span class="sxs-lookup"><span data-stu-id="fce8a-212">HostIso</span></span>|<span data-ttu-id="fce8a-213">BTService</span><span class="sxs-lookup"><span data-stu-id="fce8a-213">BTService</span></span>|<span data-ttu-id="fce8a-214">BizTalk 独立主机实例帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-214">BizTalk Isolated Host Instance Account</span></span>|  
|<span data-ttu-id="fce8a-215">SSOService</span><span class="sxs-lookup"><span data-stu-id="fce8a-215">SSOService</span></span>|<span data-ttu-id="fce8a-216">SSO</span><span class="sxs-lookup"><span data-stu-id="fce8a-216">SSO</span></span>|<span data-ttu-id="fce8a-217">BTService</span><span class="sxs-lookup"><span data-stu-id="fce8a-217">BTService</span></span>|<span data-ttu-id="fce8a-218">企业单一登录服务</span><span class="sxs-lookup"><span data-stu-id="fce8a-218">Enterprise Single Sign-On Service</span></span>|  
|<span data-ttu-id="fce8a-219">BTServiceREU</span><span class="sxs-lookup"><span data-stu-id="fce8a-219">BTServiceREU</span></span>|<span data-ttu-id="fce8a-220">REU</span><span class="sxs-lookup"><span data-stu-id="fce8a-220">REU</span></span>|<span data-ttu-id="fce8a-221">BTService</span><span class="sxs-lookup"><span data-stu-id="fce8a-221">BTService</span></span>|<span data-ttu-id="fce8a-222">规则引擎更新服务</span><span class="sxs-lookup"><span data-stu-id="fce8a-222">Rule Engine Update Service</span></span>|  
  
 <span data-ttu-id="fce8a-223">根据公司和环境标准设置用户名（例如 devBTService、alphaBTService）。</span><span class="sxs-lookup"><span data-stu-id="fce8a-223">Set user names according to company and environmental standards (for example, devBTService, alphaBTService).</span></span> <span data-ttu-id="fce8a-224">根据公司标准设置帐户密码，并且能够为配置步骤检索这些密码。</span><span class="sxs-lookup"><span data-stu-id="fce8a-224">Set account passwords according to company standards and be able to retrieve them for the configuration steps.</span></span> <span data-ttu-id="fce8a-225">请参阅**开发的密码注意事项**围绕问题本主题的部分生成的密码。</span><span class="sxs-lookup"><span data-stu-id="fce8a-225">Refer to the **Password Considerations for Development** section of this topic for issues surrounding generated passwords.</span></span>  
  
 <span data-ttu-id="fce8a-226">安装人员将注意到服务帐户具有很高的粒度，具有与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 所创建的服务的接近一对一的映射。</span><span class="sxs-lookup"><span data-stu-id="fce8a-226">The installer will notice the service accounts are quite granular, with a near one-to-one mapping to the services created by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="fce8a-227">这一粒度允许公司 IT 安全人员根据需要跟踪或限制访问。</span><span class="sxs-lookup"><span data-stu-id="fce8a-227">The granularity allows corporate IT security to track or restrict access as needed.</span></span> <span data-ttu-id="fce8a-228">建议采用该粒度，但由系统设计人员和企业安全人员确定在企业环境中是否需要这一粒度。</span><span class="sxs-lookup"><span data-stu-id="fce8a-228">The granularity is recommended, but it is up to the system designer and enterprise security personnel to determine if it is necessary in the enterprise environment.</span></span>  
  
 <span data-ttu-id="fce8a-229">前一组中的服务帐户旨在仅用于自动访问，而不是针对用户交互式登录。</span><span class="sxs-lookup"><span data-stu-id="fce8a-229">The service accounts in the previous group are intended for automaton access only, not for interactive logon by users.</span></span>  
  
#### <a name="to-set-the-appropriate-account-options"></a><span data-ttu-id="fce8a-230">设置适当的帐户选项</span><span class="sxs-lookup"><span data-stu-id="fce8a-230">To set the appropriate account options</span></span>  
  
1. <span data-ttu-id="fce8a-231">在中**Active Directory 用户和计算机**控制台，单击以展开域，然后单击以展开**用户**容器。</span><span class="sxs-lookup"><span data-stu-id="fce8a-231">In the **Active Directory Users and Computers** console, click to expand the domain, and then click to expand the **Users** container.</span></span>  
  
2. <span data-ttu-id="fce8a-232">右键单击该帐户，然后选择**属性**以显示**属性**帐户对话框。</span><span class="sxs-lookup"><span data-stu-id="fce8a-232">Right-click the account and then select **Properties** to display the **Properties** dialog box for the account.</span></span>  
  
3. <span data-ttu-id="fce8a-233">单击**帐户**选项卡**属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="fce8a-233">Click the **Account** tab of the **Properties** dialog box.</span></span>  
  
4. <span data-ttu-id="fce8a-234">单击以选中以下选项：</span><span class="sxs-lookup"><span data-stu-id="fce8a-234">Click to check the following options:</span></span>  
  
   -   <span data-ttu-id="fce8a-235">**用户不能更改密码**(企业安全人员将成批更改密码)。</span><span class="sxs-lookup"><span data-stu-id="fce8a-235">**User cannot change password** (enterprise security will batch change the passwords).</span></span>  
  
   -   <span data-ttu-id="fce8a-236">**密码永不过期**</span><span class="sxs-lookup"><span data-stu-id="fce8a-236">**Password never expires**</span></span>  
  
5. <span data-ttu-id="fce8a-237">单击**登录到**按钮以显示**登录工作站**对话框。</span><span class="sxs-lookup"><span data-stu-id="fce8a-237">Click the **Log On To** button to display the **Logon Workstations** dialog box.</span></span>  
  
6. <span data-ttu-id="fce8a-238">单击此选项以**以下计算机**，添加每台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fce8a-238">Click the option for **The following computers**, add each computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and then click **OK**.</span></span>  
  
7. <span data-ttu-id="fce8a-239">单击**遥控器**选项卡**属性**对话框的，然后单击以清除选项**启用远程控制**。</span><span class="sxs-lookup"><span data-stu-id="fce8a-239">Click the **Remote Control** tab of the **Properties** dialog box, and then click to clear the option to **Enable remote control**.</span></span>  
  
8. <span data-ttu-id="fce8a-240">单击**终端服务配置文件**选项卡**属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="fce8a-240">Click the **Terminal Services Profile** tab of the **Properties** dialog box.</span></span>  
  
9. <span data-ttu-id="fce8a-241">单击以选中选项**拒绝此用户的权限登录到任何终端服务器上**。</span><span class="sxs-lookup"><span data-stu-id="fce8a-241">Click to check the option to **Deny this user permissions to log on to any Terminal Server**.</span></span>  
  
10. <span data-ttu-id="fce8a-242">单击**确定**以关闭**属性**帐户对话框。</span><span class="sxs-lookup"><span data-stu-id="fce8a-242">Click **OK** to close the **Properties** dialog box for the account.</span></span>  
  
11. <span data-ttu-id="fce8a-243">对每个服务帐户重复步骤 3 至 10。</span><span class="sxs-lookup"><span data-stu-id="fce8a-243">Repeat steps 3 through 10 for each service account.</span></span>  
  
    <span data-ttu-id="fce8a-244">**BizTalk 用户帐户**</span><span class="sxs-lookup"><span data-stu-id="fce8a-244">**BizTalk User Accounts**</span></span>  
  
|<span data-ttu-id="fce8a-245">**用户名**</span><span class="sxs-lookup"><span data-stu-id="fce8a-245">**User name**</span></span>|<span data-ttu-id="fce8a-246">**First Name**</span><span class="sxs-lookup"><span data-stu-id="fce8a-246">**First Name**</span></span>|<span data-ttu-id="fce8a-247">**Last Name**</span><span class="sxs-lookup"><span data-stu-id="fce8a-247">**Last Name**</span></span>|<span data-ttu-id="fce8a-248">**全名**</span><span class="sxs-lookup"><span data-stu-id="fce8a-248">**Full Name**</span></span>|  
|-------------------|--------------------|-------------------|-------------------|  
|<span data-ttu-id="fce8a-249">BTUserAdmin</span><span class="sxs-lookup"><span data-stu-id="fce8a-249">BTUserAdmin</span></span>|<span data-ttu-id="fce8a-250">管理员</span><span class="sxs-lookup"><span data-stu-id="fce8a-250">Admin</span></span>|<span data-ttu-id="fce8a-251">BTUser</span><span class="sxs-lookup"><span data-stu-id="fce8a-251">BTUser</span></span>|<span data-ttu-id="fce8a-252">BizTalk 管理用户帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-252">BizTalk Administrative User Account</span></span>|  
|<span data-ttu-id="fce8a-253">BTUserDeploy</span><span class="sxs-lookup"><span data-stu-id="fce8a-253">BTUserDeploy</span></span>|<span data-ttu-id="fce8a-254">部署</span><span class="sxs-lookup"><span data-stu-id="fce8a-254">Deploy</span></span>|<span data-ttu-id="fce8a-255">BTUser</span><span class="sxs-lookup"><span data-stu-id="fce8a-255">BTUser</span></span>|<span data-ttu-id="fce8a-256">BizTalk 部署用户帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-256">BizTalk Deployment User Account</span></span>|  
|<span data-ttu-id="fce8a-257">BTUserHostInstance</span><span class="sxs-lookup"><span data-stu-id="fce8a-257">BTUserHostInstance</span></span>|<span data-ttu-id="fce8a-258">HostInstance</span><span class="sxs-lookup"><span data-stu-id="fce8a-258">HostInstance</span></span>|<span data-ttu-id="fce8a-259">BTUser</span><span class="sxs-lookup"><span data-stu-id="fce8a-259">BTUser</span></span>|<span data-ttu-id="fce8a-260">BizTalk 主机实例帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-260">BizTalk Host Instance Account</span></span>|  
|<span data-ttu-id="fce8a-261">BTUserHostIsolated</span><span class="sxs-lookup"><span data-stu-id="fce8a-261">BTUserHostIsolated</span></span>|<span data-ttu-id="fce8a-262">IsolatedlHost</span><span class="sxs-lookup"><span data-stu-id="fce8a-262">IsolatedlHost</span></span>|<span data-ttu-id="fce8a-263">BTUser</span><span class="sxs-lookup"><span data-stu-id="fce8a-263">BTUser</span></span>|<span data-ttu-id="fce8a-264">BizTalk 独立主机实例帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-264">BizTalk Isolated Host Instance Account</span></span>|  
|<span data-ttu-id="fce8a-265">BTUserInstall</span><span class="sxs-lookup"><span data-stu-id="fce8a-265">BTUserInstall</span></span>|<span data-ttu-id="fce8a-266">Install</span><span class="sxs-lookup"><span data-stu-id="fce8a-266">Install</span></span>|<span data-ttu-id="fce8a-267">BTUser</span><span class="sxs-lookup"><span data-stu-id="fce8a-267">BTUser</span></span>|<span data-ttu-id="fce8a-268">BizTalk 安装用户帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-268">BizTalk Installation User Account</span></span>|  
|<span data-ttu-id="fce8a-269">BTUserSupport</span><span class="sxs-lookup"><span data-stu-id="fce8a-269">BTUserSupport</span></span>|<span data-ttu-id="fce8a-270">支持</span><span class="sxs-lookup"><span data-stu-id="fce8a-270">Support</span></span>|<span data-ttu-id="fce8a-271">BTUser</span><span class="sxs-lookup"><span data-stu-id="fce8a-271">BTUser</span></span>|<span data-ttu-id="fce8a-272">BizTalk 支持访问帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-272">BizTalk Support Access Account</span></span>|  
  
#### <a name="to-set-the-appropriate-account-options-follow-these-steps"></a><span data-ttu-id="fce8a-273">若要设置适当的帐户选项，请执行以下步骤</span><span class="sxs-lookup"><span data-stu-id="fce8a-273">To set the appropriate account options follow these steps</span></span>  
  
1. <span data-ttu-id="fce8a-274">在中**Active Directory 用户和计算机**控制台中，单击以展开域，然后单击以展开**用户**容器。</span><span class="sxs-lookup"><span data-stu-id="fce8a-274">In the **Active Directory Users and Computers** console click to expand the domain, and then click to expand the **Users** container.</span></span>  
  
2. <span data-ttu-id="fce8a-275">右键单击该帐户，然后选择**属性**以显示**属性**帐户对话框。</span><span class="sxs-lookup"><span data-stu-id="fce8a-275">Right-click the account and then select **Properties** to display the **Properties** dialog box for the account.</span></span>  
  
3. <span data-ttu-id="fce8a-276">单击**帐户**选项卡**属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="fce8a-276">Click the **Account** tab of the **Properties** dialog box.</span></span>  
  
4. <span data-ttu-id="fce8a-277">单击以选中以下选项：</span><span class="sxs-lookup"><span data-stu-id="fce8a-277">Click to check the following options:</span></span>  
  
   -   <span data-ttu-id="fce8a-278">**用户不能更改密码**(企业安全人员将成批更改密码)。</span><span class="sxs-lookup"><span data-stu-id="fce8a-278">**User cannot change password** (enterprise security will batch change the passwords).</span></span>  
  
   -   <span data-ttu-id="fce8a-279">**密码永不过期**</span><span class="sxs-lookup"><span data-stu-id="fce8a-279">**Password never expires**</span></span>  
  
5. <span data-ttu-id="fce8a-280">单击**登录到**按钮以显示**登录工作站**对话框。</span><span class="sxs-lookup"><span data-stu-id="fce8a-280">Click the **Log On To** button to display the **Logon Workstations** dialog box.</span></span>  
  
6. <span data-ttu-id="fce8a-281">单击此选项以**以下计算机**，添加每台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fce8a-281">Click the option for **The following computers**, add each computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and then click **OK**.</span></span>  
  
7. <span data-ttu-id="fce8a-282">单击**遥控器**选项卡**属性**对话框中，然后单击以选中选项**启用远程控制**。</span><span class="sxs-lookup"><span data-stu-id="fce8a-282">Click the **Remote Control** tab of the **Properties** dialog box, and then click to check the option to **Enable remote control**.</span></span>  
  
8. <span data-ttu-id="fce8a-283">单击**终端服务配置文件**选项卡**属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="fce8a-283">Click the **Terminal Services Profile** tab of the **Properties** dialog box.</span></span>  
  
9. <span data-ttu-id="fce8a-284">单击以清除选项**拒绝此用户的权限登录到任何终端服务器上**。</span><span class="sxs-lookup"><span data-stu-id="fce8a-284">Click to clear the option to **Deny this user permissions to log on to any Terminal Server**.</span></span>  
  
10. <span data-ttu-id="fce8a-285">单击**确定**以关闭**属性**帐户对话框。</span><span class="sxs-lookup"><span data-stu-id="fce8a-285">Click **OK** to close the **Properties** dialog box for the account.</span></span>  
  
11. <span data-ttu-id="fce8a-286">对每个用户帐户重复步骤 3 至 10。</span><span class="sxs-lookup"><span data-stu-id="fce8a-286">Repeat steps 3 through 10 for each user account.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fce8a-287">如果要将提供给它们的角色分配给实际用户，则可以禁用上述任何帐户。</span><span class="sxs-lookup"><span data-stu-id="fce8a-287">Any of these accounts can be disabled if the roles they are to provide are assigned to actual users.</span></span> <span data-ttu-id="fce8a-288">在版本 1 和版本 2 的初期阶段中，假定这些帐户用于开发、测试版测试和 beta 测试环境。</span><span class="sxs-lookup"><span data-stu-id="fce8a-288">In the early stages of release one and release two, it is assumed that these accounts are used in the development, alpha test, and beta test environments.</span></span>  
  
    <span data-ttu-id="fce8a-289">**BizTalk 组帐户**</span><span class="sxs-lookup"><span data-stu-id="fce8a-289">**BizTalk Group Accounts**</span></span>  
  
|<span data-ttu-id="fce8a-290">**组名称**</span><span class="sxs-lookup"><span data-stu-id="fce8a-290">**Group Name**</span></span>|<span data-ttu-id="fce8a-291">**组类型**</span><span class="sxs-lookup"><span data-stu-id="fce8a-291">**Group Type**</span></span>|<span data-ttu-id="fce8a-292">**成员**</span><span class="sxs-lookup"><span data-stu-id="fce8a-292">**Members**</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fce8a-293">BizTalk Application Users</span><span class="sxs-lookup"><span data-stu-id="fce8a-293">BizTalk Application Users</span></span>|<span data-ttu-id="fce8a-294">全局或通用</span><span class="sxs-lookup"><span data-stu-id="fce8a-294">Global or Universal</span></span>|<span data-ttu-id="fce8a-295">-BTServiceHost</span><span class="sxs-lookup"><span data-stu-id="fce8a-295">-   BTServiceHost</span></span><br /><span data-ttu-id="fce8a-296">-BTUserHostInstance</span><span class="sxs-lookup"><span data-stu-id="fce8a-296">-   BTUserHostInstance</span></span>|  
|<span data-ttu-id="fce8a-297">BizTalk 开发用户</span><span class="sxs-lookup"><span data-stu-id="fce8a-297">BizTalk Development Users</span></span>|<span data-ttu-id="fce8a-298">全局或通用</span><span class="sxs-lookup"><span data-stu-id="fce8a-298">Global or Universal</span></span>|<span data-ttu-id="fce8a-299">（开发用户的本地域帐户）**注意：** 最佳做法是，不要启用上游环境中的 BizTalk 开发用户组。</span><span class="sxs-lookup"><span data-stu-id="fce8a-299">(local domain accounts of development users) **Note:**  As a best practice, do not enable the BizTalk Development Users group in up-line environments.</span></span>|  
|<span data-ttu-id="fce8a-300">BizTalk 部署用户</span><span class="sxs-lookup"><span data-stu-id="fce8a-300">BizTalk Deployment Users</span></span>|<span data-ttu-id="fce8a-301">全局或通用</span><span class="sxs-lookup"><span data-stu-id="fce8a-301">Global or Universal</span></span>|<span data-ttu-id="fce8a-302">（部署用户的本地域帐户）</span><span class="sxs-lookup"><span data-stu-id="fce8a-302">(local domain accounts of deployment users)</span></span>|  
|<span data-ttu-id="fce8a-303">BizTalk 主机用户</span><span class="sxs-lookup"><span data-stu-id="fce8a-303">BizTalk Host Users</span></span>|<span data-ttu-id="fce8a-304">全局或通用</span><span class="sxs-lookup"><span data-stu-id="fce8a-304">Global or Universal</span></span>|<span data-ttu-id="fce8a-305">BTUserHostInstance</span><span class="sxs-lookup"><span data-stu-id="fce8a-305">BTUserHostInstance</span></span>|  
|<span data-ttu-id="fce8a-306">BizTalk Isolated Host Users</span><span class="sxs-lookup"><span data-stu-id="fce8a-306">BizTalk Isolated Host Users</span></span>|<span data-ttu-id="fce8a-307">全局或通用</span><span class="sxs-lookup"><span data-stu-id="fce8a-307">Global or Universal</span></span>|<span data-ttu-id="fce8a-308">-BTServiceHostIso</span><span class="sxs-lookup"><span data-stu-id="fce8a-308">-   BTServiceHostIso</span></span><br /><span data-ttu-id="fce8a-309">-BTUserHostInstance</span><span class="sxs-lookup"><span data-stu-id="fce8a-309">-   BTUserHostInstance</span></span>|  
|<span data-ttu-id="fce8a-310">BizTalk Server Administrators</span><span class="sxs-lookup"><span data-stu-id="fce8a-310">BizTalk Server Administrators</span></span>|<span data-ttu-id="fce8a-311">全局或通用</span><span class="sxs-lookup"><span data-stu-id="fce8a-311">Global or Universal</span></span>|<span data-ttu-id="fce8a-312">-BTUserAdmin</span><span class="sxs-lookup"><span data-stu-id="fce8a-312">-   BTUserAdmin</span></span><br /><span data-ttu-id="fce8a-313">-BTUserInstall</span><span class="sxs-lookup"><span data-stu-id="fce8a-313">-   BTUserInstall</span></span><br /><span data-ttu-id="fce8a-314">BizTalk 开发用户</span><span class="sxs-lookup"><span data-stu-id="fce8a-314">-   BizTalk Development Users</span></span><br /><span data-ttu-id="fce8a-315">BizTalk 部署用户</span><span class="sxs-lookup"><span data-stu-id="fce8a-315">-   BizTalk Deployment Users</span></span>|  
|<span data-ttu-id="fce8a-316">BizTalk 支持用户</span><span class="sxs-lookup"><span data-stu-id="fce8a-316">BizTalk Support Users</span></span>|<span data-ttu-id="fce8a-317">全局或通用</span><span class="sxs-lookup"><span data-stu-id="fce8a-317">Global or Universal</span></span>|<span data-ttu-id="fce8a-318">BTUserSupport（支持用户的本地域帐户）</span><span class="sxs-lookup"><span data-stu-id="fce8a-318">BTUserSupport (local domain accounts of support users)</span></span>|  
|<span data-ttu-id="fce8a-319">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="fce8a-319">SSO Administrators</span></span>|<span data-ttu-id="fce8a-320">全局或通用</span><span class="sxs-lookup"><span data-stu-id="fce8a-320">Global or Universal</span></span>|<span data-ttu-id="fce8a-321">-SSOService</span><span class="sxs-lookup"><span data-stu-id="fce8a-321">-   SSOService</span></span><br /><span data-ttu-id="fce8a-322">-BTUserInstall</span><span class="sxs-lookup"><span data-stu-id="fce8a-322">-   BTUserInstall</span></span><br /><span data-ttu-id="fce8a-323">本地管理员</span><span class="sxs-lookup"><span data-stu-id="fce8a-323">-   Local Administrator</span></span>|  
|<span data-ttu-id="fce8a-324">SSO Affiliate Administrators</span><span class="sxs-lookup"><span data-stu-id="fce8a-324">SSO Affiliate Administrators</span></span>|<span data-ttu-id="fce8a-325">全局或通用</span><span class="sxs-lookup"><span data-stu-id="fce8a-325">Global or Universal</span></span>|<span data-ttu-id="fce8a-326">BizTalk 开发用户</span><span class="sxs-lookup"><span data-stu-id="fce8a-326">-   BizTalk Development Users</span></span><br /><span data-ttu-id="fce8a-327">BizTalk 部署用户</span><span class="sxs-lookup"><span data-stu-id="fce8a-327">-   BizTalk Deployment Users</span></span><br /><span data-ttu-id="fce8a-328">-BTServiceHostIso</span><span class="sxs-lookup"><span data-stu-id="fce8a-328">-   BTServiceHostIso</span></span><br /><span data-ttu-id="fce8a-329">-   \<控制台用户\></span><span class="sxs-lookup"><span data-stu-id="fce8a-329">-   \<console user\></span></span>|  
|<span data-ttu-id="fce8a-330">Windows SharePoint Services 管理员</span><span class="sxs-lookup"><span data-stu-id="fce8a-330">Windows SharePoint Services Administrators</span></span>|<span data-ttu-id="fce8a-331">全局或通用</span><span class="sxs-lookup"><span data-stu-id="fce8a-331">Global or Universal</span></span>|<span data-ttu-id="fce8a-332">-SPAdmin</span><span class="sxs-lookup"><span data-stu-id="fce8a-332">-   SPAdmin</span></span><br /><span data-ttu-id="fce8a-333">-BTUserInstall</span><span class="sxs-lookup"><span data-stu-id="fce8a-333">-   BTUserInstall</span></span><br /><span data-ttu-id="fce8a-334">-BTUserDeploy</span><span class="sxs-lookup"><span data-stu-id="fce8a-334">-   BTUserDeploy</span></span><br /><span data-ttu-id="fce8a-335">BizTalk 开发用户</span><span class="sxs-lookup"><span data-stu-id="fce8a-335">-   BizTalk Development Users</span></span><br /><span data-ttu-id="fce8a-336">BizTalk 部署用户</span><span class="sxs-lookup"><span data-stu-id="fce8a-336">-   BizTalk Deployment users</span></span>|  
  
 <span data-ttu-id="fce8a-337">有关域组的建议和说明：</span><span class="sxs-lookup"><span data-stu-id="fce8a-337">Recommendations and notes on domain groups:</span></span>  
  
- <span data-ttu-id="fce8a-338">在安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 前创建组和添加成员。</span><span class="sxs-lookup"><span data-stu-id="fce8a-338">Create the groups and add members prior to installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="fce8a-339">域组可以为全局组或通用组。</span><span class="sxs-lookup"><span data-stu-id="fce8a-339">Domain groups can be Global or Universal groups.</span></span>  
  
- <span data-ttu-id="fce8a-340">使用 *\<DomainName\>\\< 用户名\>* 时配置向导中指定的域帐户信息。</span><span class="sxs-lookup"><span data-stu-id="fce8a-340">Use *\<DomainName\>\\<UserName\>* when specifying domain account information in the Configuration Wizard.</span></span>  
  
- <span data-ttu-id="fce8a-341">组和用户/服务帐户必须属于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机所属于的域（配置向导将对此进行检查并且将不会显示包含来自其他域的帐户的帐户或组）。</span><span class="sxs-lookup"><span data-stu-id="fce8a-341">Groups and user/service accounts must belong to the domain in which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer belongs (the Configuration Wizard checks this and will not display accounts or groups containing accounts from other domains).</span></span>  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="fce8a-342"> 对于所有群集方案都要求使用域帐户。</span><span class="sxs-lookup"><span data-stu-id="fce8a-342"> requires domain accounts for all clustering scenarios.</span></span>  
  
- <span data-ttu-id="fce8a-343">安装时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，控制台用户必须是以下组的成员：</span><span class="sxs-lookup"><span data-stu-id="fce8a-343">When installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the console user needs to be a member of the following groups:</span></span>  
  
  - <span data-ttu-id="fce8a-344">BizTalk Server Administrators</span><span class="sxs-lookup"><span data-stu-id="fce8a-344">BizTalk Server Administrators</span></span>  
  
  - <span data-ttu-id="fce8a-345">SSO Administrators（只在配置主密钥服务器时）</span><span class="sxs-lookup"><span data-stu-id="fce8a-345">SSO Administrators (only when configuring the master secret server)</span></span>  
  
  - <span data-ttu-id="fce8a-346">Windows 管理员</span><span class="sxs-lookup"><span data-stu-id="fce8a-346">Windows administrator</span></span>  
  
  - [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]<span data-ttu-id="fce8a-347"> 管理员</span><span class="sxs-lookup"><span data-stu-id="fce8a-347"> administrator</span></span>  
  
  - <span data-ttu-id="fce8a-348">OLAP 管理员</span><span class="sxs-lookup"><span data-stu-id="fce8a-348">OLAP administrator</span></span>  
  
    <span data-ttu-id="fce8a-349">BTUserInstall 帐户应该用于安装和配置，并且在完成配置后应被禁用。</span><span class="sxs-lookup"><span data-stu-id="fce8a-349">The BTUserInstall account should be used for installation and configuration and should be disabled after configuration is complete.</span></span>  
  
- <span data-ttu-id="fce8a-350">若要允许消息事件和服务实例跟踪将业务流程附加到调试器，开发人员需要属于 BizTalk Server Administrators 组中，如上面的部分中所述**BizTalk 开发帐户**.</span><span class="sxs-lookup"><span data-stu-id="fce8a-350">To allow message event and service instance tracking to attach orchestrations to the debugger, the developer needs to belong to the BizTalk Server Administrators group, as outlined above in the section **BizTalk Development Accounts**.</span></span>  
  
## <a name="local-administrator-accounts"></a><span data-ttu-id="fce8a-351">本地管理员帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-351">Local Administrator Accounts</span></span>  
 <span data-ttu-id="fce8a-352">确认或将以下帐户和帐户组添加到 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 计算机上的本地管理员组：</span><span class="sxs-lookup"><span data-stu-id="fce8a-352">Confirm or add the following accounts and groups to the Local Administrators group on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer:</span></span>  
  
- <span data-ttu-id="fce8a-353">Domain\BTUserInstall（在完成配置后禁用）</span><span class="sxs-lookup"><span data-stu-id="fce8a-353">Domain\BTUserInstall (disable when configuration is complete)</span></span>  
  
- <span data-ttu-id="fce8a-354">Domain\BTUserDeploy（在完成部署后在生产中禁用）</span><span class="sxs-lookup"><span data-stu-id="fce8a-354">Domain\BTUserDeploy (disable in production when deployment is complete)</span></span>  
  
- <span data-ttu-id="fce8a-355">Domain\SPAdmin</span><span class="sxs-lookup"><span data-stu-id="fce8a-355">Domain\SPAdmin</span></span>  
  
- <span data-ttu-id="fce8a-356">Domain\SQLAdmin</span><span class="sxs-lookup"><span data-stu-id="fce8a-356">Domain\SQLAdmin</span></span>  
  
- <span data-ttu-id="fce8a-357">Domain\SQLService</span><span class="sxs-lookup"><span data-stu-id="fce8a-357">Domain\SQLService</span></span>  
  
- <span data-ttu-id="fce8a-358">域 \biztalk 开发用户 （在上游环境）</span><span class="sxs-lookup"><span data-stu-id="fce8a-358">Domain\BizTalk Development Users (omit in up line environments)</span></span>  
  
- <span data-ttu-id="fce8a-359">域\BizTalk 部署用户（在开发环境中忽略）</span><span class="sxs-lookup"><span data-stu-id="fce8a-359">Domain\BizTalk Deployment Users (omit in development environments)</span></span>  
  
  <span data-ttu-id="fce8a-360">确认或将以下帐户和帐户组添加到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上的本地管理员组：</span><span class="sxs-lookup"><span data-stu-id="fce8a-360">Confirm or add the following accounts and groups to the Local Administrators group on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer:</span></span>  
  
- <span data-ttu-id="fce8a-361">Domain\BTUserInstall（在完成配置后禁用）</span><span class="sxs-lookup"><span data-stu-id="fce8a-361">Domain\BTUserInstall (disable when configuration is complete)</span></span>  
  
- <span data-ttu-id="fce8a-362">Domain\BTUserDeploy（在完成部署后在生产中禁用）</span><span class="sxs-lookup"><span data-stu-id="fce8a-362">Domain\BTUserDeploy (disable in production when deployment is complete)</span></span>  
  
- <span data-ttu-id="fce8a-363">Domain\BTUserSupport</span><span class="sxs-lookup"><span data-stu-id="fce8a-363">Domain\BTUserSupport</span></span>  
  
- <span data-ttu-id="fce8a-364">Domain\SPAdmin</span><span class="sxs-lookup"><span data-stu-id="fce8a-364">Domain\SPAdmin</span></span>  
  
- <span data-ttu-id="fce8a-365">域\BizTalk 开发用户（在上游环境中忽略）</span><span class="sxs-lookup"><span data-stu-id="fce8a-365">Domain\BizTalk Development Users (omit in upline environments)</span></span>  
  
- <span data-ttu-id="fce8a-366">域\BizTalk 部署用户（在开发环境中忽略）</span><span class="sxs-lookup"><span data-stu-id="fce8a-366">Domain\BizTalk Deployment Users (omit in development environments)</span></span>  
  
## <a name="sql-server-administrator-accounts"></a><span data-ttu-id="fce8a-367">SQL Server 管理员帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-367">SQL Server Administrator Accounts</span></span>  
 <span data-ttu-id="fce8a-368">安装程序接受来自安装人员的输入，并将 SQL 角色分配给用户和组：</span><span class="sxs-lookup"><span data-stu-id="fce8a-368">Setup programs accept input from the installer and assigns SQL roles to users and groups:</span></span>  
  
- <span data-ttu-id="fce8a-369">在 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 安装期间，向 SPAdmin 帐户授予 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 计算机上的安全管理员和数据库创建者权限。</span><span class="sxs-lookup"><span data-stu-id="fce8a-369">During [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] setup, the SPAdmin account is granted Security Administrator and Database Creator rights on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span> <span data-ttu-id="fce8a-370">如果 SPAdmin 帐户是本地管理员组的成员，则可以删除这些权限。</span><span class="sxs-lookup"><span data-stu-id="fce8a-370">These rights can be removed if the SPAdmin account is a member of the Local Administrators group.</span></span>  
  
## <a name="e-mail-account"></a><span data-ttu-id="fce8a-371">电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-371">E-Mail Account</span></span>  
 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]<span data-ttu-id="fce8a-372"> 将基于某些系统事件发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fce8a-372"> will send mail based on certain system events.</span></span> <span data-ttu-id="fce8a-373">安装程序将在配置过程中提示电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="fce8a-373">Setup prompts for an e-mail address during the configuration process.</span></span> <span data-ttu-id="fce8a-374">为此目的创建电子邮件别名，并且在安装和单元测试期间监控此别名。</span><span class="sxs-lookup"><span data-stu-id="fce8a-374">Create e-mail aliases for this purpose and monitor the alias during setup and unit testing.</span></span> <span data-ttu-id="fce8a-375">在生产环境中，此帐户应该可由监控系统的系统管理员访问。</span><span class="sxs-lookup"><span data-stu-id="fce8a-375">In the production environment, this account should be accessible by a system administrator who is monitoring the system.</span></span>  
  
 <span data-ttu-id="fce8a-376">使用的电子邮件帐户[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]是**WSS 管理员电子邮件**帐户。</span><span class="sxs-lookup"><span data-stu-id="fce8a-376">The e-mail account used by [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] is the **WSS Administrator E-mail** account.</span></span>  
  
## <a name="password-considerations-for-development"></a><span data-ttu-id="fce8a-377">有关开发的密码注意事项</span><span class="sxs-lookup"><span data-stu-id="fce8a-377">Password Considerations for Development</span></span>  
 <span data-ttu-id="fce8a-378">对于开发和测试环境，可按标准设置帐户密码并且帐户密码可分发。</span><span class="sxs-lookup"><span data-stu-id="fce8a-378">For development and test environments, account passwords can be set by a standard and be distributable.</span></span> <span data-ttu-id="fce8a-379">安装人员的标准各异；本主题采用一个名字单元，它由服务组件的首字母大写缩写加上后随的帐户其余部分（服务或用户）的小写字母缩写组成。</span><span class="sxs-lookup"><span data-stu-id="fce8a-379">Installer standards vary; this topic uses the template of initial capital letters abbreviating the service component followed by a lower-case abbreviation for the rest of the account (service or user).</span></span> <span data-ttu-id="fce8a-380">对于服务帐户，本主题使用“Serv”；对于用户帐户，本主题使用“User”。</span><span class="sxs-lookup"><span data-stu-id="fce8a-380">For service accounts, this topic uses 'Serv', for user accounts this topic uses 'User'.</span></span>  
  
 <span data-ttu-id="fce8a-381">例如：</span><span class="sxs-lookup"><span data-stu-id="fce8a-381">For example:</span></span>  
  
- <span data-ttu-id="fce8a-382">Windows SharePoint Services (SharePoint) 服务和管理员帐户 (SPAdmin) 密码: SPServ。</span><span class="sxs-lookup"><span data-stu-id="fce8a-382">Windows SharePoint Services (SharePoint) Service and admin account (SPAdmin) passwords: 'SPServ'.</span></span>  
  
- <span data-ttu-id="fce8a-383">BizTalk 服务帐户密码: BTServ。</span><span class="sxs-lookup"><span data-stu-id="fce8a-383">BizTalk Service account passwords: 'BTServ'.</span></span>  
  
- <span data-ttu-id="fce8a-384">BizTalk 用户帐户密码: BTUser。</span><span class="sxs-lookup"><span data-stu-id="fce8a-384">BizTalk User account passwords: 'BTUser'.</span></span>  
  
  <span data-ttu-id="fce8a-385">某些 IT 环境要求密码包含非 alpha 和/或数字字符。</span><span class="sxs-lookup"><span data-stu-id="fce8a-385">Some IT environments require passwords to contain non-alpha and/or numeric characters.</span></span> <span data-ttu-id="fce8a-386">在此环境下，您可以将美元符号 ($) 替换为“s”，将“at”符号 (@) 替换为“a”。</span><span class="sxs-lookup"><span data-stu-id="fce8a-386">In this scenario you could substitute a dollar sign ($) for "s", and an 'at' sign (@) for "a".</span></span> <span data-ttu-id="fce8a-387">这些符号只是示例；开发最适合于您的用于具有半公共密码的共享帐户的模式。</span><span class="sxs-lookup"><span data-stu-id="fce8a-387">The symbols are samples; develop a pattern that works best for you for shared accounts with semi-public passwords.</span></span>  
  
  <span data-ttu-id="fce8a-388">在开发环境中使用的可重复分发的密码示例是：</span><span class="sxs-lookup"><span data-stu-id="fce8a-388">Sample redistributable passwords in use in the development environment are:</span></span>  
  
- <span data-ttu-id="fce8a-389">BT$erv99           BizTalk 服务帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-389">BT$erv99           BizTalk Service Accounts</span></span>  
  
- <span data-ttu-id="fce8a-390">BTU$er99          BizTalk 用户帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-390">BTU$er99          BizTalk User Accounts</span></span>  
  
- <span data-ttu-id="fce8a-391">SP$erv99           WSS 服务帐户 (SPAdmin)</span><span class="sxs-lookup"><span data-stu-id="fce8a-391">SP$erv99           WSS Service Account (SPAdmin)</span></span>  
  
- <span data-ttu-id="fce8a-392">SQL$erv99         SQL 服务/访问/管理员帐户</span><span class="sxs-lookup"><span data-stu-id="fce8a-392">SQL$erv99         SQL Service/Access/Admin Account</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fce8a-393">这些建议只针对开发和共享环境，不建议或不鼓励用于公司密码策略。</span><span class="sxs-lookup"><span data-stu-id="fce8a-393">These recommendations are for development and shared environments only and do not recommend or discourage the use of corporate password policies.</span></span> <span data-ttu-id="fce8a-394">有关密码要求，请向您的网络管理员咨询。</span><span class="sxs-lookup"><span data-stu-id="fce8a-394">See your network administrator for password requirements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fce8a-395">如果公司密码策略包括生成的密码，您需要注意的是，某些符号和符号组合是对于 XML 有特殊用途的字符。</span><span class="sxs-lookup"><span data-stu-id="fce8a-395">If corporate password policy includes generated passwords, be advised that some symbols and symbol combinations are special-use characters to XML.</span></span> <span data-ttu-id="fce8a-396">不恰当地使用这些字符将导致配置 XML 文件在配置过程中无法打开。</span><span class="sxs-lookup"><span data-stu-id="fce8a-396">Inappropriate use of these characters will prevent configuration XML files from being opened during the configuration process.</span></span> <span data-ttu-id="fce8a-397">这些符号包括"&"、"\<"，"\>"、 和双单引号，并且可能包括其他人。</span><span class="sxs-lookup"><span data-stu-id="fce8a-397">These symbols include "&", "\<", "\>", single- and double-quote, and may include others.</span></span> <span data-ttu-id="fce8a-398">请在执行基于文件的配置前测试配置 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="fce8a-398">Test the configuration XML file prior to executing file-based configuration.</span></span> <span data-ttu-id="fce8a-399">您可以通过在 Internet Explorer（或某一 XML 编辑器）中打开嵌入了生成的密码的文档，测试文件是否可靠地用于适当的 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="fce8a-399">You can test this reliably for proper XML formatting by opening the document in Internet Explorer (or an XML editor) with the generated passwords embedded therein.</span></span>  
  
 <span data-ttu-id="fce8a-400">有关部署上游环境中保证密码安全的详细信息 (包括要测试的方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置文件)，请参阅[BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)。</span><span class="sxs-lookup"><span data-stu-id="fce8a-400">For more information about deployment of secure passwords in up-line environments (including the method to test a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration file), see [Configuration Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fce8a-401">请参阅</span><span class="sxs-lookup"><span data-stu-id="fce8a-401">See Also</span></span>  
 [<span data-ttu-id="fce8a-402">故障排除的 BizTalk Server 权限</span><span class="sxs-lookup"><span data-stu-id="fce8a-402">Troubleshooting BizTalk Server Permissions</span></span>](../core/troubleshooting-biztalk-server-permissions.md)