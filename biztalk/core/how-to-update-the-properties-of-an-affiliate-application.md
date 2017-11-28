---
title: "如何更新关联应用程序的属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], updating properties
- applications [SSO], properties
ms.assetid: b06eefdd-a5ca-4a32-93d7-72246e31a2e4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 577ded3a225acd8b3f95372075103ab37dfba854
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-the-properties-of-an-affiliate-application"></a><span data-ttu-id="fab33-102">如何更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="fab33-102">How to Update the Properties of an Affiliate Application</span></span>
<span data-ttu-id="fab33-103">您可以使用 MMC 管理单元或此命令根据 XML 文件指定的内容更新一个或多个应用程序属性。</span><span class="sxs-lookup"><span data-stu-id="fab33-103">You can use the MMC Snap-In or this command to update one or more application properties, as specified by the XML file.</span></span> <span data-ttu-id="fab33-104">只有关联管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="fab33-104">You must be an Affiliate Administrator to perform this task.</span></span> <span data-ttu-id="fab33-105">下面是一个示例 XML 文件，其中列出了可更新的字段：</span><span class="sxs-lookup"><span data-stu-id="fab33-105">The following is an example XML file that lists the fields you can update.</span></span>  
  
```  
<SSO>  
<application name="SSOApplication">  
<description>An SSO Application</description>  
<contact>someone@companyname.com</contact>  
<appUserAccount>DomainName\AppUserGroup</appUserAccount>  
<appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>  
<flags allowTickets="no" validateTickets="yes"  timeoutTickets="yes" enableApp="no" />  
</application>  
</SSO>  
  
```  
  
 <span data-ttu-id="fab33-106">创建关联应用程序后，将无法修改以下属性：</span><span class="sxs-lookup"><span data-stu-id="fab33-106">After you create an affiliate application, you cannot modify the following properties:</span></span>  
  
-   <span data-ttu-id="fab33-107">关联应用程序的名称</span><span class="sxs-lookup"><span data-stu-id="fab33-107">Name of the affiliate application</span></span>  
  
-   <span data-ttu-id="fab33-108">与关联应用程序关联的字段</span><span class="sxs-lookup"><span data-stu-id="fab33-108">Fields associated with the affiliate application</span></span>  
  
-   <span data-ttu-id="fab33-109">关联应用程序类型（主机组、单项或配置存储）</span><span class="sxs-lookup"><span data-stu-id="fab33-109">Affiliate application type (host group, individual, or configuration store)</span></span>  
  
-   <span data-ttu-id="fab33-110">与 Affiliate Administrators 组相同的管理帐户。</span><span class="sxs-lookup"><span data-stu-id="fab33-110">Administration account same as affiliate administrators group.</span></span> <span data-ttu-id="fab33-111">（如果指定此标志，则将始终使用 Affiliate Administrators 组作为此关联应用程序的管理员帐户）</span><span class="sxs-lookup"><span data-stu-id="fab33-111">(Specifying this flag will always use the affiliate administrators group as the administrator account for this affiliate application)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fab33-112">通过将 allowLocalAccounts 标志设置为“是”，可以为管理帐户和用户帐户使用本地帐户。</span><span class="sxs-lookup"><span data-stu-id="fab33-112">You can use local accounts for the administration account and user account by setting the allowLocalAccounts flag to yes.</span></span> <span data-ttu-id="fab33-113">但是，你只可以在单计算机方案中使用此标志。</span><span class="sxs-lookup"><span data-stu-id="fab33-113">However, you can only use this flag in single-computer scenarios.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fab33-114">只有 SSO 管理员、SSO 关联管理员或应用程序管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="fab33-114">You must be an SSO administrator, SSO affiliate administrator, or application administrator to perform this task.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fab33-115">只有 SSO 管理员才能修改票证标志（validateTickets 和 timeoutTickets）。</span><span class="sxs-lookup"><span data-stu-id="fab33-115">You must be an SSO administrator to modify the ticketing flags (validateTickets and timeoutTickets).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fab33-116">只有 SSO 管理员或 SSO 关联管理员才能修改应用程序管理帐户。</span><span class="sxs-lookup"><span data-stu-id="fab33-116">You must be an SSO administrator or an SSO affiliate administrator to modify the application administration account.</span></span>  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="fab33-117">使用 MMC 管理单元更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="fab33-117">To update the properties of an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="fab33-118">上**启动**菜单上，单击**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="fab33-118">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="fab33-119">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="fab33-119">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="fab33-120">右键单击 affililate 应用程序，并依次**更新**。</span><span class="sxs-lookup"><span data-stu-id="fab33-120">Right-click the affililate application, and then click **Update**.</span></span>  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="fab33-121">使用命令行更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="fab33-121">To update the properties of an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="fab33-122">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="fab33-122">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="fab33-123">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="fab33-123">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="fab33-124">默认安装目录是**\<驱动器 >**: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="fab33-124">The default installation directory is **\<drive>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="fab33-125">类型**ssomanage-updateapps\<应用程序文件名称 >**，其中应用程序文件名称是 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="fab33-125">Type **ssomanage –updateapps \<application file name>**, where the application file name is the XML file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fab33-126">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="fab33-126">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab33-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fab33-127">See Also</span></span>  
 <span data-ttu-id="fab33-128">[SSO 关联应用程序](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="fab33-128">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="fab33-129">[如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="fab33-129">[How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="fab33-130">[管理用户映射](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="fab33-130">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="fab33-131">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="fab33-131">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)