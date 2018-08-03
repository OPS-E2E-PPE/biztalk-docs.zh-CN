---
title: 如何配置 SSO 票证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], configuring tickets
- SSO, tickets
- tickets [SSO], configuring
ms.assetid: 32f0384b-ac79-4cce-b3f5-f4f8a73a673a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edec81ab1fa64ce7b4523771bb2c69b39c00bdfd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018755"
---
# <a name="how-to-configure-the-sso-tickets"></a><span data-ttu-id="211f1-102">如何配置 SSO 票证</span><span class="sxs-lookup"><span data-stu-id="211f1-102">How to Configure the SSO Tickets</span></span>
<span data-ttu-id="211f1-103">可使用 MMC 管理单元或命令行对整个单一登录系统的票证行为进行控制，包括是否允许使用票证、系统是否必须验证票证。</span><span class="sxs-lookup"><span data-stu-id="211f1-103">You can use the MMC Snap-In or the command line to control ticket behavior for the entire Single Sign-On system, including whether to allow tickets, and whether the system must validate the tickets.</span></span>  
  
 <span data-ttu-id="211f1-104">可用于 Yes、 No、 On 或 Off 指示是否允许和/或验证票证。</span><span class="sxs-lookup"><span data-stu-id="211f1-104">You can use Yes, No, On, or Off to indicate whether to allow and/or validate tickets.</span></span> <span data-ttu-id="211f1-105">这些词不区分大小写，必须在任何语言设置下都能使用。</span><span class="sxs-lookup"><span data-stu-id="211f1-105">These words are case independent, and must be used regardless of your language settings.</span></span>  
  
 <span data-ttu-id="211f1-106">如果 SSO 管理功能安装在远程计算机上，则可执行远程 IssueTicket 操作。</span><span class="sxs-lookup"><span data-stu-id="211f1-106">If you have the SSO Administration feature installed on a remote computer, remote IssueTicket operation can be performed.</span></span> <span data-ttu-id="211f1-107">请注意，SSO 管理模块和运行时模块（ENTSSO 服务）之间的所有通信都是加密的。</span><span class="sxs-lookup"><span data-stu-id="211f1-107">Note that all traffic between the SSO Administration module and the Runtime module (ENTSSO service) is encrypted.</span></span>  
  
 <span data-ttu-id="211f1-108">仅当执行应用程序更新时（而非创建时），才能使用命令行实用工具 ssomanage.exe 在关联应用程序级别上指定票证超时。</span><span class="sxs-lookup"><span data-stu-id="211f1-108">Using the command line utility, ssomanage.exe, you can specify the ticket timeout at the Affiliate Application level only when an update of the Application is performed,  not at creation time.</span></span>  
  
 <span data-ttu-id="211f1-109">只有 SSO 管理员可以在 SSO 系统级别和关联应用程序级别配置票证。</span><span class="sxs-lookup"><span data-stu-id="211f1-109">Only an SSO Administrator can configure tickets at the SSO System level and at the Affiliate Application level.</span></span>  
  
 <span data-ttu-id="211f1-110">如果在系统级别上禁用了票证，则也不能在关联应用程序级别上使用票证。</span><span class="sxs-lookup"><span data-stu-id="211f1-110">If ticketing is disabled at the system level, it cannot be used at the Affiliate Application level either.</span></span> <span data-ttu-id="211f1-111">就可以启用在系统级别票证和关联应用程序级别禁用它。</span><span class="sxs-lookup"><span data-stu-id="211f1-111">It is possible to enable tickets at the system level and disable it at the Affiliate Application level.</span></span>  
  
 <span data-ttu-id="211f1-112">如果在系统级别上启用验证，则在关联应用程序级别上也需要票证验证。</span><span class="sxs-lookup"><span data-stu-id="211f1-112">If validation is enabled at the system level, validation of tickets are required at the Affiliate Application level as well.</span></span> <span data-ttu-id="211f1-113">但是，可以在系统级别上禁用验证，而在关联应用程序级别上启用验证。</span><span class="sxs-lookup"><span data-stu-id="211f1-113">It is possible to disable validation at the system level and enable it at the Affiliate Application level.</span></span>  
  
 <span data-ttu-id="211f1-114">如果在系统级别和关联应用程序级别同时指定了票证超时，则使用在关联应用程序级别上指定的票证超时确定票证过期时间。</span><span class="sxs-lookup"><span data-stu-id="211f1-114">If Ticket timeout is specified both at the System level and the Affiliate Application level, the one specified at the Affiliate Application level is used to determine the ticket expiry time.</span></span>  
  
 <span data-ttu-id="211f1-115">有关票证和票证验证的详细信息，请参阅[SSO 票证](../core/sso-tickets.md)。</span><span class="sxs-lookup"><span data-stu-id="211f1-115">For more information about tickets and tickets validation, see [SSO Tickets](../core/sso-tickets.md).</span></span>  
  
### <a name="to-configure-the-enterprise-single-sign-on-tickets-using-the-mmc-snap-in-for-the-affiliate-application"></a><span data-ttu-id="211f1-116">使用 MMC 管理单元为关联应用程序配置企业单一登录票证</span><span class="sxs-lookup"><span data-stu-id="211f1-116">To configure the Enterprise Single Sign-On tickets using the MMC Snap-In for the Affiliate Application</span></span>  
  
1.  <span data-ttu-id="211f1-117">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="211f1-117">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="211f1-118">中的 ENTSSO Mmc 管理单元的作用域窗格中，展开**关联应用程序**节点。</span><span class="sxs-lookup"><span data-stu-id="211f1-118">In the scope pane of the ENTSSO MMC Snap-In, expand the **Affiliate Applications** node.</span></span>  
  
3.  <span data-ttu-id="211f1-119">右键单击**关联应用程序**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="211f1-119">Right-click **Affiliate Application**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="211f1-120">单击**选项**选项卡。</span><span class="sxs-lookup"><span data-stu-id="211f1-120">Click the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="211f1-121">选择**允许使用票证**并根据需要配置票证超时。</span><span class="sxs-lookup"><span data-stu-id="211f1-121">Select **Allow Tickets** and configure the ticket timeout as appropriate.</span></span>  
  
### <a name="to-configure-the-enterprise-single-sign-on-system-level-tickets-using-the-command-line"></a><span data-ttu-id="211f1-122">使用命令行配置企业单一登录系统级别票证</span><span class="sxs-lookup"><span data-stu-id="211f1-122">To configure the Enterprise Single Sign-On system-level tickets using the command line</span></span>  
  
1. <span data-ttu-id="211f1-123">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="211f1-123">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="211f1-124">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="211f1-124">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="211f1-125">默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="211f1-125">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="211f1-126">类型 * * ssomanage-tickets\<允许是/否\> *\<验证是/否\>**<em>，其中 *\<允许是/否\></em>指示是否允许使用票证，并*\<验证是/否\>* 指示是否将需要票证兑换后是否要验证。</span><span class="sxs-lookup"><span data-stu-id="211f1-126">Type **ssomanage –tickets \<allowed yes/no\> *\<validate yes/no\>**<em>, where *\<allowed yes/no\></em> indicates whether tickets will be allowed or not, and *\<validate yes/no\>* indicates whether tickets will need to be validated after they are redeemed.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="211f1-127">可使用 Yes、No、On 或 Off 指示是否允许使用和/或验证票证。</span><span class="sxs-lookup"><span data-stu-id="211f1-127">You can use yes, no, on, or off to indicate whether to allow and/or validate tickets.</span></span> <span data-ttu-id="211f1-128">这些词不区分大小写，必须在任何语言设置下都能使用。</span><span class="sxs-lookup"><span data-stu-id="211f1-128">These words are case independent, and must be used regardless of your language settings.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="211f1-129">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="211f1-129">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="211f1-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="211f1-130">See Also</span></span>  
 <span data-ttu-id="211f1-131">[了解 SSO](../core/understanding-sso.md) </span><span class="sxs-lookup"><span data-stu-id="211f1-131">[Understanding SSO](../core/understanding-sso.md) </span></span>  
 [<span data-ttu-id="211f1-132">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="211f1-132">Using SSO</span></span>](../core/using-sso.md)