---
title: "部署过程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, deploying
- deploying, SSO
- LogonExternalUser test [SSO]
- security, SSO
- SSO, LogonExternalUser test
- SSO, security
ms.assetid: 7dd4c022-c70b-467a-bf94-dc4ac6029f81
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21be32ec58c90c1fb95134a002bee82ef5d78fa5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-process"></a><span data-ttu-id="66f1d-102">部署过程</span><span class="sxs-lookup"><span data-stu-id="66f1d-102">Deployment Process</span></span>
<span data-ttu-id="66f1d-103">以下步骤对企业单一登录的安全部署进行了高级概述。</span><span class="sxs-lookup"><span data-stu-id="66f1d-103">The following steps give a high-level overview of secure deployment of Enterprise Single Sign-On.</span></span> <span data-ttu-id="66f1d-104">有关在 SQL Server 中执行操作的详细过程，请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="66f1d-104">For detailed procedures on the actions to take in SQL Server, see your SQL Server documentation.</span></span>  
  
1.  <span data-ttu-id="66f1d-105">在 SQL Server 域控制器上，使用新建信任向导可创建具有以下属性的信任：</span><span class="sxs-lookup"><span data-stu-id="66f1d-105">On the SQL Server domain controller, use the New Trust Wizard to create a trust with the following properties:</span></span>  
  
    -   <span data-ttu-id="66f1d-106">**名称：** ORCH.com</span><span class="sxs-lookup"><span data-stu-id="66f1d-106">**Name:** ORCH.com</span></span>  
  
    -   <span data-ttu-id="66f1d-107">**方向：**双向</span><span class="sxs-lookup"><span data-stu-id="66f1d-107">**Direction:** Two-way</span></span>  
  
    -   <span data-ttu-id="66f1d-108">**边：**仅限于此域</span><span class="sxs-lookup"><span data-stu-id="66f1d-108">**Sides:** This domain only</span></span>  
  
    -   <span data-ttu-id="66f1d-109">**传出信任身份验证级别的本地域：**选择性身份验证</span><span class="sxs-lookup"><span data-stu-id="66f1d-109">**Outgoing Trust Authentication Level - Local Domain:** Selective authentication</span></span>  
  
    -   <span data-ttu-id="66f1d-110">**密码：**选择一个密码</span><span class="sxs-lookup"><span data-stu-id="66f1d-110">**Password:** Choose a password</span></span>  
  
    -   <span data-ttu-id="66f1d-111">**确认传出信任：**是</span><span class="sxs-lookup"><span data-stu-id="66f1d-111">**Confirm Outgoing Trust:** Yes</span></span>  
  
    -   <span data-ttu-id="66f1d-112">**确认传入信任：**否</span><span class="sxs-lookup"><span data-stu-id="66f1d-112">**Confirm Incoming Trust:** No</span></span>  
  
2.  <span data-ttu-id="66f1d-113">在 ORCH.com 域控制器上，使用新建信任向导可创建具有以下属性的信任：</span><span class="sxs-lookup"><span data-stu-id="66f1d-113">On the ORCH.com domain controller, use the New Trust Wizard to create a trust with the following properties:</span></span>  
  
    -   <span data-ttu-id="66f1d-114">**名称：** SQL.com</span><span class="sxs-lookup"><span data-stu-id="66f1d-114">**Name:** SQL.com</span></span>  
  
    -   <span data-ttu-id="66f1d-115">**方向：**双向</span><span class="sxs-lookup"><span data-stu-id="66f1d-115">**Direction:** Two-way</span></span>  
  
    -   <span data-ttu-id="66f1d-116">**边：**仅限于此域</span><span class="sxs-lookup"><span data-stu-id="66f1d-116">**Sides:** This domain only</span></span>  
  
    -   <span data-ttu-id="66f1d-117">**传出信任身份验证级别的本地域：**选择性身份验证</span><span class="sxs-lookup"><span data-stu-id="66f1d-117">**Outgoing Trust Authentication Level - Local Domain:** Selective authentication</span></span>  
  
    -   <span data-ttu-id="66f1d-118">**密码：**必须是与密码相同的 ORCH.com</span><span class="sxs-lookup"><span data-stu-id="66f1d-118">**Password:** Must be the same as password for ORCH.com</span></span>  
  
    -   <span data-ttu-id="66f1d-119">**确认传出信任：**是</span><span class="sxs-lookup"><span data-stu-id="66f1d-119">**Confirm Outgoing Trust:** Yes</span></span>  
  
    -   <span data-ttu-id="66f1d-120">**确认传入信任：**否</span><span class="sxs-lookup"><span data-stu-id="66f1d-120">**Confirm Incoming Trust:** No</span></span>  
  
3.  <span data-ttu-id="66f1d-121">在 ORCH.com 域控制器上，为从 SQL.COM 的传入通信设置域范围信任。</span><span class="sxs-lookup"><span data-stu-id="66f1d-121">On the ORCH.com domain controller, set the domain wide trust for Incoming from SQL.COM.</span></span>  
  
4.  <span data-ttu-id="66f1d-122">在 SQL.com 域控制器上，为从 ORCH.COM 的传出通信设置域范围信任。</span><span class="sxs-lookup"><span data-stu-id="66f1d-122">On the SQL.com domain controller, set the domain wide trust for Outgoing from ORCH.COM.</span></span>  
  
5.  <span data-ttu-id="66f1d-123">在 ORCH.com 域控制器上，将域功能级别提升到 Windows Server 2008 SP2 或 Windows Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="66f1d-123">On the ORCH.com domain controller, raise the domain functional level to Windows Server 2008 SP2 or Windows Server 2008 R2.</span></span>  
  
6.  <span data-ttu-id="66f1d-124">在 ORCH 域中，创建以下新用户：</span><span class="sxs-lookup"><span data-stu-id="66f1d-124">In the ORCH domain, create the following new users:</span></span>  
  
    -   <span data-ttu-id="66f1d-125">ORCH\SSOSvcUser</span><span class="sxs-lookup"><span data-stu-id="66f1d-125">ORCH\SSOSvcUser</span></span>  
  
    -   <span data-ttu-id="66f1d-126">ORCH\TestAppUser</span><span class="sxs-lookup"><span data-stu-id="66f1d-126">ORCH\TestAppUser</span></span>  
  
    -   <span data-ttu-id="66f1d-127">ORCH\AffAppUser</span><span class="sxs-lookup"><span data-stu-id="66f1d-127">ORCH\AffAppUser</span></span>  
  
7.  <span data-ttu-id="66f1d-128">添加**充当操作系统的一部分**SSOSvcUser 和 TestAppUser。</span><span class="sxs-lookup"><span data-stu-id="66f1d-128">Add **Act as part of the operating system** to SSOSvcUser and TestAppUser.</span></span>  
  
8.  <span data-ttu-id="66f1d-129">添加**以进行身份验证允许**ORCH\TestAdmin 特权。</span><span class="sxs-lookup"><span data-stu-id="66f1d-129">Add **Allowed to Authenticate** privilege to ORCH\TestAdmin.</span></span>  
  
9. <span data-ttu-id="66f1d-130">将 ORCH\SSOSvcUser 添加到 SQL 域的 SQL2 中。</span><span class="sxs-lookup"><span data-stu-id="66f1d-130">Add ORCH\SSOSvcUser to SQL2 in the SQL domain.</span></span> <span data-ttu-id="66f1d-131">（此步骤需要使用 Active Directory MMC 中的高级视图。）</span><span class="sxs-lookup"><span data-stu-id="66f1d-131">(This step requires using Advanced View in Active Directory MMC.)</span></span>  
  
10. <span data-ttu-id="66f1d-132">在 SQL2 计算机上，创建以下两个新登录名：</span><span class="sxs-lookup"><span data-stu-id="66f1d-132">On the SQL2 computer, create the following two new logins:</span></span>  
  
    -   <span data-ttu-id="66f1d-133">ORCH\TestAdmin</span><span class="sxs-lookup"><span data-stu-id="66f1d-133">ORCH\TestAdmin</span></span>  
  
    -   <span data-ttu-id="66f1d-134">ORCH\SSOSvcUser</span><span class="sxs-lookup"><span data-stu-id="66f1d-134">ORCH\SSOSvcUser</span></span>  
  
11. <span data-ttu-id="66f1d-135">在 SQL2 域上，创建两个域全局组：</span><span class="sxs-lookup"><span data-stu-id="66f1d-135">On the SQL2 domain, create two domain global groups:</span></span>  
  
    -   <span data-ttu-id="66f1d-136">ORCH\SSOAdminGroup</span><span class="sxs-lookup"><span data-stu-id="66f1d-136">ORCH\SSOAdminGroup</span></span>  
  
    -   <span data-ttu-id="66f1d-137">ORCH\SSOAffAdminGroup</span><span class="sxs-lookup"><span data-stu-id="66f1d-137">ORCH\SSOAffAdminGroup</span></span>  
  
12. <span data-ttu-id="66f1d-138">添加**以进行身份验证允许**ORCH\SSOAdminGroup 组特权。</span><span class="sxs-lookup"><span data-stu-id="66f1d-138">Add **Allowed to Authenticate** privilege to the ORCH\SSOAdminGroup group.</span></span>  
  
13. <span data-ttu-id="66f1d-139">在 SQL2 数据库上，创建以下新登录名：</span><span class="sxs-lookup"><span data-stu-id="66f1d-139">On the SQL2 database, create the following new login:</span></span>  
  
    -   <span data-ttu-id="66f1d-140">ORCH\SSOAdminGroup</span><span class="sxs-lookup"><span data-stu-id="66f1d-140">ORCH\SSOAdminGroup</span></span>  
  
14. <span data-ttu-id="66f1d-141">按照以下步骤安装主密钥服务器：</span><span class="sxs-lookup"><span data-stu-id="66f1d-141">Install the Master Secret Server as follows:</span></span>  
  
    -   <span data-ttu-id="66f1d-142">使用 ORCH\TestAdmin 登录到 NTS5。</span><span class="sxs-lookup"><span data-stu-id="66f1d-142">Log on to NTS5 using ORCH\TestAdmin.</span></span>  
  
    -   <span data-ttu-id="66f1d-143">将 SQL2 用作主密钥服务器以安装 ESSO。</span><span class="sxs-lookup"><span data-stu-id="66f1d-143">Install ESSO, using SQL2 as the Master Secret Server.</span></span>  
  
15. <span data-ttu-id="66f1d-144">使用 ORCH\TestAdmin 登录到 HIS1，然后安装企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="66f1d-144">Log onto HIS1 using ORCH\TestAdmin, and install Enterprise Single Sign-On.</span></span> <span data-ttu-id="66f1d-145">使用数据库服务器名称 SQL2 来将 ESSO 配置为 SSO 联接 HIS2。</span><span class="sxs-lookup"><span data-stu-id="66f1d-145">Configure ESSO as SSO join HIS2, using database server name SQL2.</span></span>  
  
16. <span data-ttu-id="66f1d-146">使用 ORCH\TestAdmin 在 HIS3 上安装企业单一登录管理实用工具。</span><span class="sxs-lookup"><span data-stu-id="66f1d-146">Install the Enterprise Single Sign-On Admin utility on HIS3 using ORCH\TestAdmin.</span></span>  
  
17. <span data-ttu-id="66f1d-147">将以下用户添加到以下组中：</span><span class="sxs-lookup"><span data-stu-id="66f1d-147">Add the following users to the following groups:</span></span>  
  
    -   <span data-ttu-id="66f1d-148">将 ORCH\TestAppUser 添加到 ORCH\SSOAdminGroup 中</span><span class="sxs-lookup"><span data-stu-id="66f1d-148">Add ORCH\TestAppUser to ORCH\SSOAdminGroup</span></span>  
  
    -   <span data-ttu-id="66f1d-149">将 ORCH\AffAppUser 添加到 ORCH\TestAffUserGroup 中</span><span class="sxs-lookup"><span data-stu-id="66f1d-149">Add ORCH\AffAppUser to ORCH\TestAffUserGroup</span></span>  
  
18. <span data-ttu-id="66f1d-150">在 HIS3 上安装 SQL Server Enterprise Edition，并添加登录名 ORCH\AffAppUser。</span><span class="sxs-lookup"><span data-stu-id="66f1d-150">Install SQL Server Enterprise Edition on HIS3, and add login ORCH\AffAppUser.</span></span>  
  
19. <span data-ttu-id="66f1d-151">在 HIS1 计算机上，打开命令提示符，使用以下命令设置约束委托和协议转换：</span><span class="sxs-lookup"><span data-stu-id="66f1d-151">On the HIS1 computer, open a command prompt and use the following commands to set constrain delegation and protocol transition:</span></span>  
  
    -   <span data-ttu-id="66f1d-152">**setspn-A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\SSOSvcUser**</span><span class="sxs-lookup"><span data-stu-id="66f1d-152">**setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\SSOSvcUser**</span></span>  
  
    -   <span data-ttu-id="66f1d-153">**setspn-A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\TestAppUser**</span><span class="sxs-lookup"><span data-stu-id="66f1d-153">**setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\TestAppUser**</span></span>  
  
20. <span data-ttu-id="66f1d-154">上**ORCH\SSOSvcUser**和**ORCH\TestAppUser**属性页中，通过选择以下选项来设置这两个用户帐户的正确委派：</span><span class="sxs-lookup"><span data-stu-id="66f1d-154">On the **ORCH\SSOSvcUser** and **ORCH\TestAppUser** property pages, set the proper delegation for both user accounts by selecting the following options:</span></span>  
  
    -   <span data-ttu-id="66f1d-155">**信任仅委派到指定服务的用户**</span><span class="sxs-lookup"><span data-stu-id="66f1d-155">**Trust this user for delegation to specified services only**</span></span>  
  
    -   <span data-ttu-id="66f1d-156">**使用任何身份验证协议**</span><span class="sxs-lookup"><span data-stu-id="66f1d-156">**Use any authentication protocol**</span></span>  
  
21. <span data-ttu-id="66f1d-157">在 HIS1 计算机上使用 ORCH\TestAdmin，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="66f1d-157">Using ORCH\TestAdmin on the HIS1 computer, perform the following:</span></span>  
  
    -   <span data-ttu-id="66f1d-158">将 ORCH\TestAppUser 添加到远程桌面用户组中</span><span class="sxs-lookup"><span data-stu-id="66f1d-158">Add ORCH\TestAppUser to Remote Desktop User Group</span></span>  
  
    -   <span data-ttu-id="66f1d-159">授予**模拟身份验证后**ORCH\SSOSvcUser 特权</span><span class="sxs-lookup"><span data-stu-id="66f1d-159">Grant **Impersonate after authenticated** privilege to ORCH\SSOSvcUser</span></span>  
  
    -   <span data-ttu-id="66f1d-160">授予**模拟身份验证后**ORCH\TestAppUser 特权</span><span class="sxs-lookup"><span data-stu-id="66f1d-160">Grant **Impersonate after authenticated** privilege to ORCH\TestAppUser</span></span>  
  
22. <span data-ttu-id="66f1d-161">通过使用 ORCH\TestAppUser 登录到 HIS1 并运行以下应用程序配置，以验证您的部署：</span><span class="sxs-lookup"><span data-stu-id="66f1d-161">Verify your deployment by logging onto HIS1 using ORCH\TestAppUser and running the following application configuration:</span></span>  
  
     <span data-ttu-id="66f1d-162">运行 LogonExternalUser 测试。</span><span class="sxs-lookup"><span data-stu-id="66f1d-162">Run LogonExternalUser Test.</span></span>  
  
    ```  
    <SSO>  
       <application name="TestApp">  
          <description>An SSO Test Affiliate Application</description>  
          <contact>AffAppUser@ESSOV2.EBiz.Com</contact>  
          <appUserAccount>ORCH\TestAffAdminGroup</appUserAccount>  
          <appAdminAccount>ORCH\TestAffUserGroup</appAdminAccount>  
          <field ordinal="0" label="User ID" masked="no" />  
          <field ordinal="1" label="Password" masked="yes" />  
          <flags   
             groupApp="no"   
             configStoreApp="no"   
             allowTickets="no"   
             validateTickets="yes"   
             allowLocalGroups="yes"   
             ticketTimeout="yes"   
             adminGroupSame="no"   
             enableApp="yes"   
             hostInitiatedSSO="yes"   
             validatePassword="yes"/>  
       </application>  
    </SSO>  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="66f1d-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66f1d-163">See Also</span></span>  
 [<span data-ttu-id="66f1d-164">SSO 部署概述</span><span class="sxs-lookup"><span data-stu-id="66f1d-164">SSO Deployment Overview</span></span>](../core/sso-deployment-overview.md)