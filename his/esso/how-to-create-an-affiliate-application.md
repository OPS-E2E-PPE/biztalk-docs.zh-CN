---
title: 如何创建关联应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3be483f8-2617-459e-9081-aab886c75d93
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 5145111b2c585edab92cc10c3e3614e8bb91a85d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250985"
---
# <a name="how-to-create-an-affiliate-application"></a><span data-ttu-id="e8768-102">如何创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="e8768-102">How to Create an Affiliate Application</span></span>
<span data-ttu-id="e8768-103">你可以使用 Mmc 管理单元或**createapps**命令以创建一个或多个应用程序，为指定的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="e8768-103">You can use the MMC Snap-In or the **createapps** command to create one or more applications, as specified by the XML file.</span></span> <span data-ttu-id="e8768-104">下面是示例 XML 文件的 Windows-Initiated 单一登录 (SSO):</span><span class="sxs-lookup"><span data-stu-id="e8768-104">The following is an example XML file for Windows-Initiated Single Sign-On (SSO):</span></span>  
  
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
  
 <span data-ttu-id="e8768-105">创建关联应用程序后，将无法修改以下属性：</span><span class="sxs-lookup"><span data-stu-id="e8768-105">After you create an affiliate application, you cannot modify the following properties:</span></span>  
  
-   <span data-ttu-id="e8768-106">关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="e8768-106">Name of the affiliate application.</span></span>  
  
-   <span data-ttu-id="e8768-107">关联应用程序与关联的字段。</span><span class="sxs-lookup"><span data-stu-id="e8768-107">Fields associated with the affiliate application.</span></span>  
  
-   <span data-ttu-id="e8768-108">Affiliate 应用程序类型 （主机组、 个人或配置存储区）。</span><span class="sxs-lookup"><span data-stu-id="e8768-108">Affiliate application type (host group, individual, or configuration store).</span></span>  
  
-   <span data-ttu-id="e8768-109">与 Affiliate Administrators 组相同的管理帐户。</span><span class="sxs-lookup"><span data-stu-id="e8768-109">Administration account same as affiliate administrators group.</span></span> <span data-ttu-id="e8768-110">（指定此标志将始终使用分支机构的管理员组的管理员帐户作为此关联应用程序。）</span><span class="sxs-lookup"><span data-stu-id="e8768-110">(Specifying this flag will always use the affiliate administrators group as the administrator account for this affiliate application.)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e8768-111">通过将 allowLocalAccounts 标志设置为“是”，可以为管理帐户和用户帐户使用本地帐户。</span><span class="sxs-lookup"><span data-stu-id="e8768-111">You can use local accounts for the administration account and user account by setting the allowLocalAccounts flag to yes.</span></span> <span data-ttu-id="e8768-112">不过，只能在单计算机环境中使用此标志。</span><span class="sxs-lookup"><span data-stu-id="e8768-112">However, you should only use this flag in single-computer scenarios.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e8768-113">只有 SSO 管理员或 SSO 关联管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="e8768-113">You must be an SSO administrator or SSO affiliate administrator to perform this task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8768-114">如果你正在进行配置域控制器，并创建关联应用程序时，为应用程序管理员或应用程序的用户的域本地的作用域组指定，建议您启用本地帐户标记。</span><span class="sxs-lookup"><span data-stu-id="e8768-114">If you are performing the configuration on a Domain Controller, and the Domain Local scope groups are specified for Application Administrators or Application Users while creating Affiliate Applications, it is recommended that you enable the local account flag.</span></span> <span data-ttu-id="e8768-115">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e8768-115">To do this:</span></span>  
  
-   <span data-ttu-id="e8768-116">在 MMC 管理单元中，在创建过程期间选择允许的访问帐户的本地帐户。</span><span class="sxs-lookup"><span data-stu-id="e8768-116">In the MMC Snap-in, select Allow local accounts for access accounts during the creation process.</span></span>  
  
-   <span data-ttu-id="e8768-117">从命令行中，指定 allowLocalAccounts = Affiliate 应用程序创建的 XML 文件中的是。</span><span class="sxs-lookup"><span data-stu-id="e8768-117">From the command line, specify allowLocalAccounts=yes in the XML file for Affiliate Application creation.</span></span>  
  
 <span data-ttu-id="e8768-118">只有在创建关联应用程序后才能启用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="e8768-118">After you create the affiliate application, you must enable it.</span></span> <span data-ttu-id="e8768-119">有关详细信息，请参阅[如何启用 Affiliate 应用程序](../esso/how-to-enable-an-affiliate-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e8768-119">For more information, see [How to Enable an Affiliate Application](../esso/how-to-enable-an-affiliate-application.md).</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-microsoft-management-console-mmc-snap-in"></a><span data-ttu-id="e8768-120">若要创建使用 Microsoft 管理控制台 (MMC) 管理单元中的关联应用程序</span><span class="sxs-lookup"><span data-stu-id="e8768-120">To create an affiliate application using the Microsoft Management Console (MMC) Snap-In</span></span>  
  
1.  <span data-ttu-id="e8768-121">单击**启动**，指向**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="e8768-121">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="e8768-122">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="e8768-122">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="e8768-123">右键单击**Affiliate 应用程序**，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="e8768-123">Right-click **Affiliate Applications**, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="e8768-124">按照中的说明**创建新 Affiliate 应用程序**向导。</span><span class="sxs-lookup"><span data-stu-id="e8768-124">Follow the instructions in the **Create New Affiliate Application** wizard.</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="e8768-125">使用命令行创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="e8768-125">To create an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="e8768-126">单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="e8768-126">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="e8768-127">在命令提示符处，转到企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="e8768-127">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="e8768-128">默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="e8768-128">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="e8768-129">类型`ssomanage –createapps <application file name>`，其中*\<应用程序文件名称 >* 是 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="e8768-129">Type `ssomanage –createapps <application file name>`, where *\<application file name>* is the XML file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8768-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8768-130">See Also</span></span>  
 <span data-ttu-id="e8768-131">[SSO 关联应用程序](../esso/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="e8768-131">[SSO Affiliate Applications](../esso/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="e8768-132">[如何启用关联应用程序](../esso/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="e8768-132">[How to Enable an Affiliate Application](../esso/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="e8768-133">[如何删除关联应用程序](../esso/how-to-delete-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="e8768-133">[How to Delete an Affiliate Application](../esso/how-to-delete-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="e8768-134">[管理用户映射](../esso/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="e8768-134">[Managing User Mappings](../esso/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="e8768-135">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="e8768-135">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)