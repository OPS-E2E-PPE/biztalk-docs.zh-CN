---
title: 单一登录：Event 10542 | Microsoft Docs
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
ms.openlocfilehash: 493937fbcf9eb04ccfe59881c56f12e4b3851f11
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243432"
---
# <a name="single-sign-on-event-10542"></a><span data-ttu-id="c8889-102">单一登录：事件 10542</span><span class="sxs-lookup"><span data-stu-id="c8889-102">Single Sign-On: Event 10542</span></span>
## <a name="details"></a><span data-ttu-id="c8889-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c8889-103">Details</span></span>  

|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c8889-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c8889-104">Product Name</span></span>   |                                          <span data-ttu-id="c8889-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="c8889-105">Enterprise Single Sign-On</span></span>                                          |
| <span data-ttu-id="c8889-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="c8889-106">Product Version</span></span> |                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                          |
|    <span data-ttu-id="c8889-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c8889-107">Event ID</span></span>     |                                                    <span data-ttu-id="c8889-108">10542</span><span class="sxs-lookup"><span data-stu-id="c8889-108">10542</span></span>                                                    |
|  <span data-ttu-id="c8889-109">事件源</span><span class="sxs-lookup"><span data-stu-id="c8889-109">Event Source</span></span>   |                                                   <span data-ttu-id="c8889-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c8889-110">ENTSSO</span></span>                                                    |
|    <span data-ttu-id="c8889-111">组件</span><span class="sxs-lookup"><span data-stu-id="c8889-111">Component</span></span>    |                                                     <span data-ttu-id="c8889-112">CO</span><span class="sxs-lookup"><span data-stu-id="c8889-112">CO</span></span>                                                      |
|  <span data-ttu-id="c8889-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="c8889-113">Symbolic Name</span></span>  |                                       <span data-ttu-id="c8889-114">SSO_WARN_APP_TICKETS_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="c8889-114">SSO_WARN_APP_TICKETS_VALIDATED</span></span>                                        |
|  <span data-ttu-id="c8889-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="c8889-115">Message Text</span></span>   | <span data-ttu-id="c8889-116">不能为此应用程序未经 validated.%r 兑换票证</span><span class="sxs-lookup"><span data-stu-id="c8889-116">Tickets cannot be redeemed for this application without being validated.%r</span></span><br /><br /> <span data-ttu-id="c8889-117">应用程序名称： %1</span><span class="sxs-lookup"><span data-stu-id="c8889-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="c8889-118">解释</span><span class="sxs-lookup"><span data-stu-id="c8889-118">Explanation</span></span>  
 <span data-ttu-id="c8889-119">此警告事件表示，不能应用程序票证兑换未经验证。</span><span class="sxs-lookup"><span data-stu-id="c8889-119">This Warning event indicates that application tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="c8889-120">当应用程序票证兑换之后它们可以进行验证或不进行验证。</span><span class="sxs-lookup"><span data-stu-id="c8889-120">When application tickets are redeemed they can be validated or not validated.</span></span> <span data-ttu-id="c8889-121">验证可以提高安全性，通过比较 BizTalk 消息中的用户的名称与颁发票证的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="c8889-121">Validation improves security by comparing the name of the user who issued the ticket with the name of the user in the BizTalk message.</span></span> <span data-ttu-id="c8889-122">如果名称不同时验证失败。</span><span class="sxs-lookup"><span data-stu-id="c8889-122">If the names are not the same then validation fails.</span></span> <span data-ttu-id="c8889-123">当 BizTalk 消息流经的不受信任的主机时，BizTalk 消息中的用户的名称更改为不受信任的主机。</span><span class="sxs-lookup"><span data-stu-id="c8889-123">When a BizTalk message flows through an un-trusted host, the name of the user in the BizTalk message is changed to that of the un-trusted host.</span></span> <span data-ttu-id="c8889-124">验证可确保 BizTalk 消息仅已流经受信任的主机。</span><span class="sxs-lookup"><span data-stu-id="c8889-124">Validation ensures that the BizTalk message has only flowed through trusted hosts.</span></span> <span data-ttu-id="c8889-125">此消息尤其意味着系统级别的应用程序 （由于 SSO 系统选项设置），需要验证但已由调用方提供任何验证信息。</span><span class="sxs-lookup"><span data-stu-id="c8889-125">This message means specifically that validation is required at the application system level (due to an SSO system option setting), but no validation information was provided by the caller.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c8889-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="c8889-126">User Action</span></span>  
 <span data-ttu-id="c8889-127">若要解决此警告，请执行一个或多个以下操作：</span><span class="sxs-lookup"><span data-stu-id="c8889-127">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="c8889-128">如果使用 BizTalk Server，请确保，您的消息只流经受受信任的主机。</span><span class="sxs-lookup"><span data-stu-id="c8889-128">If you are using BizTalk Server, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="c8889-129">这将减少与消息中的数据被篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="c8889-129">This will reduce the risk of tampering with the data in the message.</span></span>  

- <span data-ttu-id="c8889-130">如果你的方案允许，将关闭此应用程序的验证。</span><span class="sxs-lookup"><span data-stu-id="c8889-130">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="c8889-131">验证是一个管理选项，可以关闭状态的系统或只需为此特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8889-131">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  

  <span data-ttu-id="c8889-132">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="c8889-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="c8889-133">SSO 票证</span><span class="sxs-lookup"><span data-stu-id="c8889-133">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="c8889-134">如何列出关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="c8889-134">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="c8889-135">如何更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="c8889-135">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
