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
ms.openlocfilehash: 7f3319c0d8157ebe0c71c36a2494b3bda641181c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341224"
---
# <a name="how-to-configure-requirements-for-host-initiated-sso"></a><span data-ttu-id="99367-102">如何配置主机要求启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="99367-102">How to Configure Requirements for Host Initiated SSO</span></span>
<span data-ttu-id="99367-103">尽管企业 SSO 和主机启动的 SSO 的共同点某些方面，某些平台和 Active Directory 要求是唯一的以主机启动的 SSO。</span><span class="sxs-lookup"><span data-stu-id="99367-103">Although Enterprise SSO and host initiated SSO have certain aspects in common, certain platform and Active Directory requirements are unique to host initiated SSO.</span></span> <span data-ttu-id="99367-104">本主题讨论了这些要求，并列出了检查或创建这些系统上的步骤。</span><span class="sxs-lookup"><span data-stu-id="99367-104">This topic discusses those requirements, and lists the steps to check or create them on your system.</span></span>  
  
- <span data-ttu-id="99367-105">主机启动的 SSO 可仅在本机的 Windows Server 2008 域环境执行。</span><span class="sxs-lookup"><span data-stu-id="99367-105">Host initiated SSO can be executed only on a native Windows Server 2008 domain environment.</span></span>  
  
- <span data-ttu-id="99367-106">将执行主机的 SSO 服务的服务帐户启动的 SSO 必须配置为具有 TCB 权限。</span><span class="sxs-lookup"><span data-stu-id="99367-106">The service account for SSO Service that is performing host initiated SSO must be configured to have TCB privileges.</span></span> <span data-ttu-id="99367-107">（你可以配置此域安全策略中的服务帐户。）</span><span class="sxs-lookup"><span data-stu-id="99367-107">(You can configure this for the service account in the domain security policy.)</span></span>  
  
  <span data-ttu-id="99367-108">此外，某些要求是必需的使用主机启动的处理的事务集成器时。</span><span class="sxs-lookup"><span data-stu-id="99367-108">In addition, certain requirements are necessary when using Transaction Integrator for Host Initiated Processing.</span></span> <span data-ttu-id="99367-109">TI 为 HIP 利用主机启动的 SSO 为非 Windows 用户实现单一登录。</span><span class="sxs-lookup"><span data-stu-id="99367-109">TI for HIP leverages host initiated SSO to achieve Single Sign-On for non-Windows users.</span></span>  
  
  <span data-ttu-id="99367-110">例如，HIP 服务的 TI 的服务帐户在服务帐户 domainname\hipsvc 下运行。</span><span class="sxs-lookup"><span data-stu-id="99367-110">For example, service account for TI for HIP service runs under a service account domainname\hipsvc.</span></span> <span data-ttu-id="99367-111">此服务可承载的应用程序想要访问远程或本地资源在 Windows 上使用 Windows 帐户对应的非 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="99367-111">This service can host applications that want to access remote or local resources on Windows with the Windows account that correspond to the non-Windows account.</span></span>  
  
  <span data-ttu-id="99367-112">Domainname\hipsvc 帐户必须属于正在使用单一登录关联应用程序的应用程序管理员组帐户。</span><span class="sxs-lookup"><span data-stu-id="99367-112">The domainname\hipsvc account must belong to the Application Administrator group account for the Affiliate Application that is being used for Single Sign-On.</span></span>  
  
  <span data-ttu-id="99367-113">Domainname\hipsvc 帐户必须具有约束委托权限才能使用主机启动的单一登录。</span><span class="sxs-lookup"><span data-stu-id="99367-113">The domainname\hipsvc account must have constrained delegation privileges to use host initiated Single Sign-On.</span></span> <span data-ttu-id="99367-114">这可以由域管理员在 Active Directory 中配置。</span><span class="sxs-lookup"><span data-stu-id="99367-114">This can be configured by the domain administrator in Active Directory.</span></span> <span data-ttu-id="99367-115">可以为已注册 Spn 的帐户配置委托。</span><span class="sxs-lookup"><span data-stu-id="99367-115">Delegation can be configured for accounts that have registered SPNs.</span></span> <span data-ttu-id="99367-116">约束的委派允许服务帐户来访问由管理员指定的组件。</span><span class="sxs-lookup"><span data-stu-id="99367-116">Constrained delegation allows the service account to access only components that are specified by the administrator.</span></span>  
  
### <a name="to-check-your-domain-function-level"></a><span data-ttu-id="99367-117">若要检查域功能级别</span><span class="sxs-lookup"><span data-stu-id="99367-117">To check your domain function level</span></span>  
  
1.  <span data-ttu-id="99367-118">在你**Active Directory 域和信任关系**MMC 管理单元中，右单击的节点**Active Directory 域和信任关系**，然后单击**提升林功能级别**。</span><span class="sxs-lookup"><span data-stu-id="99367-118">In your **Active Directory Domains and Trusts** MMC snap-in, right click the node **Active Directory Domains and Trusts**, and then click **Raise Forest Functional Level**.</span></span>  
  
2.  <span data-ttu-id="99367-119">验证功能级别是否**Windows Server 2008**。</span><span class="sxs-lookup"><span data-stu-id="99367-119">Verify that the functional level is **Windows Server 2008**.</span></span> <span data-ttu-id="99367-120">如果不存在，请参阅 Active Directory 文档，然后再尝试更改该设置。</span><span class="sxs-lookup"><span data-stu-id="99367-120">If it is not, refer to your Active Directory documentation before you attempt to change the setting.</span></span>  
  
### <a name="to-create-an-spn"></a><span data-ttu-id="99367-121">若要创建 SPN</span><span class="sxs-lookup"><span data-stu-id="99367-121">To create an SPN</span></span>  
  
1. <span data-ttu-id="99367-122">下载**setspn**实用程序从以下位置： [ http://go.microsoft.com/fwlink/?LinkId=33178 ](http://go.microsoft.com/fwlink/?LinkId=33178)。</span><span class="sxs-lookup"><span data-stu-id="99367-122">Download the **setspn** utility from the following location: [http://go.microsoft.com/fwlink/?LinkId=33178](http://go.microsoft.com/fwlink/?LinkId=33178).</span></span>  
  
2. <span data-ttu-id="99367-123">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="99367-123">On the **Start** menu, click **Run**.</span></span>  
  
3. <span data-ttu-id="99367-124">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="99367-124">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="99367-125">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="99367-125">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="99367-126">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="99367-126">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
5. <span data-ttu-id="99367-127">Type **setpsn -a hipsvc\computername.domain.com domain\hissvc**</span><span class="sxs-lookup"><span data-stu-id="99367-127">Type **setpsn -a hipsvc\computername.domain.com domain\hissvc**</span></span>  
  
    <span data-ttu-id="99367-128">其中**hipsvc\computername.domain.com**是将执行该操作和，运行的计算机的服务和**domain\hissvc**是 hipsvc 的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="99367-128">where **hipsvc\computername.domain.com** is the service that will perform the operation and the computer it is running on, and **domain\hissvc** is the service account for hipsvc.</span></span>  
  
   <span data-ttu-id="99367-129">完成后，可以在此服务帐户 (domain\hissvc) 来访问网络中的相应资源的 Active Directory 中配置约束的委派。</span><span class="sxs-lookup"><span data-stu-id="99367-129">After doing this, you can configure constrained delegation in Active Directory for this service account (domain\hissvc) to access the appropriate resource in the network.</span></span>  
  
#### <a name="to-give-tcb-privileges-for-the-sso-service-account"></a><span data-ttu-id="99367-130">SSO 服务帐户授予 TCB 权限</span><span class="sxs-lookup"><span data-stu-id="99367-130">To give TCB privileges for the SSO service account</span></span>  
  
-   <span data-ttu-id="99367-131">在你**域安全策略-本地策略-用户权限分配**，将 SSO 服务帐户添加到**充当操作系统的一部分**策略。</span><span class="sxs-lookup"><span data-stu-id="99367-131">Under your **Domain Security Policy - Local Policies - User Rights Assignment**, add the SSO Service account to the **Act as part of operating system** policy.</span></span>  
  
     <span data-ttu-id="99367-132">有关 Kerberos 协议转换和约束委派的详细信息，请转到[ http://go.microsoft.com/fwlink/?LinkId=195484 ](http://go.microsoft.com/fwlink/?LinkId=195484)。</span><span class="sxs-lookup"><span data-stu-id="99367-132">For more information about Kerberos Protocol Transition and Constrained Delegation, go to [http://go.microsoft.com/fwlink/?LinkId=195484](http://go.microsoft.com/fwlink/?LinkId=195484).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99367-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="99367-133">See Also</span></span>  
 [<span data-ttu-id="99367-134">主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="99367-134">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)