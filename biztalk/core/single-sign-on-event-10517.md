---
title: "单一登录： 事件 10517 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b63e4b0-0ef6-45c2-b8b1-55ac20e79e26
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2716eb7d331ec5c15070555a028c00310188856c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10517"></a><span data-ttu-id="650b5-102">单一登录： 事件 10517</span><span class="sxs-lookup"><span data-stu-id="650b5-102">Single Sign-On: Event 10517</span></span>
## <a name="details"></a><span data-ttu-id="650b5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="650b5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="650b5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="650b5-104">Product Name</span></span>|<span data-ttu-id="650b5-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="650b5-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="650b5-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="650b5-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="650b5-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="650b5-107">Event ID</span></span>|<span data-ttu-id="650b5-108">10517</span><span class="sxs-lookup"><span data-stu-id="650b5-108">10517</span></span>|  
|<span data-ttu-id="650b5-109">事件源</span><span class="sxs-lookup"><span data-stu-id="650b5-109">Event Source</span></span>|<span data-ttu-id="650b5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="650b5-110">ENTSSO</span></span>|  
|<span data-ttu-id="650b5-111">组件</span><span class="sxs-lookup"><span data-stu-id="650b5-111">Component</span></span>|<span data-ttu-id="650b5-112">N\A</span><span class="sxs-lookup"><span data-stu-id="650b5-112">N\A</span></span>|  
|<span data-ttu-id="650b5-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="650b5-113">Symbolic Name</span></span>|<span data-ttu-id="650b5-114">SSO_ERROR_BAD_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="650b5-114">SSO_ERROR_BAD_SSO_ADMIN</span></span>|  
|<span data-ttu-id="650b5-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="650b5-115">Message Text</span></span>|<span data-ttu-id="650b5-116">SSO 管理员帐户无效。</span><span class="sxs-lookup"><span data-stu-id="650b5-116">The SSO Administrators account is not valid.</span></span> <span data-ttu-id="650b5-117">如果是本地帐户，请检查服务器上是否存在此帐户。</span><span class="sxs-lookup"><span data-stu-id="650b5-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="650b5-118">如果是域帐户，请与域管理员联系。</span><span class="sxs-lookup"><span data-stu-id="650b5-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="650b5-119">当帐户有效时，启用 SSO。%r</span><span class="sxs-lookup"><span data-stu-id="650b5-119">Enable SSO when the account is valid.%r</span></span><br /><br /> <span data-ttu-id="650b5-120">SSO Administrators: %1 %r</span><span class="sxs-lookup"><span data-stu-id="650b5-120">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="650b5-121">无效帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="650b5-121">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="650b5-122">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="650b5-122">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="650b5-123">解释</span><span class="sxs-lookup"><span data-stu-id="650b5-123">Explanation</span></span>  
 <span data-ttu-id="650b5-124">此错误事件表示为企业单一登录指定的 SSO 管理员帐户不是有效的 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="650b5-124">This Error event indicates that the SSO Administrators account specified for Enterprise Single Sign-On is not a valid Windows account.</span></span> <span data-ttu-id="650b5-125">运行企业单一登录服务的服务帐户必须是此帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="650b5-125">The service account running the Enterprise Single Sign-On service must be a member of this account.</span></span> <span data-ttu-id="650b5-126">SSO 管理员帐户可以是 Windows 组帐户，也可以是单个帐户。</span><span class="sxs-lookup"><span data-stu-id="650b5-126">The SSO Administrators account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="650b5-127">SSO 管理员帐户可以是域组帐户，也可以是本地组帐户。</span><span class="sxs-lookup"><span data-stu-id="650b5-127">The SSO Administrators account can also be either a domain or local group account.</span></span> <span data-ttu-id="650b5-128">时使用个人帐户，不能为其他个人帐户更改此帐户。</span><span class="sxs-lookup"><span data-stu-id="650b5-128">When using an individual account, you cannot change this account to another individual account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="650b5-129">用户操作</span><span class="sxs-lookup"><span data-stu-id="650b5-129">User Action</span></span>  
 <span data-ttu-id="650b5-130">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="650b5-130">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="650b5-131">验证 SSO 管理员帐户是否存在。</span><span class="sxs-lookup"><span data-stu-id="650b5-131">Verify the SSO Administrators account exists.</span></span>  
  
 <span data-ttu-id="650b5-132">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="650b5-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="650b5-133">SSO 用户组</span><span class="sxs-lookup"><span data-stu-id="650b5-133">SSO User Groups</span></span>](../core/sso-user-groups.md)