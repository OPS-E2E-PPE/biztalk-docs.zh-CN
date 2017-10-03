---
title: "如何配置 SSO 票证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO], configuring tickets
- SSO, tickets
- tickets [SSO], configuring
ms.assetid: 32f0384b-ac79-4cce-b3f5-f4f8a73a673a
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef78c47c3da88945573a70e85580c90e05b1d225
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-sso-tickets"></a><span data-ttu-id="27f88-102">如何配置 SSO 票证</span><span class="sxs-lookup"><span data-stu-id="27f88-102">How to Configure the SSO Tickets</span></span>
<span data-ttu-id="27f88-103">可使用 MMC 管理单元或命令行对整个单一登录系统的票证行为进行控制，包括是否允许使用票证、系统是否必须验证票证。</span><span class="sxs-lookup"><span data-stu-id="27f88-103">You can use the MMC Snap-In or the command line to control ticket behavior for the entire Single Sign-On system, including whether to allow tickets, and whether the system must validate the tickets.</span></span>  
  
 <span data-ttu-id="27f88-104">你可以使用是，否，打开或关闭以指示是否允许和/或验证票证。</span><span class="sxs-lookup"><span data-stu-id="27f88-104">You can use Yes, No, On, or Off to indicate whether to allow and/or validate tickets.</span></span> <span data-ttu-id="27f88-105">这些词不区分大小写，必须在任何语言设置下都能使用。</span><span class="sxs-lookup"><span data-stu-id="27f88-105">These words are case independent, and must be used regardless of your language settings.</span></span>  
  
 <span data-ttu-id="27f88-106">如果 SSO 管理功能安装在远程计算机上，则可执行远程 IssueTicket 操作。</span><span class="sxs-lookup"><span data-stu-id="27f88-106">If you have the SSO Administration feature installed on a remote computer, remote IssueTicket operation can be performed.</span></span> <span data-ttu-id="27f88-107">请注意，SSO 管理模块和运行时模块（ENTSSO 服务）之间的所有通信都是加密的。</span><span class="sxs-lookup"><span data-stu-id="27f88-107">Note that all traffic between the SSO Administration module and the Runtime module (ENTSSO service) is encrypted.</span></span>  
  
 <span data-ttu-id="27f88-108">仅当执行应用程序更新时（而非创建时），才能使用命令行实用工具 ssomanage.exe 在关联应用程序级别上指定票证超时。</span><span class="sxs-lookup"><span data-stu-id="27f88-108">Using the command line utility, ssomanage.exe, you can specify the ticket timeout at the Affiliate Application level only when an update of the Application is performed,  not at creation time.</span></span>  
  
 <span data-ttu-id="27f88-109">只有 SSO 管理员可以配置票证，SSO 系统级别和 Affiliate 应用程序级别。</span><span class="sxs-lookup"><span data-stu-id="27f88-109">Only an SSO Administrator can configure tickets at the SSO System level and at the Affiliate Application level.</span></span>  
  
 <span data-ttu-id="27f88-110">如果在系统级别上禁用了票证，则也不能在关联应用程序级别上使用票证。</span><span class="sxs-lookup"><span data-stu-id="27f88-110">If ticketing is disabled at the system level, it cannot be used at the Affiliate Application level either.</span></span> <span data-ttu-id="27f88-111">它可启用在系统级别的票证和 Affiliate 应用程序级别禁用它。</span><span class="sxs-lookup"><span data-stu-id="27f88-111">It is possible to enable tickets at the system level and disable it at the Affiliate Application level.</span></span>  
  
 <span data-ttu-id="27f88-112">如果在系统级别上启用验证，则在关联应用程序级别上也需要票证验证。</span><span class="sxs-lookup"><span data-stu-id="27f88-112">If validation is enabled at the system level, validation of tickets are required at the Affiliate Application level as well.</span></span> <span data-ttu-id="27f88-113">但是，可以在系统级别上禁用验证，而在关联应用程序级别上启用验证。</span><span class="sxs-lookup"><span data-stu-id="27f88-113">It is possible to disable validation at the system level and enable it at the Affiliate Application level.</span></span>  
  
 <span data-ttu-id="27f88-114">如果在系统级别和关联应用程序级别同时指定了票证超时，则使用在关联应用程序级别上指定的票证超时确定票证过期时间。</span><span class="sxs-lookup"><span data-stu-id="27f88-114">If Ticket timeout is specified both at the System level and the Affiliate Application level, the one specified at the Affiliate Application level is used to determine the ticket expiry time.</span></span>  
  
 <span data-ttu-id="27f88-115">有关票证和票证验证的详细信息，请参阅[SSO 票证](../core/sso-tickets.md)。</span><span class="sxs-lookup"><span data-stu-id="27f88-115">For more information about tickets and tickets validation, see [SSO Tickets](../core/sso-tickets.md).</span></span>  
  
### <a name="to-configure-the-enterprise-single-sign-on-tickets-using-the-mmc-snap-in-for-the-affiliate-application"></a><span data-ttu-id="27f88-116">使用 MMC 管理单元为关联应用程序配置企业单一登录票证</span><span class="sxs-lookup"><span data-stu-id="27f88-116">To configure the Enterprise Single Sign-On tickets using the MMC Snap-In for the Affiliate Application</span></span>  
  
1.  <span data-ttu-id="27f88-117">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="27f88-117">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="27f88-118">在的 ENTSSO MMC 管理单元中的作用域窗格中，展开**Affiliate 应用程序**节点。</span><span class="sxs-lookup"><span data-stu-id="27f88-118">In the scope pane of the ENTSSO MMC Snap-In, expand the **Affiliate Applications** node.</span></span>  
  
3.  <span data-ttu-id="27f88-119">右键单击**Affiliate 应用程序**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="27f88-119">Right-click **Affiliate Application**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="27f88-120">单击**选项**选项卡。</span><span class="sxs-lookup"><span data-stu-id="27f88-120">Click the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="27f88-121">选择**允许票证**并适当地配置的票证超时值。</span><span class="sxs-lookup"><span data-stu-id="27f88-121">Select **Allow Tickets** and configure the ticket timeout as appropriate.</span></span>  
  
### <a name="to-configure-the-enterprise-single-sign-on-system-level-tickets-using-the-command-line"></a><span data-ttu-id="27f88-122">使用命令行配置企业单一登录系统级别票证</span><span class="sxs-lookup"><span data-stu-id="27f88-122">To configure the Enterprise Single Sign-On system-level tickets using the command line</span></span>  
  
1.  <span data-ttu-id="27f88-123">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="27f88-123">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="27f88-124">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="27f88-124">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="27f88-125">默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="27f88-125">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="27f88-126">类型**ssomanage-票证\<允许是/否 > *\<验证是/否 >***，其中*\<允许是/否 >*指示或不是，是否将允许票证和*\<验证是/否 >*指示票证是否将需要进行验证后它们兑换。</span><span class="sxs-lookup"><span data-stu-id="27f88-126">Type **ssomanage –tickets \<allowed yes/no> *\<validate yes/no>***, where *\<allowed yes/no>* indicates whether tickets will be allowed or not, and *\<validate yes/no>* indicates whether tickets will need to be validated after they are redeemed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27f88-127">可使用 Yes、No、On 或 Off 指示是否允许使用和/或验证票证。</span><span class="sxs-lookup"><span data-stu-id="27f88-127">You can use yes, no, on, or off to indicate whether to allow and/or validate tickets.</span></span> <span data-ttu-id="27f88-128">这些词不区分大小写，必须在任何语言设置下都能使用。</span><span class="sxs-lookup"><span data-stu-id="27f88-128">These words are case independent, and must be used regardless of your language settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27f88-129">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="27f88-129">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27f88-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27f88-130">See Also</span></span>  
 <span data-ttu-id="27f88-131">[了解 SSO](../core/understanding-sso.md) </span><span class="sxs-lookup"><span data-stu-id="27f88-131">[Understanding SSO](../core/understanding-sso.md) </span></span>  
 [<span data-ttu-id="27f88-132">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="27f88-132">Using SSO</span></span>](../core/using-sso.md)