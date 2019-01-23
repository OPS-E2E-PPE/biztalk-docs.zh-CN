---
title: 配置 SSO 票证 |Microsoft Docs
description: 使用 SSO 管理或命令行来允许和验证企业单一登录票证系统级别和 BizTalk Server 中的关联应用程序。
ms.custom: ''
ms.date: 01/08/2019
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
ms.openlocfilehash: f3ce6c1de1a94225f06d09b66cc3e6c60c471f24
ms.sourcegitcommit: 2d39bcd10a22c5945d97a03988ccdc62f6fb3c93
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2019
ms.locfileid: "54443370"
---
# <a name="configure-the-sso-tickets-in-biztalk-server"></a><span data-ttu-id="f03f2-103">在 BizTalk Server 中配置 SSO 票证</span><span class="sxs-lookup"><span data-stu-id="f03f2-103">Configure the SSO Tickets in BizTalk Server</span></span>
<span data-ttu-id="f03f2-104">整个单一登录系统，可以使用企业单一登录 (SSO) 管理 MMC 或命令行对票证行为进行控制。</span><span class="sxs-lookup"><span data-stu-id="f03f2-104">You can use Enterprise Single Sign-On (SSO) Administration MMC or the command line to control ticket behavior for the entire single sign-on system.</span></span> <span data-ttu-id="f03f2-105">使用此工具，可以允许使用票证，并验证 SSO 票证。</span><span class="sxs-lookup"><span data-stu-id="f03f2-105">Using this tools, you can allow tickets and validate SSO tickets.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="f03f2-106">开始之前</span><span class="sxs-lookup"><span data-stu-id="f03f2-106">Before you begin</span></span>

- <span data-ttu-id="f03f2-107">如果在远程计算机上安装 SSO 管理，则可以运行远程[IssueTicket](https://docs.microsoft.com/biztalk/core/technical-reference/issoticket-issueticket-method)操作。</span><span class="sxs-lookup"><span data-stu-id="f03f2-107">If SSO Administration is installed on a remote computer, you can run a remote [IssueTicket](https://docs.microsoft.com/biztalk/core/technical-reference/issoticket-issueticket-method) operation.</span></span> <span data-ttu-id="f03f2-108">SSO 管理模块和运行时模块 （ENTSSO 服务） 之间的所有通信进行都加密。</span><span class="sxs-lookup"><span data-stu-id="f03f2-108">All traffic between the SSO Administration module and the Runtime module (ENTSSO service) is encrypted.</span></span>  
  
- <span data-ttu-id="f03f2-109">使用 ssomanage.exe 命令行实用工具，可以输入在关联应用程序级别的票证超时值。</span><span class="sxs-lookup"><span data-stu-id="f03f2-109">Using the ssomanage.exe command line utility, you can enter the ticket timeout at the Affiliate Application level.</span></span> <span data-ttu-id="f03f2-110">仅当创建的应用程序时不进行应用程序的更新时，才可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f03f2-110">You can do this only when an update of the application is made, not when the application is created.</span></span>
  
- <span data-ttu-id="f03f2-111">只有 SSO 管理员组中的用户可以在 SSO 系统级别和关联应用程序级别配置票证。</span><span class="sxs-lookup"><span data-stu-id="f03f2-111">Only users in the SSO Administrator group can configure tickets at the SSO system-level and at the Affiliate Application level.</span></span>  
  
- <span data-ttu-id="f03f2-112">如果在系统级别禁用了票证，它不能在关联应用程序级别使用它。</span><span class="sxs-lookup"><span data-stu-id="f03f2-112">If ticketing is disabled at the system-level, it can't be used at the Affiliate Application level.</span></span> <span data-ttu-id="f03f2-113">就可以启用系统级别票证和关联应用程序级别禁用它们。</span><span class="sxs-lookup"><span data-stu-id="f03f2-113">It's possible to enable tickets at the system level, and disable them at the Affiliate Application level.</span></span>  
  
- <span data-ttu-id="f03f2-114">如果在系统级别启用验证，则必须在关联应用程序级别验证票证。</span><span class="sxs-lookup"><span data-stu-id="f03f2-114">If validation is enabled at the system-level, tickets must be validated at the Affiliate Application level.</span></span> <span data-ttu-id="f03f2-115">它是可以禁用在系统级别的验证并启用关联应用程序级别。</span><span class="sxs-lookup"><span data-stu-id="f03f2-115">It's possible to disable validation at the system-level, and enable it at the Affiliate Application level.</span></span>  
  
- <span data-ttu-id="f03f2-116">如果在系统级别和关联应用程序级别输入票证超时，则在关联应用程序级别输入确定票证到期时间。</span><span class="sxs-lookup"><span data-stu-id="f03f2-116">If ticket timeout is entered at the system-level and the Affiliate Application level, the one entered at the Affiliate Application level determines the ticket expiration time.</span></span>  
  
<span data-ttu-id="f03f2-117">有关票证和票证验证的详细信息，请参阅[SSO 票证](../core/sso-tickets.md)。</span><span class="sxs-lookup"><span data-stu-id="f03f2-117">For more information about tickets and tickets validation, see [SSO Tickets](../core/sso-tickets.md).</span></span>  
  
## <a name="allow-affiliate-application-tickets-using-sso-administration"></a><span data-ttu-id="f03f2-118">允许使用 SSO 管理关联应用程序票证</span><span class="sxs-lookup"><span data-stu-id="f03f2-118">Allow Affiliate Application tickets using SSO Administration</span></span>  
  
1.  <span data-ttu-id="f03f2-119">从**启动**菜单中，选择**所有程序** > **Microsoft 企业单一登录** > **SSO 管理**.</span><span class="sxs-lookup"><span data-stu-id="f03f2-119">From the **Start** menu, select **All Programs** > **Microsoft Enterprise Single Sign-On** > **SSO Administration**.</span></span>
  
2.  <span data-ttu-id="f03f2-120">中的 ENTSSO Mmc 管理单元的作用域窗格中，展开**关联应用程序**节点。</span><span class="sxs-lookup"><span data-stu-id="f03f2-120">In the scope pane of the ENTSSO MMC Snap-In, expand the **Affiliate Applications** node.</span></span>  
  
3.  <span data-ttu-id="f03f2-121">右键单击**关联应用程序** > **属性**。</span><span class="sxs-lookup"><span data-stu-id="f03f2-121">Right-click **Affiliate Application** > **Properties**.</span></span>  
  
4.  <span data-ttu-id="f03f2-122">选择**选项**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f03f2-122">Choose the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="f03f2-123">选择**允许使用票证**并输入所需的票证超时值。</span><span class="sxs-lookup"><span data-stu-id="f03f2-123">Select **Allow Tickets** and enter the ticket timeout you want.</span></span>  
  
## <a name="allow-and-validate-sso-system-level-tickets-using-the-command-line"></a><span data-ttu-id="f03f2-124">允许并验证 SSO 系统级别票证使用命令行</span><span class="sxs-lookup"><span data-stu-id="f03f2-124">Allow and validate SSO system-level tickets using the command line</span></span>  
  
1. <span data-ttu-id="f03f2-125">打开命令提示符 (开始菜单 > 类型**命令提示符**> 选择**命令提示符下**)。</span><span class="sxs-lookup"><span data-stu-id="f03f2-125">Open a command prompt (Start menu > type **command prompt** > select **Command Prompt**).</span></span>

    > [!TIP]
    >  <span data-ttu-id="f03f2-126">在系统上支持用户帐户控制 (UAC)，您可能需要使用管理权限打开命令提示符 (右键单击**命令提示符下**> \* \* 以管理员身份运行)。</span><span class="sxs-lookup"><span data-stu-id="f03f2-126">On a system that supports User Account Control (UAC), you may need to open the command prompt with Administrative privileges (right-click **Command Prompt** > \*\*Run as administrator).</span></span>
  
2. <span data-ttu-id="f03f2-127">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="f03f2-127">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="f03f2-128">默认安装目录是`\Program Files\Common Files\Enterprise Single Sign-On`。</span><span class="sxs-lookup"><span data-stu-id="f03f2-128">The default installation directory is `\Program Files\Common Files\Enterprise Single Sign-On`.</span></span> <span data-ttu-id="f03f2-129">例如，输入：</span><span class="sxs-lookup"><span data-stu-id="f03f2-129">For example, enter:</span></span> 

    `cd C:\Program Files\Common Files\Enterprise Single Sign-On`
  
3. <span data-ttu-id="f03f2-130">类型`ssomanage -tickets <allowed yes/no> <validate yes/no>`，其中*\<允许是/否\>* 指示对于票证是否允许或不是，和*\<验证是/否\>* 指示是否需要进行验证后他们正在兑换票证。</span><span class="sxs-lookup"><span data-stu-id="f03f2-130">Type `ssomanage -tickets <allowed yes/no> <validate yes/no>`, where *\<allowed yes/no\>* indicates whether tickets are allowed or not, and *\<validate yes/no\>* indicates whether tickets need to be validated after they're redeemed.</span></span>  
  
    <span data-ttu-id="f03f2-131">可以使用`yes`， `no`， `on`，或`off`允许和/或验证票证。</span><span class="sxs-lookup"><span data-stu-id="f03f2-131">You can use `yes`, `no`, `on`, or `off` to allow and/or validate tickets.</span></span> <span data-ttu-id="f03f2-132">这些词不区分大小写，必须在任何语言设置下都能使用。</span><span class="sxs-lookup"><span data-stu-id="f03f2-132">These words are case independent, and must be used regardless of your language settings.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f03f2-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="f03f2-133">See Also</span></span>

<span data-ttu-id="f03f2-134">[了解 SSO](../core/understanding-sso.md) </span><span class="sxs-lookup"><span data-stu-id="f03f2-134">[Understanding SSO](../core/understanding-sso.md) </span></span>  
[<span data-ttu-id="f03f2-135">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="f03f2-135">Using SSO</span></span>](../core/using-sso.md)
