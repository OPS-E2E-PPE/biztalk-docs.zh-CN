---
title: 部署进程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, deploying
- deploying, SSO
- LogonExternalUser test [SSO]
- security, SSO
- SSO, LogonExternalUser test
- SSO, security
ms.assetid: 7dd4c022-c70b-467a-bf94-dc4ac6029f81
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89b5e3640626ce63a58532568b08b7290bc40c4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389742"
---
# <a name="deployment-process"></a><span data-ttu-id="07764-102">部署过程</span><span class="sxs-lookup"><span data-stu-id="07764-102">Deployment Process</span></span>
<span data-ttu-id="07764-103">以下步骤进行安全的企业单一登录部署了高级概述。</span><span class="sxs-lookup"><span data-stu-id="07764-103">The following steps give a high-level overview of secure deployment of Enterprise Single Sign-On.</span></span> <span data-ttu-id="07764-104">要在 SQL Server 中执行的操作的详细过程，请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="07764-104">For detailed procedures on the actions to take in SQL Server, see your SQL Server documentation.</span></span>  
  
1.  <span data-ttu-id="07764-105">在 SQL Server 域控制器上，使用新建信任向导来创建具有以下属性的信任：</span><span class="sxs-lookup"><span data-stu-id="07764-105">On the SQL Server domain controller, use the New Trust Wizard to create a trust with the following properties:</span></span>  
  
    -   <span data-ttu-id="07764-106">**名称：** ORCH.com</span><span class="sxs-lookup"><span data-stu-id="07764-106">**Name:** ORCH.com</span></span>  
  
    -   <span data-ttu-id="07764-107">**方向：** 双向</span><span class="sxs-lookup"><span data-stu-id="07764-107">**Direction:** Two-way</span></span>  
  
    -   <span data-ttu-id="07764-108">**信任方：** 仅限此域</span><span class="sxs-lookup"><span data-stu-id="07764-108">**Sides:** This domain only</span></span>  
  
    -   <span data-ttu-id="07764-109">**传出信任身份验证级别-本地域：** 选择性身份验证</span><span class="sxs-lookup"><span data-stu-id="07764-109">**Outgoing Trust Authentication Level - Local Domain:** Selective authentication</span></span>  
  
    -   <span data-ttu-id="07764-110">**密码：** 选择的密码</span><span class="sxs-lookup"><span data-stu-id="07764-110">**Password:** Choose a password</span></span>  
  
    -   <span data-ttu-id="07764-111">**确认传出信任：** 是</span><span class="sxs-lookup"><span data-stu-id="07764-111">**Confirm Outgoing Trust:** Yes</span></span>  
  
    -   <span data-ttu-id="07764-112">**确认传入信任：** 否</span><span class="sxs-lookup"><span data-stu-id="07764-112">**Confirm Incoming Trust:** No</span></span>  
  
2.  <span data-ttu-id="07764-113">在 ORCH.com 域控制器上，使用新建信任向导来创建具有以下属性的信任：</span><span class="sxs-lookup"><span data-stu-id="07764-113">On the ORCH.com domain controller, use the New Trust Wizard to create a trust with the following properties:</span></span>  
  
    -   <span data-ttu-id="07764-114">**名称：** SQL.com</span><span class="sxs-lookup"><span data-stu-id="07764-114">**Name:** SQL.com</span></span>  
  
    -   <span data-ttu-id="07764-115">**方向：** 双向</span><span class="sxs-lookup"><span data-stu-id="07764-115">**Direction:** Two-way</span></span>  
  
    -   <span data-ttu-id="07764-116">**信任方：** 仅限此域</span><span class="sxs-lookup"><span data-stu-id="07764-116">**Sides:** This domain only</span></span>  
  
    -   <span data-ttu-id="07764-117">**传出信任身份验证级别-本地域：** 选择性身份验证</span><span class="sxs-lookup"><span data-stu-id="07764-117">**Outgoing Trust Authentication Level - Local Domain:** Selective authentication</span></span>  
  
    -   <span data-ttu-id="07764-118">**密码：** 必须为 ORCH.com 的密码相同</span><span class="sxs-lookup"><span data-stu-id="07764-118">**Password:** Must be the same as password for ORCH.com</span></span>  
  
    -   <span data-ttu-id="07764-119">**确认传出信任：** 是</span><span class="sxs-lookup"><span data-stu-id="07764-119">**Confirm Outgoing Trust:** Yes</span></span>  
  
    -   <span data-ttu-id="07764-120">**确认传入信任：** 否</span><span class="sxs-lookup"><span data-stu-id="07764-120">**Confirm Incoming Trust:** No</span></span>  
  
3.  <span data-ttu-id="07764-121">在 ORCH.com 域控制器上，从 SQL.COM 设置传入域范围信任。</span><span class="sxs-lookup"><span data-stu-id="07764-121">On the ORCH.com domain controller, set the domain wide trust for Incoming from SQL.COM.</span></span>  
  
4.  <span data-ttu-id="07764-122">在 SQL.com 域控制器设置从 ORCH.COM 的传出域范围信任。</span><span class="sxs-lookup"><span data-stu-id="07764-122">On the SQL.com domain controller, set the domain wide trust for Outgoing from ORCH.COM.</span></span>  
  
5.  <span data-ttu-id="07764-123">在 ORCH.com 域控制器上，域功能级别提升到 Windows Server 2008 SP2 或 Windows Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="07764-123">On the ORCH.com domain controller, raise the domain functional level to Windows Server 2008 SP2 or Windows Server 2008 R2.</span></span>  
  
6.  <span data-ttu-id="07764-124">在 ORCH 域中，创建以下新用户：</span><span class="sxs-lookup"><span data-stu-id="07764-124">In the ORCH domain, create the following new users:</span></span>  
  
    -   <span data-ttu-id="07764-125">ORCH\SSOSvcUser</span><span class="sxs-lookup"><span data-stu-id="07764-125">ORCH\SSOSvcUser</span></span>  
  
    -   <span data-ttu-id="07764-126">ORCH\TestAppUser</span><span class="sxs-lookup"><span data-stu-id="07764-126">ORCH\TestAppUser</span></span>  
  
    -   <span data-ttu-id="07764-127">ORCH\AffAppUser</span><span class="sxs-lookup"><span data-stu-id="07764-127">ORCH\AffAppUser</span></span>  
  
7.  <span data-ttu-id="07764-128">添加**充当操作系统的一部分**到 SSOSvcUser 和 TestAppUser。</span><span class="sxs-lookup"><span data-stu-id="07764-128">Add **Act as part of the operating system** to SSOSvcUser and TestAppUser.</span></span>  
  
8.  <span data-ttu-id="07764-129">添加**进行身份验证允许**到 ORCH\TestAdmin 特权。</span><span class="sxs-lookup"><span data-stu-id="07764-129">Add **Allowed to Authenticate** privilege to ORCH\TestAdmin.</span></span>  
  
9. <span data-ttu-id="07764-130">将 ORCH\SSOSvcUser 添加到 SQL 域中的 SQL2 中。</span><span class="sxs-lookup"><span data-stu-id="07764-130">Add ORCH\SSOSvcUser to SQL2 in the SQL domain.</span></span> <span data-ttu-id="07764-131">（此步骤需要使用 Active Directory MMC 中的高级视图。）</span><span class="sxs-lookup"><span data-stu-id="07764-131">(This step requires using Advanced View in Active Directory MMC.)</span></span>  
  
10. <span data-ttu-id="07764-132">在 SQL2 计算机上创建以下两个新登录名：</span><span class="sxs-lookup"><span data-stu-id="07764-132">On the SQL2 computer, create the following two new logins:</span></span>  
  
    -   <span data-ttu-id="07764-133">ORCH\TestAdmin</span><span class="sxs-lookup"><span data-stu-id="07764-133">ORCH\TestAdmin</span></span>  
  
    -   <span data-ttu-id="07764-134">ORCH\SSOSvcUser</span><span class="sxs-lookup"><span data-stu-id="07764-134">ORCH\SSOSvcUser</span></span>  
  
11. <span data-ttu-id="07764-135">在 SQL2 域上创建两个域全局组：</span><span class="sxs-lookup"><span data-stu-id="07764-135">On the SQL2 domain, create two domain global groups:</span></span>  
  
    -   <span data-ttu-id="07764-136">ORCH\SSOAdminGroup</span><span class="sxs-lookup"><span data-stu-id="07764-136">ORCH\SSOAdminGroup</span></span>  
  
    -   <span data-ttu-id="07764-137">ORCH\SSOAffAdminGroup</span><span class="sxs-lookup"><span data-stu-id="07764-137">ORCH\SSOAffAdminGroup</span></span>  
  
12. <span data-ttu-id="07764-138">添加**进行身份验证允许**到 ORCH\SSOAdminGroup 组的权限。</span><span class="sxs-lookup"><span data-stu-id="07764-138">Add **Allowed to Authenticate** privilege to the ORCH\SSOAdminGroup group.</span></span>  
  
13. <span data-ttu-id="07764-139">在 SQL2 数据库上创建以下新登录名：</span><span class="sxs-lookup"><span data-stu-id="07764-139">On the SQL2 database, create the following new login:</span></span>  
  
    -   <span data-ttu-id="07764-140">ORCH\SSOAdminGroup</span><span class="sxs-lookup"><span data-stu-id="07764-140">ORCH\SSOAdminGroup</span></span>  
  
14. <span data-ttu-id="07764-141">安装主密钥服务器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="07764-141">Install the Master Secret Server as follows:</span></span>  
  
    -   <span data-ttu-id="07764-142">使用 ORCH\TestAdmin 登录到 NTS5。</span><span class="sxs-lookup"><span data-stu-id="07764-142">Log on to NTS5 using ORCH\TestAdmin.</span></span>  
  
    -   <span data-ttu-id="07764-143">安装 ESSO 将 SQL2 用作主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="07764-143">Install ESSO, using SQL2 as the Master Secret Server.</span></span>  
  
15. <span data-ttu-id="07764-144">使用 ORCH\TestAdmin，登录到 HIS1 并安装企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="07764-144">Log onto HIS1 using ORCH\TestAdmin, and install Enterprise Single Sign-On.</span></span> <span data-ttu-id="07764-145">使用数据库服务器名称 SQL2 为 SSO 联接 HIS2，来将 ESSO 配置。</span><span class="sxs-lookup"><span data-stu-id="07764-145">Configure ESSO as SSO join HIS2, using database server name SQL2.</span></span>  
  
16. <span data-ttu-id="07764-146">安装使用 ORCH\TestAdmin 在 HIS3 上的企业单一登录管理员实用程序。</span><span class="sxs-lookup"><span data-stu-id="07764-146">Install the Enterprise Single Sign-On Admin utility on HIS3 using ORCH\TestAdmin.</span></span>  
  
17. <span data-ttu-id="07764-147">将以下用户添加到以下组：</span><span class="sxs-lookup"><span data-stu-id="07764-147">Add the following users to the following groups:</span></span>  
  
    -   <span data-ttu-id="07764-148">将 ORCH\TestAppUser 添加到 orch\ssoadmingroup 中</span><span class="sxs-lookup"><span data-stu-id="07764-148">Add ORCH\TestAppUser to ORCH\SSOAdminGroup</span></span>  
  
    -   <span data-ttu-id="07764-149">将 ORCH\AffAppUser 添加到 orch\testaffusergroup 中</span><span class="sxs-lookup"><span data-stu-id="07764-149">Add ORCH\AffAppUser to ORCH\TestAffUserGroup</span></span>  
  
18. <span data-ttu-id="07764-150">SQL Server Enterprise Edition HIS3 上安装，并添加登录名 ORCH\AffAppUser。</span><span class="sxs-lookup"><span data-stu-id="07764-150">Install SQL Server Enterprise Edition on HIS3, and add login ORCH\AffAppUser.</span></span>  
  
19. <span data-ttu-id="07764-151">在 HIS1 计算机上打开命令提示符并使用以下命令设置约束委派和协议转换：</span><span class="sxs-lookup"><span data-stu-id="07764-151">On the HIS1 computer, open a command prompt and use the following commands to set constrain delegation and protocol transition:</span></span>  
  
    -   <span data-ttu-id="07764-152">**setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\SSOSvcUser**</span><span class="sxs-lookup"><span data-stu-id="07764-152">**setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\SSOSvcUser**</span></span>  
  
    -   <span data-ttu-id="07764-153">**setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\TestAppUser**</span><span class="sxs-lookup"><span data-stu-id="07764-153">**setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\TestAppUser**</span></span>  
  
20. <span data-ttu-id="07764-154">上**ORCH\SSOSvcUser**并**ORCH\TestAppUser**属性页中，通过选择以下选项设置为这两个用户帐户适当的委托：</span><span class="sxs-lookup"><span data-stu-id="07764-154">On the **ORCH\SSOSvcUser** and **ORCH\TestAppUser** property pages, set the proper delegation for both user accounts by selecting the following options:</span></span>  
  
    -   <span data-ttu-id="07764-155">**信任仅委派到指定服务的用户**</span><span class="sxs-lookup"><span data-stu-id="07764-155">**Trust this user for delegation to specified services only**</span></span>  
  
    -   <span data-ttu-id="07764-156">**使用任何身份验证协议**</span><span class="sxs-lookup"><span data-stu-id="07764-156">**Use any authentication protocol**</span></span>  
  
21. <span data-ttu-id="07764-157">在 HIS1 计算机上使用 ORCH\TestAdmin，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="07764-157">Using ORCH\TestAdmin on the HIS1 computer, perform the following:</span></span>  
  
    -   <span data-ttu-id="07764-158">将 ORCH\TestAppUser 添加到远程桌面用户组</span><span class="sxs-lookup"><span data-stu-id="07764-158">Add ORCH\TestAppUser to Remote Desktop User Group</span></span>  
  
    -   <span data-ttu-id="07764-159">授予**进行身份验证之后模拟**权限授予 ORCH\SSOSvcUser</span><span class="sxs-lookup"><span data-stu-id="07764-159">Grant **Impersonate after authenticated** privilege to ORCH\SSOSvcUser</span></span>  
  
    -   <span data-ttu-id="07764-160">授予**进行身份验证之后模拟**特权授予 ORCH\TestAppUser</span><span class="sxs-lookup"><span data-stu-id="07764-160">Grant **Impersonate after authenticated** privilege to ORCH\TestAppUser</span></span>  
  
22. <span data-ttu-id="07764-161">通过登录到 HIS1 验证您的部署使用 ORCH\TestAppUser 并运行以下应用程序配置：</span><span class="sxs-lookup"><span data-stu-id="07764-161">Verify your deployment by logging onto HIS1 using ORCH\TestAppUser and running the following application configuration:</span></span>  
  
     <span data-ttu-id="07764-162">运行 LogonExternalUser 测试。</span><span class="sxs-lookup"><span data-stu-id="07764-162">Run LogonExternalUser Test.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="07764-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="07764-163">See Also</span></span>  
 [<span data-ttu-id="07764-164">SSO 部署概述</span><span class="sxs-lookup"><span data-stu-id="07764-164">SSO Deployment Overview</span></span>](../core/sso-deployment-overview.md)