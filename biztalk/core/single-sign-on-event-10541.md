---
title: 单一登录：Event 10541 | Microsoft Docs
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
ms.openlocfilehash: b7a30d3c2221632d4dd9d050067f8fc9094d37d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250286"
---
# <a name="single-sign-on-event-10541"></a><span data-ttu-id="3d9ff-102">单一登录：事件 10541</span><span class="sxs-lookup"><span data-stu-id="3d9ff-102">Single Sign-On: Event 10541</span></span>
## <a name="details"></a><span data-ttu-id="3d9ff-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3d9ff-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="3d9ff-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3d9ff-104">Product Name</span></span>   |                 <span data-ttu-id="3d9ff-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="3d9ff-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="3d9ff-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="3d9ff-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="3d9ff-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3d9ff-107">Event ID</span></span>     |                           <span data-ttu-id="3d9ff-108">10541</span><span class="sxs-lookup"><span data-stu-id="3d9ff-108">10541</span></span>                            |
|  <span data-ttu-id="3d9ff-109">事件源</span><span class="sxs-lookup"><span data-stu-id="3d9ff-109">Event Source</span></span>   |                           <span data-ttu-id="3d9ff-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3d9ff-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="3d9ff-111">组件</span><span class="sxs-lookup"><span data-stu-id="3d9ff-111">Component</span></span>    |                             <span data-ttu-id="3d9ff-112">CO</span><span class="sxs-lookup"><span data-stu-id="3d9ff-112">CO</span></span>                             |
|  <span data-ttu-id="3d9ff-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="3d9ff-113">Symbolic Name</span></span>  |               <span data-ttu-id="3d9ff-114">SSO_WARN_SSO_TICKETS_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="3d9ff-114">SSO_WARN_SSO_TICKETS_VALIDATED</span></span>               |
|  <span data-ttu-id="3d9ff-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="3d9ff-115">Message Text</span></span>   |    <span data-ttu-id="3d9ff-116">未经验证，不能兑换票证。</span><span class="sxs-lookup"><span data-stu-id="3d9ff-116">Tickets cannot be redeemed without being validated.</span></span>     |

## <a name="explanation"></a><span data-ttu-id="3d9ff-117">解释</span><span class="sxs-lookup"><span data-stu-id="3d9ff-117">Explanation</span></span>  
 <span data-ttu-id="3d9ff-118">此警告事件表示 SSO 票证，不能兑换未经验证。</span><span class="sxs-lookup"><span data-stu-id="3d9ff-118">This Warning event indicates that SSO tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="3d9ff-119">当 SSO 票证兑换之后它们可以进行验证或不进行验证。</span><span class="sxs-lookup"><span data-stu-id="3d9ff-119">When SSO tickets are redeemed they can be validated or not validated.</span></span> <span data-ttu-id="3d9ff-120">验证可以提高安全性，通过比较 BizTalk 消息中的用户的名称与颁发票证的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="3d9ff-120">Validation improves security by comparing the name of the user who issued the ticket with the name of the user in the BizTalk message.</span></span> <span data-ttu-id="3d9ff-121">如果名称不同时验证失败。</span><span class="sxs-lookup"><span data-stu-id="3d9ff-121">If the names are not the same then validation fails.</span></span> <span data-ttu-id="3d9ff-122">当 BizTalk 消息流经的不受信任的主机时，BizTalk 消息中的用户的名称更改为不受信任的主机。</span><span class="sxs-lookup"><span data-stu-id="3d9ff-122">When a BizTalk message flows through an un-trusted host, the name of the user in the BizTalk message is changed to that of the un-trusted host.</span></span> <span data-ttu-id="3d9ff-123">验证可确保 BizTalk 消息仅已流经受信任的主机。</span><span class="sxs-lookup"><span data-stu-id="3d9ff-123">Validation ensures that the BizTalk message has only flowed through trusted hosts.</span></span> <span data-ttu-id="3d9ff-124">此消息尤其意味着，在 SSO 系统级别 （由于 SSO 系统选项设置），需要验证但已由调用方提供任何验证信息。</span><span class="sxs-lookup"><span data-stu-id="3d9ff-124">This message means specifically that validation is required at the SSO system level (due to an SSO system option setting), but no validation information was provided by the caller.</span></span>  

## <a name="user-action"></a><span data-ttu-id="3d9ff-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="3d9ff-125">User Action</span></span>  
 <span data-ttu-id="3d9ff-126">若要解决此警告，请执行一个或多个以下操作：</span><span class="sxs-lookup"><span data-stu-id="3d9ff-126">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="3d9ff-127">如果使用 BizTalk Server，请确保，您的消息只流经受受信任的主机。</span><span class="sxs-lookup"><span data-stu-id="3d9ff-127">If you are using BizTalk Server, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="3d9ff-128">这将减少与消息中的数据被篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="3d9ff-128">This will reduce the risk of tampering with the data in the message.</span></span>  

- <span data-ttu-id="3d9ff-129">如果你的方案允许，将关闭此应用程序的验证。</span><span class="sxs-lookup"><span data-stu-id="3d9ff-129">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="3d9ff-130">验证是一个管理选项，可以关闭状态的系统或只需为此特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="3d9ff-130">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  

  <span data-ttu-id="3d9ff-131">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="3d9ff-131">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="3d9ff-132">SSO 票证</span><span class="sxs-lookup"><span data-stu-id="3d9ff-132">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="3d9ff-133">如何列出关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="3d9ff-133">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="3d9ff-134">如何更新关联应用程序的属性</span><span class="sxs-lookup"><span data-stu-id="3d9ff-134">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
