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
ms.openlocfilehash: dad79e7e3003f8ee66aab0838b10f44f8b519258
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332509"
---
# <a name="guidelines-for-implementing-active-directory-permissions-on-multi-server-biztalk-installations"></a><span data-ttu-id="a0e10-102">准则用于实现在多服务器 BizTalk 安装在 Active Directory 权限</span><span class="sxs-lookup"><span data-stu-id="a0e10-102">Guidelines for Implementing Active Directory Permissions on Multi Server BizTalk Installations</span></span>
<span data-ttu-id="a0e10-103">本主题介绍有关创建 Active Directory 组织单位，其中包含的用户帐户和使用 Microsoft 中的组的准则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="a0e10-103">This topic describes guidelines for creating Active Directory Organizational Units, which consist of the user accounts and groups that you use in a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span>  
  
 <span data-ttu-id="a0e10-104">此处创建的帐户不需要在域中具有超出普通用户的权限。</span><span class="sxs-lookup"><span data-stu-id="a0e10-104">The accounts created herein do not need permissions in the domain beyond those of ordinary users.</span></span> <span data-ttu-id="a0e10-105">域帐户可能需要包括的信任边界内提升的权限：</span><span class="sxs-lookup"><span data-stu-id="a0e10-105">The domain accounts may need elevated privileges within the trust boundary that includes:</span></span>  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- <span data-ttu-id="a0e10-106">Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] (在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]server)</span><span class="sxs-lookup"><span data-stu-id="a0e10-106">Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] (on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] server)</span></span>  
  
- <span data-ttu-id="a0e10-107">Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0e10-107">Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]</span></span>  
  
- <span data-ttu-id="a0e10-108">外部数据库 1</span><span class="sxs-lookup"><span data-stu-id="a0e10-108">External Database One</span></span>  
  
- <span data-ttu-id="a0e10-109">外部数据库 2</span><span class="sxs-lookup"><span data-stu-id="a0e10-109">External Database Two</span></span>  
  
- <span data-ttu-id="a0e10-110">外部数据库*N*</span><span class="sxs-lookup"><span data-stu-id="a0e10-110">External Database *N*</span></span>  
  
  <span data-ttu-id="a0e10-111">例如，域帐户可能需要被授予权限来作为外部数据库宿主的系统上执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="a0e10-111">For example, a domain account may need to be granted rights to perform certain actions on the systems hosting external databases.</span></span> <span data-ttu-id="a0e10-112">在另一种情况下，帐户可能需要将文件写入文件存放文件夹，需要对文件夹的写访问。</span><span class="sxs-lookup"><span data-stu-id="a0e10-112">In another case, an account may need to write a file to a file drop folder, requiring write access to the folder.</span></span>  
  
  <span data-ttu-id="a0e10-113">使用**Active Directory 用户和计算机**控制台来创建和管理域用户和组帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e10-113">Use the **Active Directory Users and Computers** console to create and manage domain user and group accounts.</span></span> <span data-ttu-id="a0e10-114">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Active Directory 用户和计算机**到启动**Active Directory 用户和计算机**控制台。</span><span class="sxs-lookup"><span data-stu-id="a0e10-114">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Active Directory Users and Computers** to start the **Active Directory Users and Computers** console.</span></span>  
  
## <a name="biztalk-server-installation-and-configuration-account"></a><span data-ttu-id="a0e10-115">BizTalk Server 安装和配置帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-115">BizTalk Server Installation and Configuration Account</span></span>  
 <span data-ttu-id="a0e10-116">在开发环境中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序并[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置向导要求使用具有管理权限的帐户上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]系统。</span><span class="sxs-lookup"><span data-stu-id="a0e10-116">In the development environment, the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation program and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Wizard require the use of an account with administrative rights on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] systems.</span></span> <span data-ttu-id="a0e10-117">可以立即吊销权限或只要安装和配置不完整，将禁用该帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e10-117">Rights can be revoked or the account disabled as soon as setup and configuration are complete.</span></span> <span data-ttu-id="a0e10-118">该帐户必须还属于若干 BizTalk 组，在以下各节中介绍。</span><span class="sxs-lookup"><span data-stu-id="a0e10-118">The account must also belong to several BizTalk groups, covered in the following sections.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0e10-119">你将不能配置 SSO 组件，如果用于安装的帐户属于与服务器不同的 Active Directory 林中。</span><span class="sxs-lookup"><span data-stu-id="a0e10-119">You will not be able to configure SSO components if the account used for installation belongs to a different Active Directory forest than the server.</span></span> <span data-ttu-id="a0e10-120">如果还没有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序帐户，请使用本地管理员帐户进行 SSO 配置。</span><span class="sxs-lookup"><span data-stu-id="a0e10-120">If you do not have a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installer account, use a local administrator account for SSO configuration.</span></span> <span data-ttu-id="a0e10-121">在安装期间，例如，需要登录到使用不同的凭据的资源，此方法可能会造成其他问题。</span><span class="sxs-lookup"><span data-stu-id="a0e10-121">This methodology may create other issues during installation, such as the need to log on to resources using different credentials.</span></span>  
  
## <a name="biztalk-server-development-accounts"></a><span data-ttu-id="a0e10-122">BizTalk Server 开发帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-122">BizTalk Server Development Accounts</span></span>  
 <span data-ttu-id="a0e10-123">执行操作的个人[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发需要能够访问适配器、 接收和发送处理程序，并接收位置。</span><span class="sxs-lookup"><span data-stu-id="a0e10-123">Individuals doing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development require access to adapters, receive and send handlers, and receive locations.</span></span> <span data-ttu-id="a0e10-124">这一访问要求域开发人员组的成员**BizTalk Server Administrators**并**SSO Affiliate Administrators**组。</span><span class="sxs-lookup"><span data-stu-id="a0e10-124">This access requires the domain developer group to be members of the **BizTalk Server Administrators** and **SSO Affiliate Administrators** groups.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0e10-125">Active Directory 具有有关类型的组可以包含外来域用户和组可包含其他组中的类型的限制。</span><span class="sxs-lookup"><span data-stu-id="a0e10-125">Active Directory has restrictions regarding the types of groups that can contain foreign domain users, and the types of groups that can be contained in other groups.</span></span> <span data-ttu-id="a0e10-126">组和帐户下面创建单一域上的多服务器环境中测试。</span><span class="sxs-lookup"><span data-stu-id="a0e10-126">The groups and accounts created below are tested in a multiserver environment on a single domain.</span></span>  
  
## <a name="biztalk-server-deployment-accounts"></a><span data-ttu-id="a0e10-127">BizTalk Server 部署帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-127">BizTalk Server Deployment Accounts</span></span>  
 <span data-ttu-id="a0e10-128">部署的个人[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序将需要是本地系统上的管理员，并且可能需要在环境中的其他权限。</span><span class="sxs-lookup"><span data-stu-id="a0e10-128">Individuals deploying [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications will need to be administrators on the local systems and may require other permissions in the environment.</span></span> <span data-ttu-id="a0e10-129">本主题中情况下为此目的而引用了 BizTalk Server 部署帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e10-129">A BizTalk Server deployment account is referenced in this topic for this purpose.</span></span>  
  
 <span data-ttu-id="a0e10-130">这一访问要求域部署组的成员**BizTalk Server Administrators**并**SSO Affiliate Administrators**组。</span><span class="sxs-lookup"><span data-stu-id="a0e10-130">This access requires the domain deployment group to be members of the **BizTalk Server Administrators** and **SSO Affiliate Administrators** groups.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0e10-131">你将不能配置 SSO 组件，如果用于安装的帐户属于与服务器不同的 Active Directory 林中。</span><span class="sxs-lookup"><span data-stu-id="a0e10-131">You will not be able to configure SSO components if the account used for installation belongs to a different Active Directory forest than the server.</span></span> <span data-ttu-id="a0e10-132">如果你没有 BizTalk Server 部署帐户，使用本地管理员帐户进行 SSO 配置。</span><span class="sxs-lookup"><span data-stu-id="a0e10-132">If you do not have a BizTalk Server deployment account, use a local administrator account for SSO configuration.</span></span> <span data-ttu-id="a0e10-133">在安装期间，例如，需要登录到使用不同的凭据的资源，此方法可能会造成其他问题。</span><span class="sxs-lookup"><span data-stu-id="a0e10-133">This methodology may create other issues during installation, such as the need to log on to resources using different credentials.</span></span>  
  
## <a name="biztalk-server-support-accounts"></a><span data-ttu-id="a0e10-134">BizTalk Server 支持帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-134">BizTalk Server Support Accounts</span></span>  
 <span data-ttu-id="a0e10-135">支持的个人[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序将需要是本地系统上的管理员。</span><span class="sxs-lookup"><span data-stu-id="a0e10-135">Individuals supporting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications will need to be administrators on the local systems.</span></span> <span data-ttu-id="a0e10-136">本主题中情况下为此目的而引用了 BizTalk 支持帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e10-136">A BizTalk support account is referenced in this topic for this purpose.</span></span>  
  
 <span data-ttu-id="a0e10-137">这一访问要求域支持组的成员**BizTalk Server Administrators**组。</span><span class="sxs-lookup"><span data-stu-id="a0e10-137">This access requires the domain support group to be members of the **BizTalk Server Administrators** group.</span></span>  
  
## <a name="sql-server-service-accounts"></a><span data-ttu-id="a0e10-138">SQL Server 服务帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-138">SQL Server Service Accounts</span></span>  
 <span data-ttu-id="a0e10-139">服务正在运行[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例必须属于与安装、 开发和部署的帐户相同的 Active Directory 域[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组件。</span><span class="sxs-lookup"><span data-stu-id="a0e10-139">The service running the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance must belong to the same Active Directory domain as the accounts installing, developing, and deploying [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components.</span></span>  
  
- <span data-ttu-id="a0e10-140">使用**SQLAdmin**执行管理功能 （交互式登录）。</span><span class="sxs-lookup"><span data-stu-id="a0e10-140">Use **SQLAdmin** for administrative functions (interactive logon).</span></span>  
  
- <span data-ttu-id="a0e10-141">使用**SQLService**管理服务 （无交互式登录）。</span><span class="sxs-lookup"><span data-stu-id="a0e10-141">Use **SQLService** to manage the service (no interactive logon).</span></span>  
  
- <span data-ttu-id="a0e10-142">使用**SQLAccess**访问外部数据库。</span><span class="sxs-lookup"><span data-stu-id="a0e10-142">Use **SQLAccess** to access external databases.</span></span>  
  
- <span data-ttu-id="a0e10-143">SQLAdmin 必须是本地 Administrators 组的成员上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]系统。</span><span class="sxs-lookup"><span data-stu-id="a0e10-143">SQLAdmin must be a member of the local Administrators group on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] system.</span></span>  
  
- <span data-ttu-id="a0e10-144">SQLService 必须是本地 Administrators 组的成员上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]系统，需要授予**作为服务登录**用户权限。</span><span class="sxs-lookup"><span data-stu-id="a0e10-144">SQLService must be a member of the local Administrators group on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] system and needs to be granted the **Log on as a service** user right.</span></span>  
  
- <span data-ttu-id="a0e10-145">SQLAccess 需要对远程数据库服务器上的相应权限。</span><span class="sxs-lookup"><span data-stu-id="a0e10-145">SQLAccess needs appropriate rights on the remote database servers.</span></span>  
  
  <span data-ttu-id="a0e10-146">**SQL 帐户：**</span><span class="sxs-lookup"><span data-stu-id="a0e10-146">**SQL Accounts:**</span></span>  
  
|<span data-ttu-id="a0e10-147">**用户名**</span><span class="sxs-lookup"><span data-stu-id="a0e10-147">**User name**</span></span>|<span data-ttu-id="a0e10-148">**First Name**</span><span class="sxs-lookup"><span data-stu-id="a0e10-148">**First Name**</span></span>|<span data-ttu-id="a0e10-149">**Last Name**</span><span class="sxs-lookup"><span data-stu-id="a0e10-149">**Last Name**</span></span>|<span data-ttu-id="a0e10-150">**全名**</span><span class="sxs-lookup"><span data-stu-id="a0e10-150">**Full Name**</span></span>|  
|-------------------|--------------------|-------------------|-------------------|  
|<span data-ttu-id="a0e10-151">SQLService</span><span class="sxs-lookup"><span data-stu-id="a0e10-151">SQLService</span></span>|<span data-ttu-id="a0e10-152">SQL</span><span class="sxs-lookup"><span data-stu-id="a0e10-152">SQL</span></span>|<span data-ttu-id="a0e10-153">SQLService</span><span class="sxs-lookup"><span data-stu-id="a0e10-153">SQLService</span></span>|<span data-ttu-id="a0e10-154">SQL 服务帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-154">SQL Service Account</span></span>|  
|<span data-ttu-id="a0e10-155">SQLAdmin</span><span class="sxs-lookup"><span data-stu-id="a0e10-155">SQLAdmin</span></span>|<span data-ttu-id="a0e10-156">管理员</span><span class="sxs-lookup"><span data-stu-id="a0e10-156">Admin</span></span>|<span data-ttu-id="a0e10-157">SQLService</span><span class="sxs-lookup"><span data-stu-id="a0e10-157">SQLService</span></span>|<span data-ttu-id="a0e10-158">SQL 管理员帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-158">SQL Admin Account</span></span>|  
|<span data-ttu-id="a0e10-159">SQLAccess</span><span class="sxs-lookup"><span data-stu-id="a0e10-159">SQLAccess</span></span>|<span data-ttu-id="a0e10-160">访问</span><span class="sxs-lookup"><span data-stu-id="a0e10-160">Access</span></span>|<span data-ttu-id="a0e10-161">SQLService</span><span class="sxs-lookup"><span data-stu-id="a0e10-161">SQLService</span></span>|<span data-ttu-id="a0e10-162">SQL 访问帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-162">SQL Access Account</span></span>|  
  
 <span data-ttu-id="a0e10-163">将根据公司标准的帐户密码设置。</span><span class="sxs-lookup"><span data-stu-id="a0e10-163">Set account passwords according to company standards.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a0e10-164">运行的计算机上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，修改要使用 SQLService 帐户和凭据的 SQL Server 和 SQLServerAgent 服务的启动参数。</span><span class="sxs-lookup"><span data-stu-id="a0e10-164">On the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], modify the startup parameters for the SQL Server and SQLServerAgent services to use the SQLService account and credentials.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="a0e10-165">用户名字段是示例;您可能需要更改名称，以避免与其他 Active Directory 帐户冲突。</span><span class="sxs-lookup"><span data-stu-id="a0e10-165">The Username fields are samples; you may need to change the names to avoid conflicting with other Active Directory accounts.</span></span>  
  
## <a name="windows-sharepoint-services-account"></a><span data-ttu-id="a0e10-166">Windows SharePoint Services 帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-166">Windows SharePoint Services Account</span></span>  
 <span data-ttu-id="a0e10-167">在安装之前，必须在创建 Windows SharePoint Services 帐户[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a0e10-167">The Windows SharePoint Services accounts must be created prior to installing [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a0e10-168">有关建议和说明[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]帐户：</span><span class="sxs-lookup"><span data-stu-id="a0e10-168">Recommendations and notes on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] account:</span></span>  
  
- <span data-ttu-id="a0e10-169">SharePoint 管理员帐户 (SPAdmin) 用于管理功能、 SharePoint 定时服务和所有[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]访问。</span><span class="sxs-lookup"><span data-stu-id="a0e10-169">Use the SharePoint Admin Account (SPAdmin) for administrative functions, SharePoint Timer Service and all [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] access.</span></span>  
  
- <span data-ttu-id="a0e10-170">SPAdmin 是站点所有者，并且将需要电子邮件别名。</span><span class="sxs-lookup"><span data-stu-id="a0e10-170">SPAdmin is the site owner and will need an e-mail alias.</span></span>  
  
- <span data-ttu-id="a0e10-171">SPAdmin 必须是本地上的本地管理员组的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机 （Windows SharePoint Services 安装程序执行此）。</span><span class="sxs-lookup"><span data-stu-id="a0e10-171">SPAdmin must be a member of the local administrators group on the local [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer (Windows SharePoint Services setup does this).</span></span>  
  
- <span data-ttu-id="a0e10-172">SPAdmin 必须具有安全管理员和数据库创建者角色[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机 （Windows SharePoint Services 安装程序执行此）。</span><span class="sxs-lookup"><span data-stu-id="a0e10-172">SPAdmin must have the security administrator and database creator roles on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer (Windows SharePoint Services setup does this).</span></span>  
  
  <span data-ttu-id="a0e10-173">**Sharepoint 帐户：**</span><span class="sxs-lookup"><span data-stu-id="a0e10-173">**Sharepoint Accounts:**</span></span>  
  
|<span data-ttu-id="a0e10-174">**用户名**</span><span class="sxs-lookup"><span data-stu-id="a0e10-174">**User name**</span></span>|<span data-ttu-id="a0e10-175">**First Name**</span><span class="sxs-lookup"><span data-stu-id="a0e10-175">**First Name**</span></span>|<span data-ttu-id="a0e10-176">**Last Name**</span><span class="sxs-lookup"><span data-stu-id="a0e10-176">**Last Name**</span></span>|<span data-ttu-id="a0e10-177">**全名**</span><span class="sxs-lookup"><span data-stu-id="a0e10-177">**Full Name**</span></span>|  
|-------------------|--------------------|-------------------|-------------------|  
|<span data-ttu-id="a0e10-178">SPAdmin</span><span class="sxs-lookup"><span data-stu-id="a0e10-178">SPAdmin</span></span>|<span data-ttu-id="a0e10-179">管理员</span><span class="sxs-lookup"><span data-stu-id="a0e10-179">Admin</span></span>|<span data-ttu-id="a0e10-180">SPService</span><span class="sxs-lookup"><span data-stu-id="a0e10-180">SPService</span></span>|<span data-ttu-id="a0e10-181">SharePoint 管理员帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-181">SharePoint Admin Account</span></span>|  
  
 <span data-ttu-id="a0e10-182">根据公司标准设置帐户密码，并且能够在配置过程中检索这些密码。</span><span class="sxs-lookup"><span data-stu-id="a0e10-182">Set account passwords according to company standards and be able to retrieve these passwords during the configuration steps.</span></span> <span data-ttu-id="a0e10-183">请参阅**密码**围绕问题本主题的部分生成的密码。</span><span class="sxs-lookup"><span data-stu-id="a0e10-183">Refer to the **Passwords** section of this topic for issues surrounding generated passwords.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0e10-184">此用户名字段是一个示例;您可能需要更改此名称以保护其他 AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e10-184">This Username field is a sample; you may need to change this name to protect other AD accounts.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="a0e10-185">之后运行的计算机上安装 Windows SharePoint Services [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，确认 SharePoint 定时服务的启动参数正在使用 SPAdmin 帐户和凭据。</span><span class="sxs-lookup"><span data-stu-id="a0e10-185">After installing Windows SharePoint Services on the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], confirm that the startup parameters for the SharePoint Timer Service is using the SPAdmin account and credentials.</span></span>  
  
## <a name="biztalk-groups-and-users"></a><span data-ttu-id="a0e10-186">BizTalk 组和用户</span><span class="sxs-lookup"><span data-stu-id="a0e10-186">BizTalk Groups and Users</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a0e10-187">组和用户之前，必须创建运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置向导。</span><span class="sxs-lookup"><span data-stu-id="a0e10-187">Groups and Users must be created prior to running the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Wizard.</span></span> <span data-ttu-id="a0e10-188">在单系统安装中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用本地组和配置期间创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e10-188">In a single-system installation, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses local groups and accounts which are created during configuration.</span></span> <span data-ttu-id="a0e10-189">但是，如果将单独[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署主机或如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]安装两台不同计算机上必须使用域用户和组帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e10-189">However, if separate [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hosts are deployed or if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are installed on two different computers you must use domain user and group accounts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0e10-190">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置向导无法创建域帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e10-190">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Wizard cannot create domain accounts.</span></span>  
  
 <span data-ttu-id="a0e10-191">有关建议和说明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务和用户帐户：</span><span class="sxs-lookup"><span data-stu-id="a0e10-191">Recommendations and notes on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] service and user accounts:</span></span>  
  
- <span data-ttu-id="a0e10-192">有关创建组织单位 (OU) [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a0e10-192">Create an Organizational Unit (OU) for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a0e10-193">所有帐户和组将都属于此 OU。</span><span class="sxs-lookup"><span data-stu-id="a0e10-193">All accounts and groups will belong to this OU.</span></span>  
  
- <span data-ttu-id="a0e10-194">有描述性完整名称;以下列表中的名称应启用要在配置过程中选择适当的组/帐户/用户的安装程序。</span><span class="sxs-lookup"><span data-stu-id="a0e10-194">Be descriptive with full names; the names in the following lists should enable the installer to select the proper groups/accounts/users during configuration.</span></span>  
  
- <span data-ttu-id="a0e10-195">名字和姓氏是可选的;包含仅的一致性。</span><span class="sxs-lookup"><span data-stu-id="a0e10-195">First name and last name are optional; included for consistency only.</span></span>  
  
- <span data-ttu-id="a0e10-196">不同之处**符 BTService**并**BTUser**指的是服务帐户 （自动） 和一般/共享人类用户。</span><span class="sxs-lookup"><span data-stu-id="a0e10-196">The differentiator **BTService** and **BTUser** refers to service accounts (automatons) and generic/shared human users.</span></span>  
  
- <span data-ttu-id="a0e10-197">创建域帐户，并通过 ADSI 脚本为用户和组帐户创建为上游环境对它们进行填充。</span><span class="sxs-lookup"><span data-stu-id="a0e10-197">Create domain accounts and populate them via an ADSI script for user and group account creation for up line environments.</span></span>  
  
  <span data-ttu-id="a0e10-198">**BizTalk 服务帐户**</span><span class="sxs-lookup"><span data-stu-id="a0e10-198">**BizTalk Service Accounts**</span></span>  
  
|<span data-ttu-id="a0e10-199">**用户名**</span><span class="sxs-lookup"><span data-stu-id="a0e10-199">**User name**</span></span>|<span data-ttu-id="a0e10-200">**First Name**</span><span class="sxs-lookup"><span data-stu-id="a0e10-200">**First Name**</span></span>|<span data-ttu-id="a0e10-201">**Last Name**</span><span class="sxs-lookup"><span data-stu-id="a0e10-201">**Last Name**</span></span>|<span data-ttu-id="a0e10-202">**全名**</span><span class="sxs-lookup"><span data-stu-id="a0e10-202">**Full Name**</span></span>|  
|-------------------|--------------------|-------------------|-------------------|  
|<span data-ttu-id="a0e10-203">BTService</span><span class="sxs-lookup"><span data-stu-id="a0e10-203">BTService</span></span>|<span data-ttu-id="a0e10-204">BTS</span><span class="sxs-lookup"><span data-stu-id="a0e10-204">BTS</span></span>|<span data-ttu-id="a0e10-205">BTService</span><span class="sxs-lookup"><span data-stu-id="a0e10-205">BTService</span></span>|<span data-ttu-id="a0e10-206">BizTalk 服务帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-206">BizTalk Service Account</span></span>|  
|<span data-ttu-id="a0e10-207">BTServiceHost</span><span class="sxs-lookup"><span data-stu-id="a0e10-207">BTServiceHost</span></span>|<span data-ttu-id="a0e10-208">主机</span><span class="sxs-lookup"><span data-stu-id="a0e10-208">Host</span></span>|<span data-ttu-id="a0e10-209">BTService</span><span class="sxs-lookup"><span data-stu-id="a0e10-209">BTService</span></span>|<span data-ttu-id="a0e10-210">BizTalk 主机实例帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-210">BizTalk Host Instance Account</span></span>|  
|<span data-ttu-id="a0e10-211">BTServiceHostIso</span><span class="sxs-lookup"><span data-stu-id="a0e10-211">BTServiceHostIso</span></span>|<span data-ttu-id="a0e10-212">HostIso</span><span class="sxs-lookup"><span data-stu-id="a0e10-212">HostIso</span></span>|<span data-ttu-id="a0e10-213">BTService</span><span class="sxs-lookup"><span data-stu-id="a0e10-213">BTService</span></span>|<span data-ttu-id="a0e10-214">BizTalk 独立主机实例帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-214">BizTalk Isolated Host Instance Account</span></span>|  
|<span data-ttu-id="a0e10-215">SSOService</span><span class="sxs-lookup"><span data-stu-id="a0e10-215">SSOService</span></span>|<span data-ttu-id="a0e10-216">SSO</span><span class="sxs-lookup"><span data-stu-id="a0e10-216">SSO</span></span>|<span data-ttu-id="a0e10-217">BTService</span><span class="sxs-lookup"><span data-stu-id="a0e10-217">BTService</span></span>|<span data-ttu-id="a0e10-218">企业单一登录服务</span><span class="sxs-lookup"><span data-stu-id="a0e10-218">Enterprise Single Sign-On Service</span></span>|  
|<span data-ttu-id="a0e10-219">BTServiceREU</span><span class="sxs-lookup"><span data-stu-id="a0e10-219">BTServiceREU</span></span>|<span data-ttu-id="a0e10-220">REU</span><span class="sxs-lookup"><span data-stu-id="a0e10-220">REU</span></span>|<span data-ttu-id="a0e10-221">BTService</span><span class="sxs-lookup"><span data-stu-id="a0e10-221">BTService</span></span>|<span data-ttu-id="a0e10-222">规则引擎更新服务</span><span class="sxs-lookup"><span data-stu-id="a0e10-222">Rule Engine Update Service</span></span>|  
  
 <span data-ttu-id="a0e10-223">设置用户名称，根据公司和环境标准 （例如 devBTService、 alphaBTService）。</span><span class="sxs-lookup"><span data-stu-id="a0e10-223">Set user names according to company and environmental standards (for example, devBTService, alphaBTService).</span></span> <span data-ttu-id="a0e10-224">根据公司标准设置帐户密码，并能够检索它们的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="a0e10-224">Set account passwords according to company standards and be able to retrieve them for the configuration steps.</span></span> <span data-ttu-id="a0e10-225">请参阅**开发的密码注意事项**围绕问题本主题的部分生成的密码。</span><span class="sxs-lookup"><span data-stu-id="a0e10-225">Refer to the **Password Considerations for Development** section of this topic for issues surrounding generated passwords.</span></span>  
  
 <span data-ttu-id="a0e10-226">安装程序会注意到的服务帐户是非常精细，接近一对一的映射到创建的服务都有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a0e10-226">The installer will notice the service accounts are quite granular, with a near one-to-one mapping to the services created by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a0e10-227">这一粒度允许公司 IT 安全人员跟踪或根据需要限制访问。</span><span class="sxs-lookup"><span data-stu-id="a0e10-227">The granularity allows corporate IT security to track or restrict access as needed.</span></span> <span data-ttu-id="a0e10-228">建议使用粒度，但若要确定是否需要在企业环境中的系统设计人员和企业安全人员之前。</span><span class="sxs-lookup"><span data-stu-id="a0e10-228">The granularity is recommended, but it is up to the system designer and enterprise security personnel to determine if it is necessary in the enterprise environment.</span></span>  
  
 <span data-ttu-id="a0e10-229">上一组中的服务帐户旨在仅，用于自动访问不适用于用户交互式登录。</span><span class="sxs-lookup"><span data-stu-id="a0e10-229">The service accounts in the previous group are intended for automaton access only, not for interactive logon by users.</span></span>  
  
#### <a name="to-set-the-appropriate-account-options"></a><span data-ttu-id="a0e10-230">若要设置适当的帐户选项</span><span class="sxs-lookup"><span data-stu-id="a0e10-230">To set the appropriate account options</span></span>  
  
1. <span data-ttu-id="a0e10-231">在中**Active Directory 用户和计算机**控制台，单击以展开域，然后单击以展开**用户**容器。</span><span class="sxs-lookup"><span data-stu-id="a0e10-231">In the **Active Directory Users and Computers** console, click to expand the domain, and then click to expand the **Users** container.</span></span>  
  
2. <span data-ttu-id="a0e10-232">右键单击该帐户，然后选择**属性**以显示**属性**帐户对话框。</span><span class="sxs-lookup"><span data-stu-id="a0e10-232">Right-click the account and then select **Properties** to display the **Properties** dialog box for the account.</span></span>  
  
3. <span data-ttu-id="a0e10-233">单击**帐户**选项卡**属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="a0e10-233">Click the **Account** tab of the **Properties** dialog box.</span></span>  
  
4. <span data-ttu-id="a0e10-234">单击此项可检查以下选项：</span><span class="sxs-lookup"><span data-stu-id="a0e10-234">Click to check the following options:</span></span>  
  
   -   <span data-ttu-id="a0e10-235">**用户不能更改密码**(企业安全人员将成批更改密码)。</span><span class="sxs-lookup"><span data-stu-id="a0e10-235">**User cannot change password** (enterprise security will batch change the passwords).</span></span>  
  
   -   <span data-ttu-id="a0e10-236">**密码永不过期**</span><span class="sxs-lookup"><span data-stu-id="a0e10-236">**Password never expires**</span></span>  
  
5. <span data-ttu-id="a0e10-237">单击**登录到**按钮以显示**登录工作站**对话框。</span><span class="sxs-lookup"><span data-stu-id="a0e10-237">Click the **Log On To** button to display the **Logon Workstations** dialog box.</span></span>  
  
6. <span data-ttu-id="a0e10-238">单击此选项以**以下计算机**，添加每台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a0e10-238">Click the option for **The following computers**, add each computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and then click **OK**.</span></span>  
  
7. <span data-ttu-id="a0e10-239">单击**遥控器**选项卡**属性**对话框的，然后单击以清除选项**启用远程控制**。</span><span class="sxs-lookup"><span data-stu-id="a0e10-239">Click the **Remote Control** tab of the **Properties** dialog box, and then click to clear the option to **Enable remote control**.</span></span>  
  
8. <span data-ttu-id="a0e10-240">单击**终端服务配置文件**选项卡**属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="a0e10-240">Click the **Terminal Services Profile** tab of the **Properties** dialog box.</span></span>  
  
9. <span data-ttu-id="a0e10-241">单击以选中选项**拒绝此用户的权限登录到任何终端服务器上**。</span><span class="sxs-lookup"><span data-stu-id="a0e10-241">Click to check the option to **Deny this user permissions to log on to any Terminal Server**.</span></span>  
  
10. <span data-ttu-id="a0e10-242">单击**确定**以关闭**属性**帐户对话框。</span><span class="sxs-lookup"><span data-stu-id="a0e10-242">Click **OK** to close the **Properties** dialog box for the account.</span></span>  
  
11. <span data-ttu-id="a0e10-243">每个服务帐户重复步骤 3 至 10。</span><span class="sxs-lookup"><span data-stu-id="a0e10-243">Repeat steps 3 through 10 for each service account.</span></span>  
  
    <span data-ttu-id="a0e10-244">**BizTalk 用户帐户**</span><span class="sxs-lookup"><span data-stu-id="a0e10-244">**BizTalk User Accounts**</span></span>  
  
|<span data-ttu-id="a0e10-245">**用户名**</span><span class="sxs-lookup"><span data-stu-id="a0e10-245">**User name**</span></span>|<span data-ttu-id="a0e10-246">**First Name**</span><span class="sxs-lookup"><span data-stu-id="a0e10-246">**First Name**</span></span>|<span data-ttu-id="a0e10-247">**Last Name**</span><span class="sxs-lookup"><span data-stu-id="a0e10-247">**Last Name**</span></span>|<span data-ttu-id="a0e10-248">**全名**</span><span class="sxs-lookup"><span data-stu-id="a0e10-248">**Full Name**</span></span>|  
|-------------------|--------------------|-------------------|-------------------|  
|<span data-ttu-id="a0e10-249">BTUserAdmin</span><span class="sxs-lookup"><span data-stu-id="a0e10-249">BTUserAdmin</span></span>|<span data-ttu-id="a0e10-250">管理员</span><span class="sxs-lookup"><span data-stu-id="a0e10-250">Admin</span></span>|<span data-ttu-id="a0e10-251">BTUser</span><span class="sxs-lookup"><span data-stu-id="a0e10-251">BTUser</span></span>|<span data-ttu-id="a0e10-252">BizTalk 管理用户帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-252">BizTalk Administrative User Account</span></span>|  
|<span data-ttu-id="a0e10-253">BTUserDeploy</span><span class="sxs-lookup"><span data-stu-id="a0e10-253">BTUserDeploy</span></span>|<span data-ttu-id="a0e10-254">部署</span><span class="sxs-lookup"><span data-stu-id="a0e10-254">Deploy</span></span>|<span data-ttu-id="a0e10-255">BTUser</span><span class="sxs-lookup"><span data-stu-id="a0e10-255">BTUser</span></span>|<span data-ttu-id="a0e10-256">BizTalk 部署用户帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-256">BizTalk Deployment User Account</span></span>|  
|<span data-ttu-id="a0e10-257">BTUserHostInstance</span><span class="sxs-lookup"><span data-stu-id="a0e10-257">BTUserHostInstance</span></span>|<span data-ttu-id="a0e10-258">HostInstance</span><span class="sxs-lookup"><span data-stu-id="a0e10-258">HostInstance</span></span>|<span data-ttu-id="a0e10-259">BTUser</span><span class="sxs-lookup"><span data-stu-id="a0e10-259">BTUser</span></span>|<span data-ttu-id="a0e10-260">BizTalk 主机实例帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-260">BizTalk Host Instance Account</span></span>|  
|<span data-ttu-id="a0e10-261">BTUserHostIsolated</span><span class="sxs-lookup"><span data-stu-id="a0e10-261">BTUserHostIsolated</span></span>|<span data-ttu-id="a0e10-262">IsolatedlHost</span><span class="sxs-lookup"><span data-stu-id="a0e10-262">IsolatedlHost</span></span>|<span data-ttu-id="a0e10-263">BTUser</span><span class="sxs-lookup"><span data-stu-id="a0e10-263">BTUser</span></span>|<span data-ttu-id="a0e10-264">BizTalk 独立主机实例帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-264">BizTalk Isolated Host Instance Account</span></span>|  
|<span data-ttu-id="a0e10-265">BTUserInstall</span><span class="sxs-lookup"><span data-stu-id="a0e10-265">BTUserInstall</span></span>|<span data-ttu-id="a0e10-266">安装</span><span class="sxs-lookup"><span data-stu-id="a0e10-266">Install</span></span>|<span data-ttu-id="a0e10-267">BTUser</span><span class="sxs-lookup"><span data-stu-id="a0e10-267">BTUser</span></span>|<span data-ttu-id="a0e10-268">BizTalk 安装用户帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-268">BizTalk Installation User Account</span></span>|  
|<span data-ttu-id="a0e10-269">BTUserSupport</span><span class="sxs-lookup"><span data-stu-id="a0e10-269">BTUserSupport</span></span>|<span data-ttu-id="a0e10-270">支持</span><span class="sxs-lookup"><span data-stu-id="a0e10-270">Support</span></span>|<span data-ttu-id="a0e10-271">BTUser</span><span class="sxs-lookup"><span data-stu-id="a0e10-271">BTUser</span></span>|<span data-ttu-id="a0e10-272">BizTalk 支持访问帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-272">BizTalk Support Access Account</span></span>|  
  
#### <a name="to-set-the-appropriate-account-options-follow-these-steps"></a><span data-ttu-id="a0e10-273">若要设置适当的帐户选项，请执行以下步骤</span><span class="sxs-lookup"><span data-stu-id="a0e10-273">To set the appropriate account options follow these steps</span></span>  
  
1. <span data-ttu-id="a0e10-274">在中**Active Directory 用户和计算机**控制台中，单击以展开域，然后单击以展开**用户**容器。</span><span class="sxs-lookup"><span data-stu-id="a0e10-274">In the **Active Directory Users and Computers** console click to expand the domain, and then click to expand the **Users** container.</span></span>  
  
2. <span data-ttu-id="a0e10-275">右键单击该帐户，然后选择**属性**以显示**属性**帐户对话框。</span><span class="sxs-lookup"><span data-stu-id="a0e10-275">Right-click the account and then select **Properties** to display the **Properties** dialog box for the account.</span></span>  
  
3. <span data-ttu-id="a0e10-276">单击**帐户**选项卡**属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="a0e10-276">Click the **Account** tab of the **Properties** dialog box.</span></span>  
  
4. <span data-ttu-id="a0e10-277">单击此项可检查以下选项：</span><span class="sxs-lookup"><span data-stu-id="a0e10-277">Click to check the following options:</span></span>  
  
   -   <span data-ttu-id="a0e10-278">**用户不能更改密码**(企业安全人员将成批更改密码)。</span><span class="sxs-lookup"><span data-stu-id="a0e10-278">**User cannot change password** (enterprise security will batch change the passwords).</span></span>  
  
   -   <span data-ttu-id="a0e10-279">**密码永不过期**</span><span class="sxs-lookup"><span data-stu-id="a0e10-279">**Password never expires**</span></span>  
  
5. <span data-ttu-id="a0e10-280">单击**登录到**按钮以显示**登录工作站**对话框。</span><span class="sxs-lookup"><span data-stu-id="a0e10-280">Click the **Log On To** button to display the **Logon Workstations** dialog box.</span></span>  
  
6. <span data-ttu-id="a0e10-281">单击此选项以**以下计算机**，添加每台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a0e10-281">Click the option for **The following computers**, add each computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and then click **OK**.</span></span>  
  
7. <span data-ttu-id="a0e10-282">单击**遥控器**选项卡**属性**对话框中，然后单击以选中选项**启用远程控制**。</span><span class="sxs-lookup"><span data-stu-id="a0e10-282">Click the **Remote Control** tab of the **Properties** dialog box, and then click to check the option to **Enable remote control**.</span></span>  
  
8. <span data-ttu-id="a0e10-283">单击**终端服务配置文件**选项卡**属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="a0e10-283">Click the **Terminal Services Profile** tab of the **Properties** dialog box.</span></span>  
  
9. <span data-ttu-id="a0e10-284">单击以清除选项**拒绝此用户的权限登录到任何终端服务器上**。</span><span class="sxs-lookup"><span data-stu-id="a0e10-284">Click to clear the option to **Deny this user permissions to log on to any Terminal Server**.</span></span>  
  
10. <span data-ttu-id="a0e10-285">单击**确定**以关闭**属性**帐户对话框。</span><span class="sxs-lookup"><span data-stu-id="a0e10-285">Click **OK** to close the **Properties** dialog box for the account.</span></span>  
  
11. <span data-ttu-id="a0e10-286">每个用户帐户重复步骤 3 至 10。</span><span class="sxs-lookup"><span data-stu-id="a0e10-286">Repeat steps 3 through 10 for each user account.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a0e10-287">它们提供的角色分配给实际用户时，可禁用任何这些帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e10-287">Any of these accounts can be disabled if the roles they are to provide are assigned to actual users.</span></span> <span data-ttu-id="a0e10-288">在版本 1 和版本 2 的早期阶段，假定这些帐户可在开发、 测试和 beta 版测试环境。</span><span class="sxs-lookup"><span data-stu-id="a0e10-288">In the early stages of release one and release two, it is assumed that these accounts are used in the development, alpha test, and beta test environments.</span></span>  
  
    <span data-ttu-id="a0e10-289">**BizTalk 组帐户**</span><span class="sxs-lookup"><span data-stu-id="a0e10-289">**BizTalk Group Accounts**</span></span>  
  
|<span data-ttu-id="a0e10-290">**组名称**</span><span class="sxs-lookup"><span data-stu-id="a0e10-290">**Group Name**</span></span>|<span data-ttu-id="a0e10-291">**组类型**</span><span class="sxs-lookup"><span data-stu-id="a0e10-291">**Group Type**</span></span>|<span data-ttu-id="a0e10-292">**成员**</span><span class="sxs-lookup"><span data-stu-id="a0e10-292">**Members**</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a0e10-293">BizTalk Application Users</span><span class="sxs-lookup"><span data-stu-id="a0e10-293">BizTalk Application Users</span></span>|<span data-ttu-id="a0e10-294">全局或通用</span><span class="sxs-lookup"><span data-stu-id="a0e10-294">Global or Universal</span></span>|<span data-ttu-id="a0e10-295">-   BTServiceHost</span><span class="sxs-lookup"><span data-stu-id="a0e10-295">-   BTServiceHost</span></span><br /><span data-ttu-id="a0e10-296">-BTUserHostInstance</span><span class="sxs-lookup"><span data-stu-id="a0e10-296">-   BTUserHostInstance</span></span>|  
|<span data-ttu-id="a0e10-297">BizTalk 开发用户</span><span class="sxs-lookup"><span data-stu-id="a0e10-297">BizTalk Development Users</span></span>|<span data-ttu-id="a0e10-298">全局或通用</span><span class="sxs-lookup"><span data-stu-id="a0e10-298">Global or Universal</span></span>|<span data-ttu-id="a0e10-299">（开发用户的本地域帐户）**注意：** 最佳做法是，不要启用上游环境中的 BizTalk 开发用户组。</span><span class="sxs-lookup"><span data-stu-id="a0e10-299">(local domain accounts of development users) **Note:**  As a best practice, do not enable the BizTalk Development Users group in up-line environments.</span></span>|  
|<span data-ttu-id="a0e10-300">BizTalk 部署用户</span><span class="sxs-lookup"><span data-stu-id="a0e10-300">BizTalk Deployment Users</span></span>|<span data-ttu-id="a0e10-301">全局或通用</span><span class="sxs-lookup"><span data-stu-id="a0e10-301">Global or Universal</span></span>|<span data-ttu-id="a0e10-302">（部署用户的本地域帐户）</span><span class="sxs-lookup"><span data-stu-id="a0e10-302">(local domain accounts of deployment users)</span></span>|  
|<span data-ttu-id="a0e10-303">BizTalk 主机用户</span><span class="sxs-lookup"><span data-stu-id="a0e10-303">BizTalk Host Users</span></span>|<span data-ttu-id="a0e10-304">全局或通用</span><span class="sxs-lookup"><span data-stu-id="a0e10-304">Global or Universal</span></span>|<span data-ttu-id="a0e10-305">BTUserHostInstance</span><span class="sxs-lookup"><span data-stu-id="a0e10-305">BTUserHostInstance</span></span>|  
|<span data-ttu-id="a0e10-306">BizTalk Isolated Host Users</span><span class="sxs-lookup"><span data-stu-id="a0e10-306">BizTalk Isolated Host Users</span></span>|<span data-ttu-id="a0e10-307">全局或通用</span><span class="sxs-lookup"><span data-stu-id="a0e10-307">Global or Universal</span></span>|<span data-ttu-id="a0e10-308">-   BTServiceHostIso</span><span class="sxs-lookup"><span data-stu-id="a0e10-308">-   BTServiceHostIso</span></span><br /><span data-ttu-id="a0e10-309">-BTUserHostInstance</span><span class="sxs-lookup"><span data-stu-id="a0e10-309">-   BTUserHostInstance</span></span>|  
|<span data-ttu-id="a0e10-310">BizTalk Server Administrators</span><span class="sxs-lookup"><span data-stu-id="a0e10-310">BizTalk Server Administrators</span></span>|<span data-ttu-id="a0e10-311">全局或通用</span><span class="sxs-lookup"><span data-stu-id="a0e10-311">Global or Universal</span></span>|<span data-ttu-id="a0e10-312">-BTUserAdmin</span><span class="sxs-lookup"><span data-stu-id="a0e10-312">-   BTUserAdmin</span></span><br /><span data-ttu-id="a0e10-313">-BTUserInstall</span><span class="sxs-lookup"><span data-stu-id="a0e10-313">-   BTUserInstall</span></span><br /><span data-ttu-id="a0e10-314">BizTalk 开发用户</span><span class="sxs-lookup"><span data-stu-id="a0e10-314">-   BizTalk Development Users</span></span><br /><span data-ttu-id="a0e10-315">BizTalk 部署用户</span><span class="sxs-lookup"><span data-stu-id="a0e10-315">-   BizTalk Deployment Users</span></span>|  
|<span data-ttu-id="a0e10-316">BizTalk 支持用户</span><span class="sxs-lookup"><span data-stu-id="a0e10-316">BizTalk Support Users</span></span>|<span data-ttu-id="a0e10-317">全局或通用</span><span class="sxs-lookup"><span data-stu-id="a0e10-317">Global or Universal</span></span>|<span data-ttu-id="a0e10-318">BTUserSupport （支持用户的本地域帐户）</span><span class="sxs-lookup"><span data-stu-id="a0e10-318">BTUserSupport (local domain accounts of support users)</span></span>|  
|<span data-ttu-id="a0e10-319">SSO Administrators</span><span class="sxs-lookup"><span data-stu-id="a0e10-319">SSO Administrators</span></span>|<span data-ttu-id="a0e10-320">全局或通用</span><span class="sxs-lookup"><span data-stu-id="a0e10-320">Global or Universal</span></span>|<span data-ttu-id="a0e10-321">-   SSOService</span><span class="sxs-lookup"><span data-stu-id="a0e10-321">-   SSOService</span></span><br /><span data-ttu-id="a0e10-322">-BTUserInstall</span><span class="sxs-lookup"><span data-stu-id="a0e10-322">-   BTUserInstall</span></span><br /><span data-ttu-id="a0e10-323">本地管理员</span><span class="sxs-lookup"><span data-stu-id="a0e10-323">-   Local Administrator</span></span>|  
|<span data-ttu-id="a0e10-324">SSO 关联管理员</span><span class="sxs-lookup"><span data-stu-id="a0e10-324">SSO Affiliate Administrators</span></span>|<span data-ttu-id="a0e10-325">全局或通用</span><span class="sxs-lookup"><span data-stu-id="a0e10-325">Global or Universal</span></span>|<span data-ttu-id="a0e10-326">BizTalk 开发用户</span><span class="sxs-lookup"><span data-stu-id="a0e10-326">-   BizTalk Development Users</span></span><br /><span data-ttu-id="a0e10-327">BizTalk 部署用户</span><span class="sxs-lookup"><span data-stu-id="a0e10-327">-   BizTalk Deployment Users</span></span><br /><span data-ttu-id="a0e10-328">-   BTServiceHostIso</span><span class="sxs-lookup"><span data-stu-id="a0e10-328">-   BTServiceHostIso</span></span><br /><span data-ttu-id="a0e10-329">-   \<控制台用户\></span><span class="sxs-lookup"><span data-stu-id="a0e10-329">-   \<console user\></span></span>|  
|<span data-ttu-id="a0e10-330">Windows SharePoint Services 管理员</span><span class="sxs-lookup"><span data-stu-id="a0e10-330">Windows SharePoint Services Administrators</span></span>|<span data-ttu-id="a0e10-331">全局或通用</span><span class="sxs-lookup"><span data-stu-id="a0e10-331">Global or Universal</span></span>|<span data-ttu-id="a0e10-332">-   SPAdmin</span><span class="sxs-lookup"><span data-stu-id="a0e10-332">-   SPAdmin</span></span><br /><span data-ttu-id="a0e10-333">-BTUserInstall</span><span class="sxs-lookup"><span data-stu-id="a0e10-333">-   BTUserInstall</span></span><br /><span data-ttu-id="a0e10-334">-   BTUserDeploy</span><span class="sxs-lookup"><span data-stu-id="a0e10-334">-   BTUserDeploy</span></span><br /><span data-ttu-id="a0e10-335">BizTalk 开发用户</span><span class="sxs-lookup"><span data-stu-id="a0e10-335">-   BizTalk Development Users</span></span><br /><span data-ttu-id="a0e10-336">BizTalk 部署用户</span><span class="sxs-lookup"><span data-stu-id="a0e10-336">-   BizTalk Deployment users</span></span>|  
  
 <span data-ttu-id="a0e10-337">建议和域组的说明：</span><span class="sxs-lookup"><span data-stu-id="a0e10-337">Recommendations and notes on domain groups:</span></span>  
  
- <span data-ttu-id="a0e10-338">创建组并添加成员在安装之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a0e10-338">Create the groups and add members prior to installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="a0e10-339">域组可以是全局或通用组。</span><span class="sxs-lookup"><span data-stu-id="a0e10-339">Domain groups can be Global or Universal groups.</span></span>  
  
- <span data-ttu-id="a0e10-340">使用 *\<DomainName\>\\< 用户名\>* 时配置向导中指定的域帐户信息。</span><span class="sxs-lookup"><span data-stu-id="a0e10-340">Use *\<DomainName\>\\<UserName\>* when specifying domain account information in the Configuration Wizard.</span></span>  
  
- <span data-ttu-id="a0e10-341">组和用户/服务帐户必须与在其中的域属于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机所属 （配置向导检查此并且不会显示帐户或组包含来自其他域帐户）。</span><span class="sxs-lookup"><span data-stu-id="a0e10-341">Groups and user/service accounts must belong to the domain in which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer belongs (the Configuration Wizard checks this and will not display accounts or groups containing accounts from other domains).</span></span>  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a0e10-342">对于所有聚类分析方案要求使用域帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e10-342">requires domain accounts for all clustering scenarios.</span></span>  
  
- <span data-ttu-id="a0e10-343">安装时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，控制台用户必须是以下组的成员：</span><span class="sxs-lookup"><span data-stu-id="a0e10-343">When installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the console user needs to be a member of the following groups:</span></span>  
  
  - <span data-ttu-id="a0e10-344">BizTalk Server Administrators</span><span class="sxs-lookup"><span data-stu-id="a0e10-344">BizTalk Server Administrators</span></span>  
  
  - <span data-ttu-id="a0e10-345">SSO Administrators （仅当配置主密钥服务器）</span><span class="sxs-lookup"><span data-stu-id="a0e10-345">SSO Administrators (only when configuring the master secret server)</span></span>  
  
  - <span data-ttu-id="a0e10-346">Windows 管理员</span><span class="sxs-lookup"><span data-stu-id="a0e10-346">Windows administrator</span></span>  
  
  - [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] <span data-ttu-id="a0e10-347">管理员</span><span class="sxs-lookup"><span data-stu-id="a0e10-347">administrator</span></span>  
  
  - <span data-ttu-id="a0e10-348">OLAP 管理员</span><span class="sxs-lookup"><span data-stu-id="a0e10-348">OLAP administrator</span></span>  
  
    <span data-ttu-id="a0e10-349">BTUserInstall 帐户应该用于安装和配置和完成配置后应禁用。</span><span class="sxs-lookup"><span data-stu-id="a0e10-349">The BTUserInstall account should be used for installation and configuration and should be disabled after configuration is complete.</span></span>  
  
- <span data-ttu-id="a0e10-350">若要允许消息事件和服务实例跟踪将业务流程附加到调试器，开发人员需要属于 BizTalk Server Administrators 组中，如上面的部分中所述**BizTalk 开发帐户**.</span><span class="sxs-lookup"><span data-stu-id="a0e10-350">To allow message event and service instance tracking to attach orchestrations to the debugger, the developer needs to belong to the BizTalk Server Administrators group, as outlined above in the section **BizTalk Development Accounts**.</span></span>  
  
## <a name="local-administrator-accounts"></a><span data-ttu-id="a0e10-351">本地管理员帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-351">Local Administrator Accounts</span></span>  
 <span data-ttu-id="a0e10-352">确认或到本地管理员组中添加以下帐户和组，在[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机：</span><span class="sxs-lookup"><span data-stu-id="a0e10-352">Confirm or add the following accounts and groups to the Local Administrators group on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer:</span></span>  
  
- <span data-ttu-id="a0e10-353">Domain\BTUserInstall （配置完成后禁用）</span><span class="sxs-lookup"><span data-stu-id="a0e10-353">Domain\BTUserInstall (disable when configuration is complete)</span></span>  
  
- <span data-ttu-id="a0e10-354">Domain\BTUserDeploy （在生产部署完成后禁用）</span><span class="sxs-lookup"><span data-stu-id="a0e10-354">Domain\BTUserDeploy (disable in production when deployment is complete)</span></span>  
  
- <span data-ttu-id="a0e10-355">Domain\SPAdmin</span><span class="sxs-lookup"><span data-stu-id="a0e10-355">Domain\SPAdmin</span></span>  
  
- <span data-ttu-id="a0e10-356">Domain\SQLAdmin</span><span class="sxs-lookup"><span data-stu-id="a0e10-356">Domain\SQLAdmin</span></span>  
  
- <span data-ttu-id="a0e10-357">Domain\SQLService</span><span class="sxs-lookup"><span data-stu-id="a0e10-357">Domain\SQLService</span></span>  
  
- <span data-ttu-id="a0e10-358">域 \biztalk 开发用户 （在上游环境）</span><span class="sxs-lookup"><span data-stu-id="a0e10-358">Domain\BizTalk Development Users (omit in up line environments)</span></span>  
  
- <span data-ttu-id="a0e10-359">域 \biztalk 部署用户 （在开发环境中省略）</span><span class="sxs-lookup"><span data-stu-id="a0e10-359">Domain\BizTalk Deployment Users (omit in development environments)</span></span>  
  
  <span data-ttu-id="a0e10-360">确认或到本地管理员组中添加以下帐户和组，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机：</span><span class="sxs-lookup"><span data-stu-id="a0e10-360">Confirm or add the following accounts and groups to the Local Administrators group on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer:</span></span>  
  
- <span data-ttu-id="a0e10-361">Domain\BTUserInstall （配置完成后禁用）</span><span class="sxs-lookup"><span data-stu-id="a0e10-361">Domain\BTUserInstall (disable when configuration is complete)</span></span>  
  
- <span data-ttu-id="a0e10-362">Domain\BTUserDeploy （在生产部署完成后禁用）</span><span class="sxs-lookup"><span data-stu-id="a0e10-362">Domain\BTUserDeploy (disable in production when deployment is complete)</span></span>  
  
- <span data-ttu-id="a0e10-363">Domain\BTUserSupport</span><span class="sxs-lookup"><span data-stu-id="a0e10-363">Domain\BTUserSupport</span></span>  
  
- <span data-ttu-id="a0e10-364">Domain\SPAdmin</span><span class="sxs-lookup"><span data-stu-id="a0e10-364">Domain\SPAdmin</span></span>  
  
- <span data-ttu-id="a0e10-365">域 \biztalk 开发用户 （在上游环境中）</span><span class="sxs-lookup"><span data-stu-id="a0e10-365">Domain\BizTalk Development Users (omit in upline environments)</span></span>  
  
- <span data-ttu-id="a0e10-366">域 \biztalk 部署用户 （在开发环境中省略）</span><span class="sxs-lookup"><span data-stu-id="a0e10-366">Domain\BizTalk Deployment Users (omit in development environments)</span></span>  
  
## <a name="sql-server-administrator-accounts"></a><span data-ttu-id="a0e10-367">SQL Server 管理员帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-367">SQL Server Administrator Accounts</span></span>  
 <span data-ttu-id="a0e10-368">安装程序接受用户和组从安装程序，并将分配 SQL 角色的输入：</span><span class="sxs-lookup"><span data-stu-id="a0e10-368">Setup programs accept input from the installer and assigns SQL roles to users and groups:</span></span>  
  
- <span data-ttu-id="a0e10-369">期间[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]安装程序，SPAdmin 帐户安全管理员和数据库创建者权限授予在[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="a0e10-369">During [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] setup, the SPAdmin account is granted Security Administrator and Database Creator rights on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span> <span data-ttu-id="a0e10-370">如果 SPAdmin 帐户是本地管理员组的成员可以删除这些权限。</span><span class="sxs-lookup"><span data-stu-id="a0e10-370">These rights can be removed if the SPAdmin account is a member of the Local Administrators group.</span></span>  
  
## <a name="e-mail-account"></a><span data-ttu-id="a0e10-371">电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="a0e10-371">E-Mail Account</span></span>  
 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] <span data-ttu-id="a0e10-372">将基于发送电子邮件某些系统事件。</span><span class="sxs-lookup"><span data-stu-id="a0e10-372">will send mail based on certain system events.</span></span> <span data-ttu-id="a0e10-373">安装程序将在配置过程中提示电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a0e10-373">Setup prompts for an e-mail address during the configuration process.</span></span> <span data-ttu-id="a0e10-374">实现此目的创建电子邮件别名，并且在安装和单元测试期间监控此别名。</span><span class="sxs-lookup"><span data-stu-id="a0e10-374">Create e-mail aliases for this purpose and monitor the alias during setup and unit testing.</span></span> <span data-ttu-id="a0e10-375">在生产环境中，此帐户应是可由监控系统的系统管理员访问。</span><span class="sxs-lookup"><span data-stu-id="a0e10-375">In the production environment, this account should be accessible by a system administrator who is monitoring the system.</span></span>  
  
 <span data-ttu-id="a0e10-376">使用的电子邮件帐户[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]是**WSS 管理员电子邮件**帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e10-376">The e-mail account used by [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] is the **WSS Administrator E-mail** account.</span></span>  
  
## <a name="password-considerations-for-development"></a><span data-ttu-id="a0e10-377">有关开发的密码注意事项</span><span class="sxs-lookup"><span data-stu-id="a0e10-377">Password Considerations for Development</span></span>  
 <span data-ttu-id="a0e10-378">对于开发和测试环境中，帐户密码可以按标准设置，并可分发。</span><span class="sxs-lookup"><span data-stu-id="a0e10-378">For development and test environments, account passwords can be set by a standard and be distributable.</span></span> <span data-ttu-id="a0e10-379">安装程序的标准各异;本主题使用首字母大写，缩写加上 （服务或用户） 的帐户其余小写缩写词后跟的服务组件的模板。</span><span class="sxs-lookup"><span data-stu-id="a0e10-379">Installer standards vary; this topic uses the template of initial capital letters abbreviating the service component followed by a lower-case abbreviation for the rest of the account (service or user).</span></span> <span data-ttu-id="a0e10-380">对于服务帐户，本主题使用 Serv; 本主题使用用户的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e10-380">For service accounts, this topic uses 'Serv', for user accounts this topic uses 'User'.</span></span>  
  
 <span data-ttu-id="a0e10-381">例如：</span><span class="sxs-lookup"><span data-stu-id="a0e10-381">For example:</span></span>  
  
- <span data-ttu-id="a0e10-382">Windows SharePoint Services (SharePoint) 服务和管理员帐户 (SPAdmin) 密码：SPServ。</span><span class="sxs-lookup"><span data-stu-id="a0e10-382">Windows SharePoint Services (SharePoint) Service and admin account (SPAdmin) passwords: 'SPServ'.</span></span>  
  
- <span data-ttu-id="a0e10-383">BizTalk 服务帐户密码：BTServ。</span><span class="sxs-lookup"><span data-stu-id="a0e10-383">BizTalk Service account passwords: 'BTServ'.</span></span>  
  
- <span data-ttu-id="a0e10-384">BizTalk 用户帐户密码：BTUser。</span><span class="sxs-lookup"><span data-stu-id="a0e10-384">BizTalk User account passwords: 'BTUser'.</span></span>  
  
  <span data-ttu-id="a0e10-385">某些 IT 环境要求密码包含非 alpha 和/或数字字符。</span><span class="sxs-lookup"><span data-stu-id="a0e10-385">Some IT environments require passwords to contain non-alpha and/or numeric characters.</span></span> <span data-ttu-id="a0e10-386">在此方案中，你可以替换美元符号 （$） 的"s"，并将 at 符号 (@) 为"a"。</span><span class="sxs-lookup"><span data-stu-id="a0e10-386">In this scenario you could substitute a dollar sign ($) for "s", and an 'at' sign (@) for "a".</span></span> <span data-ttu-id="a0e10-387">符号是示例;开发一种模式，最适合您的共享具有半公共密码的帐户。</span><span class="sxs-lookup"><span data-stu-id="a0e10-387">The symbols are samples; develop a pattern that works best for you for shared accounts with semi-public passwords.</span></span>  
  
  <span data-ttu-id="a0e10-388">在开发环境中使用的示例可再发行组件密码是：</span><span class="sxs-lookup"><span data-stu-id="a0e10-388">Sample redistributable passwords in use in the development environment are:</span></span>  
  
- <span data-ttu-id="a0e10-389">BT$erv99           BizTalk Service Accounts</span><span class="sxs-lookup"><span data-stu-id="a0e10-389">BT$erv99           BizTalk Service Accounts</span></span>  
  
- <span data-ttu-id="a0e10-390">BTU$er99          BizTalk User Accounts</span><span class="sxs-lookup"><span data-stu-id="a0e10-390">BTU$er99          BizTalk User Accounts</span></span>  
  
- <span data-ttu-id="a0e10-391">SP 美元 erv99 WSS 服务帐户 (SPAdmin)</span><span class="sxs-lookup"><span data-stu-id="a0e10-391">SP$erv99           WSS Service Account (SPAdmin)</span></span>  
  
- <span data-ttu-id="a0e10-392">SQL$erv99         SQL Service/Access/Admin Account</span><span class="sxs-lookup"><span data-stu-id="a0e10-392">SQL$erv99         SQL Service/Access/Admin Account</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0e10-393">这些建议适用于开发和仅限共享的环境并不会建议或不鼓励用于公司密码策略。</span><span class="sxs-lookup"><span data-stu-id="a0e10-393">These recommendations are for development and shared environments only and do not recommend or discourage the use of corporate password policies.</span></span> <span data-ttu-id="a0e10-394">请参阅有关密码要求网络管理员联系。</span><span class="sxs-lookup"><span data-stu-id="a0e10-394">See your network administrator for password requirements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0e10-395">如果公司密码策略包括生成的密码，需要注意某些符号和符号组合是特殊用途的 XML 字符。</span><span class="sxs-lookup"><span data-stu-id="a0e10-395">If corporate password policy includes generated passwords, be advised that some symbols and symbol combinations are special-use characters to XML.</span></span> <span data-ttu-id="a0e10-396">不恰当地使用这些字符将导致配置 XML 文件，在配置过程中无法打开。</span><span class="sxs-lookup"><span data-stu-id="a0e10-396">Inappropriate use of these characters will prevent configuration XML files from being opened during the configuration process.</span></span> <span data-ttu-id="a0e10-397">这些符号包括"&"、"\<"，"\>"、 和双单引号，并且可能包括其他人。</span><span class="sxs-lookup"><span data-stu-id="a0e10-397">These symbols include "&", "\<", "\>", single- and double-quote, and may include others.</span></span> <span data-ttu-id="a0e10-398">测试之前执行基于文件的配置的配置 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="a0e10-398">Test the configuration XML file prior to executing file-based configuration.</span></span> <span data-ttu-id="a0e10-399">你可以测试此可靠地保证正确的 XML 格式，通过在 Internet Explorer （或 XML 编辑器） 中打开该文档与其中嵌入了生成的密码。</span><span class="sxs-lookup"><span data-stu-id="a0e10-399">You can test this reliably for proper XML formatting by opening the document in Internet Explorer (or an XML editor) with the generated passwords embedded therein.</span></span>  
  
 <span data-ttu-id="a0e10-400">有关部署上游环境中保证密码安全的详细信息 (包括要测试的方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置文件)，请参阅[BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)。</span><span class="sxs-lookup"><span data-stu-id="a0e10-400">For more information about deployment of secure passwords in up-line environments (including the method to test a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration file), see [Configuration Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0e10-401">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0e10-401">See Also</span></span>  
 [<span data-ttu-id="a0e10-402">故障排除的 BizTalk Server 权限</span><span class="sxs-lookup"><span data-stu-id="a0e10-402">Troubleshooting BizTalk Server Permissions</span></span>](../core/troubleshooting-biztalk-server-permissions.md)