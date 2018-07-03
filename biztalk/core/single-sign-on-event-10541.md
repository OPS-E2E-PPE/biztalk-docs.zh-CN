---
title: 单一登录： 事件 10541 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e206158-5652-453c-91ac-9a75ab02809a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46f3b34c5e57b4fe10a50f684143cc10476e4eaa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991014"
---
# <a name="single-sign-on-event-10541"></a><span data-ttu-id="87940-102">单一登录： 事件 10541</span><span class="sxs-lookup"><span data-stu-id="87940-102">Single Sign-On: Event 10541</span></span>
## <a name="details"></a><span data-ttu-id="87940-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="87940-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="87940-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="87940-104">Product Name</span></span>   |                 <span data-ttu-id="87940-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="87940-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="87940-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="87940-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="87940-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="87940-107">Event ID</span></span>     |                           <span data-ttu-id="87940-108">10541</span><span class="sxs-lookup"><span data-stu-id="87940-108">10541</span></span>                            |
|  <span data-ttu-id="87940-109">事件源</span><span class="sxs-lookup"><span data-stu-id="87940-109">Event Source</span></span>   |                           <span data-ttu-id="87940-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="87940-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="87940-111">组件</span><span class="sxs-lookup"><span data-stu-id="87940-111">Component</span></span>    |                             <span data-ttu-id="87940-112">CO</span><span class="sxs-lookup"><span data-stu-id="87940-112">CO</span></span>                             |
|  <span data-ttu-id="87940-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="87940-113">Symbolic Name</span></span>  |               <span data-ttu-id="87940-114">SSO_WARN_SSO_TICKETS_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="87940-114">SSO_WARN_SSO_TICKETS_VALIDATED</span></span>               |
|  <span data-ttu-id="87940-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="87940-115">Message Text</span></span>   |    <span data-ttu-id="87940-116">票证未经验证不能兑换。</span><span class="sxs-lookup"><span data-stu-id="87940-116">Tickets cannot be redeemed without being validated.</span></span>     |

## <a name="explanation"></a><span data-ttu-id="87940-117">解释</span><span class="sxs-lookup"><span data-stu-id="87940-117">Explanation</span></span>  
 <span data-ttu-id="87940-118">此警告事件表明，SSO 票证未经验证不能兑换。</span><span class="sxs-lookup"><span data-stu-id="87940-118">This Warning event indicates that SSO tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="87940-119">SSO 票证兑换之后，可以对其进行验证，也可以不验证。</span><span class="sxs-lookup"><span data-stu-id="87940-119">When SSO tickets are redeemed they can be validated or not validated.</span></span> <span data-ttu-id="87940-120">验证过程会提高安全性，因为会将发出票证的用户的名称与 BizTalk 消息中用户的名称进行比较。</span><span class="sxs-lookup"><span data-stu-id="87940-120">Validation improves security by comparing the name of the user who issued the ticket with the name of the user in the BizTalk message.</span></span> <span data-ttu-id="87940-121">如果名称不相同，则验证失败。</span><span class="sxs-lookup"><span data-stu-id="87940-121">If the names are not the same then validation fails.</span></span> <span data-ttu-id="87940-122">当 BizTalk 消息在不受信任的主机中传输时，BizTalk 消息中用户的名称会更改为该不受信任主机的名称。</span><span class="sxs-lookup"><span data-stu-id="87940-122">When a BizTalk message flows through an un-trusted host, the name of the user in the BizTalk message is changed to that of the un-trusted host.</span></span> <span data-ttu-id="87940-123">验证过程确保了 BizTalk 消息只能在受信任的主机中传输。</span><span class="sxs-lookup"><span data-stu-id="87940-123">Validation ensures that the BizTalk message has only flowed through trusted hosts.</span></span> <span data-ttu-id="87940-124">此消息尤其意味着，需要在 SSO 系统级别进行验证（由于 SSO 系统选项设置的原因），但调用方未提供任何验证信息。</span><span class="sxs-lookup"><span data-stu-id="87940-124">This message means specifically that validation is required at the SSO system level (due to an SSO system option setting), but no validation information was provided by the caller.</span></span>  

## <a name="user-action"></a><span data-ttu-id="87940-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="87940-125">User Action</span></span>  
 <span data-ttu-id="87940-126">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="87940-126">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="87940-127">如果您使用的是 BizTalk Server，请确保您的消息只在受信任的主机之间传输。</span><span class="sxs-lookup"><span data-stu-id="87940-127">If you are using BizTalk Server, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="87940-128">这将降低在消息中篡改数据的风险。</span><span class="sxs-lookup"><span data-stu-id="87940-128">This will reduce the risk of tampering with the data in the message.</span></span>  

- <span data-ttu-id="87940-129">如果情况允许，请针对此应用程序关闭验证。</span><span class="sxs-lookup"><span data-stu-id="87940-129">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="87940-130">验证是一个管理选项，可以针对整个系统、或只针对此特定的应用程序关闭该选项。</span><span class="sxs-lookup"><span data-stu-id="87940-130">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  

  <span data-ttu-id="87940-131">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="87940-131">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="87940-132">SSO 票证</span><span class="sxs-lookup"><span data-stu-id="87940-132">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="87940-133">如何列出关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="87940-133">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="87940-134">如何更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="87940-134">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
