---
title: 如何创建关联应用程序为主机启动的 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], host initiated SSO
- creating, applications [SSO]
- host initiated SSO, creating affiliate applications
ms.assetid: 06202d21-055a-46bc-acff-da461f5673f1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d207766ce830da973a4767213810f07432c743fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339825"
---
# <a name="how-to-create-affiliate-applications-for-host-initiated-sso"></a><span data-ttu-id="9b400-102">如何为主机启动的 SSO 创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="9b400-102">How to Create Affiliate Applications for Host Initiated SSO</span></span>
<span data-ttu-id="9b400-103">可以定义两种类型的应用程序：</span><span class="sxs-lookup"><span data-stu-id="9b400-103">You can define two types of applications:</span></span>  
  
-   <span data-ttu-id="9b400-104">**单个**没有 Windows 用户和非 Windows 用户之间的一对一关系。</span><span class="sxs-lookup"><span data-stu-id="9b400-104">**Individual** There is a 1 to 1 relationship between Windows users and non-Windows users.</span></span>  
  
-   <span data-ttu-id="9b400-105">**主机组**多个非 Windows 用户可以映射到相同的 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="9b400-105">**Host Group** Multiple non-Windows users can be mapped to the same Windows account.</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="9b400-106">若要创建关联应用程序使用 Mmc 管理单元</span><span class="sxs-lookup"><span data-stu-id="9b400-106">To create an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="9b400-107">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="9b400-107">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="9b400-108">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="9b400-108">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="9b400-109">右键单击**关联应用程序**，然后单击**创建应用程序**以打开**企业单一登录应用程序向导**。</span><span class="sxs-lookup"><span data-stu-id="9b400-109">Right-click **Affiliate Applications**, and then click **Create Application** to open the **Enterprise Single Sign-On Application Wizard**.</span></span>  
  
4.  <span data-ttu-id="9b400-110">使用向导选择关联应用程序的属性。</span><span class="sxs-lookup"><span data-stu-id="9b400-110">Use the wizard to select the properties of your affiliate application.</span></span>  
  
### <a name="to-create-an-individual-type-affiliate-application-using-the-command-line"></a><span data-ttu-id="9b400-111">创建单个类型关联应用程序使用命令行</span><span class="sxs-lookup"><span data-stu-id="9b400-111">To create an individual type affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="9b400-112">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="9b400-112">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="9b400-113">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9b400-113">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9b400-114">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="9b400-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="9b400-115">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="9b400-115">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="9b400-116">类型**ssomanage – createapps \<AffApp.xml\>**，其中 AffApp.xml 是 xml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="9b400-116">Type **ssomanage –createapps \<AffApp.xml\>**, where AffApp.xml is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9b400-117">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="9b400-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="9b400-118">示例文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="9b400-118">A sample file is shown below:</span></span>  
  
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
  
### <a name="to-create-a-host-group-type-affiliate-application-using-the-command-line"></a><span data-ttu-id="9b400-119">创建主机组类型关联应用程序使用命令行</span><span class="sxs-lookup"><span data-stu-id="9b400-119">To create a host group type affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="9b400-120">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="9b400-120">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="9b400-121">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9b400-121">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9b400-122">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="9b400-122">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="9b400-123">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="9b400-123">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="9b400-124">类型**ssomanage – createapps \<AffApp.xml\>**，其中 AffApp.xml 是 xml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="9b400-124">Type **ssomanage –createapps \<AffApp.xml\>**, where AffApp.xml is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9b400-125">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="9b400-125">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="9b400-126">示例文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="9b400-126">A sample file is shown below:</span></span>  
  
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
  
### <a name="to-create-an-affiliate-application-supporting-both-windows-initiated-sso-and-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="9b400-127">若要创建附属机构支持这两个 Windows 应用程序启动的 SSO 和主机启动的 SSO 使用命令行</span><span class="sxs-lookup"><span data-stu-id="9b400-127">To create an affiliate application supporting both Windows initiated SSO and host initiated SSO using the command line</span></span>  
  
1.  <span data-ttu-id="9b400-128">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="9b400-128">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="9b400-129">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9b400-129">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9b400-130">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="9b400-130">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="9b400-131">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="9b400-131">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="9b400-132">类型**ssomanage – createapps \<AffApp.xml\>**，其中 AffApp.xml 是 xml 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="9b400-132">Type **ssomanage –createapps \<AffApp.xml\>**, where AffApp.xml is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9b400-133">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="9b400-133">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="9b400-134">示例文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="9b400-134">A sample file is shown below:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9b400-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b400-135">See Also</span></span>  
 [<span data-ttu-id="9b400-136">主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="9b400-136">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)