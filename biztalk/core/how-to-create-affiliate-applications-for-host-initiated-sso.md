---
title: "如何创建关联应用程序为主机启动的 SSO |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [SSO], host initiated SSO
- creating, applications [SSO]
- host initiated SSO, creating affiliate applications
ms.assetid: 06202d21-055a-46bc-acff-da461f5673f1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce8a5cf43cd1d6e455492a74985edb91f2cb0a94
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-create-affiliate-applications-for-host-initiated-sso"></a><span data-ttu-id="680c1-102">如何创建关联应用程序为主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="680c1-102">How to Create Affiliate Applications for Host Initiated SSO</span></span>
<span data-ttu-id="680c1-103">可以定义两种类型的应用程序：</span><span class="sxs-lookup"><span data-stu-id="680c1-103">You can define two types of applications:</span></span>  
  
-   <span data-ttu-id="680c1-104">**单个**没有 Windows 用户和非 Windows 用户之间的 1 对 1 关系。</span><span class="sxs-lookup"><span data-stu-id="680c1-104">**Individual** There is a 1 to 1 relationship between Windows users and non-Windows users.</span></span>  
  
-   <span data-ttu-id="680c1-105">**主机组**多个非 Windows 用户可以映射到相同的 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="680c1-105">**Host Group** Multiple non-Windows users can be mapped to the same Windows account.</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="680c1-106">使用 MMC 管理单元创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="680c1-106">To create an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="680c1-107">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="680c1-107">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="680c1-108">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="680c1-108">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="680c1-109">右键单击**Affiliate 应用程序**，然后单击**创建应用程序**以打开**企业单一登录在应用程序向导**。</span><span class="sxs-lookup"><span data-stu-id="680c1-109">Right-click **Affiliate Applications**, and then click **Create Application** to open the **Enterprise Single Sign-On Application Wizard**.</span></span>  
  
4.  <span data-ttu-id="680c1-110">使用该向导选择关联应用程序的属性。</span><span class="sxs-lookup"><span data-stu-id="680c1-110">Use the wizard to select the properties of your affiliate application.</span></span>  
  
### <a name="to-create-an-individual-type-affiliate-application-using-the-command-line"></a><span data-ttu-id="680c1-111">使用命令行创建“单项”类型的关联应用程序</span><span class="sxs-lookup"><span data-stu-id="680c1-111">To create an individual type affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="680c1-112">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="680c1-112">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="680c1-113">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="680c1-113">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="680c1-114">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="680c1-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="680c1-115">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="680c1-115">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="680c1-116">类型**ssomanage-createapps \<AffApp.xml\>**，其中 AffApp.xml 是 xml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="680c1-116">Type **ssomanage –createapps \<AffApp.xml\>**, where AffApp.xml is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="680c1-117">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="680c1-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="680c1-118">以下显示了一个文件示例：</span><span class="sxs-lookup"><span data-stu-id="680c1-118">A sample file is shown below:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
      <application name="SSOApp_Host1">  
        <description>An Individual Type Affiliate Application for Host Initiated SSO</description>  
        <contact>someone@companyname.com</contact>  
        <appUserAccount>DomainName\AppUserGroup_HISSO</appUserAccount>  
        <appAdminAccount>DomainName\AppAdminGroup_HISSO</appAdminAccount>  
        <field ordinal="0" label="User ID" masked="no" />  
        <field ordinal="1" label="Password" masked="yes" />  
        <flags windowsInitiatedSSO="no" enableApp="yes" />  
      </application>  
    </SSO>  
  
    ```  
  
### <a name="to-create-a-host-group-type-affiliate-application-using-the-command-line"></a><span data-ttu-id="680c1-119">使用命令行创建“主机组”类型的关联应用程序</span><span class="sxs-lookup"><span data-stu-id="680c1-119">To create a host group type affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="680c1-120">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="680c1-120">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="680c1-121">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="680c1-121">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="680c1-122">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="680c1-122">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="680c1-123">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="680c1-123">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="680c1-124">类型**ssomanage-createapps \<AffApp.xml\>**，其中 AffApp.xml 是 xml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="680c1-124">Type **ssomanage –createapps \<AffApp.xml\>**, where AffApp.xml is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="680c1-125">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="680c1-125">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="680c1-126">以下显示了一个文件示例：</span><span class="sxs-lookup"><span data-stu-id="680c1-126">A sample file is shown below:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
      <application name="SSOApp_HostGroupApp1">  
        <description>A Group Type Affiliate Application for Host Initiated SSO associating multiple non-Windows user to a single Windows user account(DomainName\WindowsUserAccount1)</description>  
        <contact>someone@companyname.com</contact>  
        <windowsAccount>DomainName\WindowsUserAccount1</windowsAccount>  
        <appAdminAccount>DomainName\AppAdminGroup_HISSO</appAdminAccount>  
        <field ordinal="0" label="User ID" masked="no" />  
        <field ordinal="1" label="Password" masked="yes" />  
        <flags  enableApp="yes" />  
      </application>  
    </SSO>  
  
    ```  
  
### <a name="to-create-an-affiliate-application-supporting-both-windows-initiated-sso-and-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="680c1-127">使用命令行创建同时支持 Windows 启动的 SSO 和主机启动的 SSO 的关联应用程序</span><span class="sxs-lookup"><span data-stu-id="680c1-127">To create an affiliate application supporting both Windows initiated SSO and host initiated SSO using the command line</span></span>  
  
1.  <span data-ttu-id="680c1-128">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="680c1-128">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="680c1-129">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="680c1-129">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="680c1-130">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="680c1-130">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="680c1-131">默认值是\<驱动器\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="680c1-131">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="680c1-132">类型**ssomanage-createapps \<AffApp.xml\>**，其中 AffApp.xml 是 xml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="680c1-132">Type **ssomanage –createapps \<AffApp.xml\>**, where AffApp.xml is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="680c1-133">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="680c1-133">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="680c1-134">以下显示了一个文件示例：</span><span class="sxs-lookup"><span data-stu-id="680c1-134">A sample file is shown below:</span></span>  
  
    ```  
    <?xml version="1.0" ?>   
    - <SSO>  
    - <application name="SSOApp1">  
      <description>An Individual Type Affiliate Application for both Host Initiated SSO and Windows Initiated SSO</description>   
      <contact>someone@companyname.com</contact>   
      <appUserAccount>DomainName\AppUserGroup</appUserAccount>   
      <appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>   
      <field ordinal="0" label="User ID" masked="no" />   
      <field ordinal="1" label="Password" masked="yes" />   
      <flags  enableApp="yes" />   
      </application>  
      </SSO>  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="680c1-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="680c1-135">See Also</span></span>  
 [<span data-ttu-id="680c1-136">主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="680c1-136">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)