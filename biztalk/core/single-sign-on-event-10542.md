---
title: 单一登录： 事件 10542 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8e12444-b47c-4919-85b6-85c8e33b8342
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ebcf97a9de014d0651c9f239c1ae6e846925f3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271173"
---
# <a name="single-sign-on-event-10542"></a><span data-ttu-id="99647-102">单一登录： 事件 10542</span><span class="sxs-lookup"><span data-stu-id="99647-102">Single Sign-On: Event 10542</span></span>
## <a name="details"></a><span data-ttu-id="99647-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="99647-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="99647-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="99647-104">Product Name</span></span>|<span data-ttu-id="99647-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="99647-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="99647-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="99647-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="99647-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="99647-107">Event ID</span></span>|<span data-ttu-id="99647-108">10542</span><span class="sxs-lookup"><span data-stu-id="99647-108">10542</span></span>|  
|<span data-ttu-id="99647-109">事件源</span><span class="sxs-lookup"><span data-stu-id="99647-109">Event Source</span></span>|<span data-ttu-id="99647-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="99647-110">ENTSSO</span></span>|  
|<span data-ttu-id="99647-111">组件</span><span class="sxs-lookup"><span data-stu-id="99647-111">Component</span></span>|<span data-ttu-id="99647-112">CO</span><span class="sxs-lookup"><span data-stu-id="99647-112">CO</span></span>|  
|<span data-ttu-id="99647-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="99647-113">Symbolic Name</span></span>|<span data-ttu-id="99647-114">SSO_WARN_APP_TICKETS_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="99647-114">SSO_WARN_APP_TICKETS_VALIDATED</span></span>|  
|<span data-ttu-id="99647-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="99647-115">Message Text</span></span>|<span data-ttu-id="99647-116">由于未经过验证，因此无法兑换此应用程序的票证。%r</span><span class="sxs-lookup"><span data-stu-id="99647-116">Tickets cannot be redeemed for this application without being validated.%r</span></span><br /><br /> <span data-ttu-id="99647-117">应用程序名称： %1</span><span class="sxs-lookup"><span data-stu-id="99647-117">Application Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="99647-118">解释</span><span class="sxs-lookup"><span data-stu-id="99647-118">Explanation</span></span>  
 <span data-ttu-id="99647-119">此警告事件表示，应用程序票证在不经过验证的情况下无法进行兑换。</span><span class="sxs-lookup"><span data-stu-id="99647-119">This Warning event indicates that application tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="99647-120">应用程序票证兑换后，它们可能经过了验证也可能未经过验证。</span><span class="sxs-lookup"><span data-stu-id="99647-120">When application tickets are redeemed they can be validated or not validated.</span></span> <span data-ttu-id="99647-121">验证过程会提高安全性，因为会将发出票证的用户的名称与 BizTalk 消息中用户的名称进行比较。</span><span class="sxs-lookup"><span data-stu-id="99647-121">Validation improves security by comparing the name of the user who issued the ticket with the name of the user in the BizTalk message.</span></span> <span data-ttu-id="99647-122">如果名称不相同，则验证失败。</span><span class="sxs-lookup"><span data-stu-id="99647-122">If the names are not the same then validation fails.</span></span> <span data-ttu-id="99647-123">当 BizTalk 消息在不受信任的主机中传输时，BizTalk 消息中用户的名称会更改为该不受信任主机的名称。</span><span class="sxs-lookup"><span data-stu-id="99647-123">When a BizTalk message flows through an un-trusted host, the name of the user in the BizTalk message is changed to that of the un-trusted host.</span></span> <span data-ttu-id="99647-124">验证过程确保了 BizTalk 消息只能在受信任的主机中传输。</span><span class="sxs-lookup"><span data-stu-id="99647-124">Validation ensures that the BizTalk message has only flowed through trusted hosts.</span></span> <span data-ttu-id="99647-125">此消息特别指出，由于 SSO 系统选项设置原因，需要在应用程序系统级别进行验证，但是呼叫者并未提供任何验证信息。</span><span class="sxs-lookup"><span data-stu-id="99647-125">This message means specifically that validation is required at the application system level (due to an SSO system option setting), but no validation information was provided by the caller.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="99647-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="99647-126">User Action</span></span>  
 <span data-ttu-id="99647-127">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="99647-127">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="99647-128">如果您使用的是 BizTalk Server，请确保您的消息只在受信任的主机之间传输。</span><span class="sxs-lookup"><span data-stu-id="99647-128">If you are using BizTalk Server, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="99647-129">这将降低在消息中篡改数据的风险。</span><span class="sxs-lookup"><span data-stu-id="99647-129">This will reduce the risk of tampering with the data in the message.</span></span>  
  
-   <span data-ttu-id="99647-130">如果情况允许，请针对此应用程序关闭验证。</span><span class="sxs-lookup"><span data-stu-id="99647-130">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="99647-131">验证是一个管理选项，可以针对整个系统、或只针对此特定的应用程序关闭该选项。</span><span class="sxs-lookup"><span data-stu-id="99647-131">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  
  
 <span data-ttu-id="99647-132">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="99647-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="99647-133">SSO 票证</span><span class="sxs-lookup"><span data-stu-id="99647-133">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="99647-134">如何列出关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="99647-134">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [<span data-ttu-id="99647-135">如何更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="99647-135">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)