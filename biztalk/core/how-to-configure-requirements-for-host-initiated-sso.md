---
title: 如何配置主机要求启动的 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service accounts, granting privileges [SSO]
- host initiated SSO, configuring
- domain function level [SSO]
- host initiated SSO, Transaction Integrator (TI)
- SPN [SSO]
- managing [SSO], granting TCB privileges
- Transaction Integrator (TI)
- host initiated SSO, SPN
- host initiated SSO, TCB privileges
- configuring, host initiated SSO
- creating, SPNs [SSO]
- TCB privileges [SSO]
- managing [SSO], host initiated
- host initiated SSO, domain function level
- service accounts, SSO
- SSO, host initiated
- managing [SSO], creating SPNs
- SSO, service accounts
ms.assetid: 91d77c9f-bab2-4f6e-8bce-e31c59cebb20
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 829deaba6782cb6e72f004c4fa96a6f8e2831be4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982822"
---
# <a name="how-to-configure-requirements-for-host-initiated-sso"></a><span data-ttu-id="2fff9-102">如何配置主机启动的 SSO 的要求</span><span class="sxs-lookup"><span data-stu-id="2fff9-102">How to Configure Requirements for Host Initiated SSO</span></span>
<span data-ttu-id="2fff9-103">尽管企业 SSO 和主机启动的 SSO 在某些方面有相同之处，但对于主机启动的 SSO，某些平台和 Active Directory 要求是其所独有的。</span><span class="sxs-lookup"><span data-stu-id="2fff9-103">Although Enterprise SSO and host initiated SSO have certain aspects in common, certain platform and Active Directory requirements are unique to host initiated SSO.</span></span> <span data-ttu-id="2fff9-104">本主题将介绍这些要求，并列出在系统中检查或创建这些要求所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="2fff9-104">This topic discusses those requirements, and lists the steps to check or create them on your system.</span></span>  
  
- <span data-ttu-id="2fff9-105">主机启动的 SSO 只能在本地 Windows Server 2008 域环境中执行。</span><span class="sxs-lookup"><span data-stu-id="2fff9-105">Host initiated SSO can be executed only on a native Windows Server 2008 domain environment.</span></span>  
  
- <span data-ttu-id="2fff9-106">必须将执行主机启动的 SSO 的 SSO 服务帐户配置为具有 TCB 权限。</span><span class="sxs-lookup"><span data-stu-id="2fff9-106">The service account for SSO Service that is performing host initiated SSO must be configured to have TCB privileges.</span></span> <span data-ttu-id="2fff9-107">（可在域安全策略中为服务帐户配置此权限。）</span><span class="sxs-lookup"><span data-stu-id="2fff9-107">(You can configure this for the service account in the domain security policy.)</span></span>  
  
  <span data-ttu-id="2fff9-108">此外，在对主机启动的处理使用事务集成器时，必须满足某些要求。</span><span class="sxs-lookup"><span data-stu-id="2fff9-108">In addition, certain requirements are necessary when using Transaction Integrator for Host Initiated Processing.</span></span> <span data-ttu-id="2fff9-109">HIP 的 TI 利用主机启动的 SSO 为非 Windows 用户实现单一登录。</span><span class="sxs-lookup"><span data-stu-id="2fff9-109">TI for HIP leverages host initiated SSO to achieve Single Sign-On for non-Windows users.</span></span>  
  
  <span data-ttu-id="2fff9-110">例如，HIP 服务的 TI 的服务帐户在服务帐户 domainname\hipsvc 下运行。</span><span class="sxs-lookup"><span data-stu-id="2fff9-110">For example, service account for TI for HIP service runs under a service account domainname\hipsvc.</span></span> <span data-ttu-id="2fff9-111">此服务可承载要使用与非 Windows 帐户对应的 Windows 帐户访问 Windows 中远程或本地资源的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2fff9-111">This service can host applications that want to access remote or local resources on Windows with the Windows account that correspond to the non-Windows account.</span></span>  
  
  <span data-ttu-id="2fff9-112">domainname\hipsvc 帐户必须属于用于单一登录的关联应用程序的 Application Administrator 组帐户。</span><span class="sxs-lookup"><span data-stu-id="2fff9-112">The domainname\hipsvc account must belong to the Application Administrator group account for the Affiliate Application that is being used for Single Sign-On.</span></span>  
  
  <span data-ttu-id="2fff9-113">domainname\hipsvc 帐户必须具有约束委托权限才能使用主机启动的单一登录。</span><span class="sxs-lookup"><span data-stu-id="2fff9-113">The domainname\hipsvc account must have constrained delegation privileges to use host initiated Single Sign-On.</span></span> <span data-ttu-id="2fff9-114">此权限可由 Active Directory 中的域管理员进行配置。</span><span class="sxs-lookup"><span data-stu-id="2fff9-114">This can be configured by the domain administrator in Active Directory.</span></span> <span data-ttu-id="2fff9-115">可以为已注册 SPN 的帐户配置委托。</span><span class="sxs-lookup"><span data-stu-id="2fff9-115">Delegation can be configured for accounts that have registered SPNs.</span></span> <span data-ttu-id="2fff9-116">使用约束委托，服务帐户可以只访问管理员指定的组件。</span><span class="sxs-lookup"><span data-stu-id="2fff9-116">Constrained delegation allows the service account to access only components that are specified by the administrator.</span></span>  
  
### <a name="to-check-your-domain-function-level"></a><span data-ttu-id="2fff9-117">检查域功能级别</span><span class="sxs-lookup"><span data-stu-id="2fff9-117">To check your domain function level</span></span>  
  
1.  <span data-ttu-id="2fff9-118">在你**Active Directory 域和信任关系**MMC 管理单元中，右单击的节点**Active Directory 域和信任关系**，然后单击**提升林功能级别**。</span><span class="sxs-lookup"><span data-stu-id="2fff9-118">In your **Active Directory Domains and Trusts** MMC snap-in, right click the node **Active Directory Domains and Trusts**, and then click **Raise Forest Functional Level**.</span></span>  
  
2.  <span data-ttu-id="2fff9-119">验证功能级别是否**Windows Server 2008**。</span><span class="sxs-lookup"><span data-stu-id="2fff9-119">Verify that the functional level is **Windows Server 2008**.</span></span> <span data-ttu-id="2fff9-120">如果不是，请参阅 Active Directory 文档，然后尝试更改该设置。</span><span class="sxs-lookup"><span data-stu-id="2fff9-120">If it is not, refer to your Active Directory documentation before you attempt to change the setting.</span></span>  
  
### <a name="to-create-an-spn"></a><span data-ttu-id="2fff9-121">若要创建 SPN</span><span class="sxs-lookup"><span data-stu-id="2fff9-121">To create an SPN</span></span>  
  
1. <span data-ttu-id="2fff9-122">下载**setspn**实用程序从以下位置： [ http://go.microsoft.com/fwlink/?LinkId=33178 ](http://go.microsoft.com/fwlink/?LinkId=33178)。</span><span class="sxs-lookup"><span data-stu-id="2fff9-122">Download the **setspn** utility from the following location: [http://go.microsoft.com/fwlink/?LinkId=33178](http://go.microsoft.com/fwlink/?LinkId=33178).</span></span>  
  
2. <span data-ttu-id="2fff9-123">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="2fff9-123">On the **Start** menu, click **Run**.</span></span>  
  
3. <span data-ttu-id="2fff9-124">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2fff9-124">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="2fff9-125">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="2fff9-125">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2fff9-126">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="2fff9-126">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
5. <span data-ttu-id="2fff9-127">类型**setpsn-a hipsvc\computername.domain.com domain\hissvc**</span><span class="sxs-lookup"><span data-stu-id="2fff9-127">Type **setpsn -a hipsvc\computername.domain.com domain\hissvc**</span></span>  
  
    <span data-ttu-id="2fff9-128">其中**hipsvc\computername.domain.com**是将执行该操作和，运行的计算机的服务和**domain\hissvc**是 hipsvc 的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="2fff9-128">where **hipsvc\computername.domain.com** is the service that will perform the operation and the computer it is running on, and **domain\hissvc** is the service account for hipsvc.</span></span>  
  
   <span data-ttu-id="2fff9-129">在执行此操作后，可以在 Active Directory 中为此服务帐户 (domain\hissvc) 配置约束委托以访问网络中的相应资源。</span><span class="sxs-lookup"><span data-stu-id="2fff9-129">After doing this, you can configure constrained delegation in Active Directory for this service account (domain\hissvc) to access the appropriate resource in the network.</span></span>  
  
#### <a name="to-give-tcb-privileges-for-the-sso-service-account"></a><span data-ttu-id="2fff9-130">为 SSO 服务帐户授予 TCB 权限</span><span class="sxs-lookup"><span data-stu-id="2fff9-130">To give TCB privileges for the SSO service account</span></span>  
  
-   <span data-ttu-id="2fff9-131">在你**域安全策略-本地策略-用户权限分配**，将 SSO 服务帐户添加到**充当操作系统的一部分**策略。</span><span class="sxs-lookup"><span data-stu-id="2fff9-131">Under your **Domain Security Policy - Local Policies - User Rights Assignment**, add the SSO Service account to the **Act as part of operating system** policy.</span></span>  
  
     <span data-ttu-id="2fff9-132">有关 Kerberos 协议转换和约束委派的详细信息，请转到[ http://go.microsoft.com/fwlink/?LinkId=195484 ](http://go.microsoft.com/fwlink/?LinkId=195484)。</span><span class="sxs-lookup"><span data-stu-id="2fff9-132">For more information about Kerberos Protocol Transition and Constrained Delegation, go to [http://go.microsoft.com/fwlink/?LinkId=195484](http://go.microsoft.com/fwlink/?LinkId=195484).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fff9-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fff9-133">See Also</span></span>  
 [<span data-ttu-id="2fff9-134">主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="2fff9-134">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)