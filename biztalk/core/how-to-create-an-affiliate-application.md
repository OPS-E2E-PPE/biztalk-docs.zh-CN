---
title: 如何创建关联应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], creating
- applications [SSO], creating
- creating, applications [SSO]
ms.assetid: d0967c4b-6201-416a-9d3a-23b5de5b83d6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8775ea82843641600c9156d79afab49e6cd7c634
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003102"
---
# <a name="how-to-create-an-affiliate-application"></a><span data-ttu-id="e5f68-102">如何创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="e5f68-102">How to Create an Affiliate Application</span></span>
<span data-ttu-id="e5f68-103">您可以使用 MMC 管理单元或此命令根据 XML 文件指定的内容创建一个或多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5f68-103">You can use the MMC Snap-In or this command to create one or more applications, as specified by the XML file.</span></span> <span data-ttu-id="e5f68-104">以下为 Windows 启动的 SSO 的 XML 文件示例：</span><span class="sxs-lookup"><span data-stu-id="e5f68-104">An example XML file for Windows Initiated SSO is:</span></span>  
  
```  
<sso>  
<application name="SAP">  
<description>The SAP application</description>   
<contact>someone@example.com</contact>   
<appuserAccount>domain\AppUserAccount</appuserAccount>   
<appAdminAccount>domain\AppAdminAccount</appAdminAccount>   
<field ordinal="0" label="User Id" masked="no" />   
<field ordinal="1" label="Password" masked="yes" />   
<flags groupApp="no" configStoreApp="no" allowTickets="no" validateTickets="yes" allowLocalAccounts="no" timeoutTickets="yes" adminAccountSame="no" enableApp="no" />  
</application>  
</sso>  
  
```  
  
 <span data-ttu-id="e5f68-105">创建关联应用程序后，将无法修改以下属性：</span><span class="sxs-lookup"><span data-stu-id="e5f68-105">After you create an affiliate application, you cannot modify the following properties:</span></span>  
  
-   <span data-ttu-id="e5f68-106">关联应用程序的名称</span><span class="sxs-lookup"><span data-stu-id="e5f68-106">Name of the affiliate application</span></span>  
  
-   <span data-ttu-id="e5f68-107">与关联应用程序关联的字段</span><span class="sxs-lookup"><span data-stu-id="e5f68-107">Fields associated with the affiliate application</span></span>  
  
-   <span data-ttu-id="e5f68-108">关联应用程序类型（主机组、单项或配置存储）</span><span class="sxs-lookup"><span data-stu-id="e5f68-108">Affiliate application type (host group, individual, or configuration store)</span></span>  
  
-   <span data-ttu-id="e5f68-109">与 Affiliate Administrators 组相同的管理帐户。</span><span class="sxs-lookup"><span data-stu-id="e5f68-109">Administration account same as affiliate administrators group.</span></span> <span data-ttu-id="e5f68-110">（如果指定此标志，则将始终使用 Affiliate Administrators 组作为此关联应用程序的管理员帐户）</span><span class="sxs-lookup"><span data-stu-id="e5f68-110">(Specifying this flag will always use the affiliate administrators group as the administrator account for this affiliate application)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e5f68-111">通过将 allowLocalAccounts 标志设置为“是”，可以为管理帐户和用户帐户使用本地帐户。</span><span class="sxs-lookup"><span data-stu-id="e5f68-111">You can use local accounts for the administration account and user account by setting the allowLocalAccounts flag to yes.</span></span> <span data-ttu-id="e5f68-112">不过，只能在单计算机环境中使用此标志。</span><span class="sxs-lookup"><span data-stu-id="e5f68-112">However, you should only use this flag in single-computer scenarios.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e5f68-113">只有 SSO 管理员或 SSO 关联管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="e5f68-113">You must be an SSO administrator or SSO affiliate administrator to perform this task.</span></span>  
  
 <span data-ttu-id="e5f68-114">只有在创建关联应用程序后才能启用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5f68-114">After you create the affiliate application, you must enable it.</span></span> <span data-ttu-id="e5f68-115">有关详细信息，请参阅[如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-115">For more information, see [How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md).</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="e5f68-116">使用 MMC 管理单元创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="e5f68-116">To create an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="e5f68-117">上**启动**菜单上，单击**程序**，单击**Microsoft 企业单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="e5f68-117">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="e5f68-118">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="e5f68-118">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="e5f68-119">右键单击**关联应用程序**，然后单击**创建应用程序**。</span><span class="sxs-lookup"><span data-stu-id="e5f68-119">Right-click **Affiliate Applications**, and then click **Create Application**.</span></span>  
  
4.  <span data-ttu-id="e5f68-120">按照中的说明**企业单一登录应用程序向导**。</span><span class="sxs-lookup"><span data-stu-id="e5f68-120">Follow the instructions in the **Enterprise Single Sign-On Application Wizard**.</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="e5f68-121">使用命令行创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="e5f68-121">To create an affiliate application using the command line</span></span>  
  
1. <span data-ttu-id="e5f68-122">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="e5f68-122">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="e5f68-123">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="e5f68-123">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="e5f68-124">默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="e5f68-124">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="e5f68-125">类型 * * ssomanage – createapps *\<应用程序的文件名\>**<em>，其中 *\<应用程序文件的名称\></em>是 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="e5f68-125">Type **ssomanage –createapps *\<application file name\>**<em>, where *\<application file name\></em> is the XML file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e5f68-126">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="e5f68-126">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f68-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5f68-127">See Also</span></span>  
 <span data-ttu-id="e5f68-128">[SSO 关联应用程序](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="e5f68-128">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="e5f68-129">[如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="e5f68-129">[How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="e5f68-130">[如何删除关联应用程序](../core/how-to-delete-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="e5f68-130">[How to Delete an Affiliate Application](../core/how-to-delete-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="e5f68-131">[管理用户映射](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="e5f68-131">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="e5f68-132">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="e5f68-132">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)