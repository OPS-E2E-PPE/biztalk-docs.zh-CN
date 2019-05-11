---
title: 如何更新关联应用程序的属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], updating properties
- applications [SSO], properties
ms.assetid: b06eefdd-a5ca-4a32-93d7-72246e31a2e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6c50664fcf9e87ed6980a031fed980bf1e01301
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333659"
---
# <a name="how-to-update-the-properties-of-an-affiliate-application"></a><span data-ttu-id="408f5-102">如何更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="408f5-102">How to Update the Properties of an Affiliate Application</span></span>
<span data-ttu-id="408f5-103">可以使用 MMC 管理单元或此命令更新一个或多个应用程序属性，指定的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="408f5-103">You can use the MMC Snap-In or this command to update one or more application properties, as specified by the XML file.</span></span> <span data-ttu-id="408f5-104">必须是关联管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="408f5-104">You must be an Affiliate Administrator to perform this task.</span></span> <span data-ttu-id="408f5-105">下面是示例 XML 文件，其中列出了可更新的字段。</span><span class="sxs-lookup"><span data-stu-id="408f5-105">The following is an example XML file that lists the fields you can update.</span></span>  
  
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
  
 <span data-ttu-id="408f5-106">创建关联应用程序后，无法修改以下属性：</span><span class="sxs-lookup"><span data-stu-id="408f5-106">After you create an affiliate application, you cannot modify the following properties:</span></span>  
  
-   <span data-ttu-id="408f5-107">关联应用程序的名称</span><span class="sxs-lookup"><span data-stu-id="408f5-107">Name of the affiliate application</span></span>  
  
-   <span data-ttu-id="408f5-108">与关联应用程序关联的字段</span><span class="sxs-lookup"><span data-stu-id="408f5-108">Fields associated with the affiliate application</span></span>  
  
-   <span data-ttu-id="408f5-109">关联应用程序类型 （主机组、 单项或配置存储区）</span><span class="sxs-lookup"><span data-stu-id="408f5-109">Affiliate application type (host group, individual, or configuration store)</span></span>  
  
-   <span data-ttu-id="408f5-110">相同与 affiliate administrators 组的管理帐户。</span><span class="sxs-lookup"><span data-stu-id="408f5-110">Administration account same as affiliate administrators group.</span></span> <span data-ttu-id="408f5-111">（指定此标志将始终使用 affiliate administrators 组的管理员帐户作为此关联应用程序）</span><span class="sxs-lookup"><span data-stu-id="408f5-111">(Specifying this flag will always use the affiliate administrators group as the administrator account for this affiliate application)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="408f5-112">可以通过此 allowLocalAccounts 标志设置为是使用管理帐户的本地帐户和用户帐户。</span><span class="sxs-lookup"><span data-stu-id="408f5-112">You can use local accounts for the administration account and user account by setting the allowLocalAccounts flag to yes.</span></span> <span data-ttu-id="408f5-113">但是，仅可以在单计算机方案中使用此标志。</span><span class="sxs-lookup"><span data-stu-id="408f5-113">However, you can only use this flag in single-computer scenarios.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="408f5-114">必须是 SSO 管理员、 SSO 关联管理员或应用程序管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="408f5-114">You must be an SSO administrator, SSO affiliate administrator, or application administrator to perform this task.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="408f5-115">必须是 SSO 管理员才能修改票证标志 （validateTickets 和 timeoutTickets）。</span><span class="sxs-lookup"><span data-stu-id="408f5-115">You must be an SSO administrator to modify the ticketing flags (validateTickets and timeoutTickets).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="408f5-116">您必须是 SSO 管理员或 SSO 关联管理员才能修改应用程序管理帐户。</span><span class="sxs-lookup"><span data-stu-id="408f5-116">You must be an SSO administrator or an SSO affiliate administrator to modify the application administration account.</span></span>  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="408f5-117">若要更新的关联应用程序使用 Mmc 管理单元属性</span><span class="sxs-lookup"><span data-stu-id="408f5-117">To update the properties of an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="408f5-118">上**启动**菜单上，单击**程序**，单击**Microsoft 企业单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="408f5-118">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="408f5-119">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="408f5-119">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="408f5-120">右键单击关联应用程序，然后依次**更新**。</span><span class="sxs-lookup"><span data-stu-id="408f5-120">Right-click the affililate application, and then click **Update**.</span></span>  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="408f5-121">若要更新的关联应用程序使用命令行属性</span><span class="sxs-lookup"><span data-stu-id="408f5-121">To update the properties of an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="408f5-122">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="408f5-122">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="408f5-123">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="408f5-123">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="408f5-124">默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="408f5-124">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="408f5-125">类型**ssomanage – updateapps\<应用程序文件名\>**，其中应用程序文件名称是 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="408f5-125">Type **ssomanage –updateapps \<application file name\>**, where the application file name is the XML file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="408f5-126">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="408f5-126">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="408f5-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="408f5-127">See Also</span></span>  
 <span data-ttu-id="408f5-128">[SSO 关联应用程序](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="408f5-128">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="408f5-129">[如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="408f5-129">[How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="408f5-130">[管理用户映射](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="408f5-130">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="408f5-131">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="408f5-131">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)