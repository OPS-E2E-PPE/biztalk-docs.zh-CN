---
title: 单一登录： 事件 10594 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f4c6041-39a8-49bc-b39e-66cb6eb2efae
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba733d9a919b2af09824242a48a2fa85af8ab481
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004757"
---
# <a name="single-sign-on-event-10594"></a><span data-ttu-id="5e898-102">单一登录： 事件 10594</span><span class="sxs-lookup"><span data-stu-id="5e898-102">Single Sign-On: Event 10594</span></span>
## <a name="details"></a><span data-ttu-id="5e898-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5e898-103">Details</span></span>  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5e898-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5e898-104">Product Name</span></span>   |                                                                                 <span data-ttu-id="5e898-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5e898-105">Enterprise Single Sign-On</span></span>                                                                                  |
| <span data-ttu-id="5e898-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="5e898-106">Product Version</span></span> |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                 |
|    <span data-ttu-id="5e898-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5e898-107">Event ID</span></span>     |                                                                                           <span data-ttu-id="5e898-108">10594</span><span class="sxs-lookup"><span data-stu-id="5e898-108">10594</span></span>                                                                                            |
|  <span data-ttu-id="5e898-109">事件源</span><span class="sxs-lookup"><span data-stu-id="5e898-109">Event Source</span></span>   |                                                                                           <span data-ttu-id="5e898-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5e898-110">ENTSSO</span></span>                                                                                           |
|    <span data-ttu-id="5e898-111">组件</span><span class="sxs-lookup"><span data-stu-id="5e898-111">Component</span></span>    |                                                                                            <span data-ttu-id="5e898-112">N/A</span><span class="sxs-lookup"><span data-stu-id="5e898-112">N/A</span></span>                                                                                             |
|  <span data-ttu-id="5e898-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="5e898-113">Symbolic Name</span></span>  |                                                                              <span data-ttu-id="5e898-114">SSO_WARN_TICKET_VALIDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="5e898-114">SSO_WARN_TICKET_VALIDATE_FAILED</span></span>                                                                               |
|  <span data-ttu-id="5e898-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="5e898-115">Message Text</span></span>   | <span data-ttu-id="5e898-116">票证验证失败。</span><span class="sxs-lookup"><span data-stu-id="5e898-116">Validation of the ticket failed.</span></span> <span data-ttu-id="5e898-117">发件人名称必须匹配的票证 issuer.%r</span><span class="sxs-lookup"><span data-stu-id="5e898-117">The sender name must match that of the ticket issuer.%r</span></span><br /><br /> <span data-ttu-id="5e898-118">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5e898-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="5e898-119">票证颁发者: %2 %r</span><span class="sxs-lookup"><span data-stu-id="5e898-119">Ticket Issued By: %2%r</span></span><br /><br /> <span data-ttu-id="5e898-120">发件人姓名： %3</span><span class="sxs-lookup"><span data-stu-id="5e898-120">Sender Name: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="5e898-121">解释</span><span class="sxs-lookup"><span data-stu-id="5e898-121">Explanation</span></span>  
 <span data-ttu-id="5e898-122">为了使票证有效，“票证颁发者”字段与“发件人姓名”字段（在警告消息中）必须匹配。</span><span class="sxs-lookup"><span data-stu-id="5e898-122">In order for a ticket to be validated, the Ticket Issued By and Sender Name fields (in the warning message) must match.</span></span> <span data-ttu-id="5e898-123">但是，如果消息是通过不受信任的 BizTalk 主机发送的，则“发件人姓名”字段将更改为该不受信任的 BizTalk 主机的名称，并且票证将无效。</span><span class="sxs-lookup"><span data-stu-id="5e898-123">If, however, the message is sent through a BizTalk untrusted host, the Sender Name gets changed to the name of the BizTalk untrusted host, and the ticket will not validate.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5e898-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="5e898-124">User Action</span></span>  
 <span data-ttu-id="5e898-125">如果您要使用企业单一登录，请确保您的消息只流经受信任的 BizTalk 主机。</span><span class="sxs-lookup"><span data-stu-id="5e898-125">If you are using Enterprise Single Sign-On, ensure that your message is flowing only through BizTalk trusted hosts.</span></span> <span data-ttu-id="5e898-126">这将降低在消息中篡改数据的风险。</span><span class="sxs-lookup"><span data-stu-id="5e898-126">This will reduce the risk of tampering with the data in the message.</span></span>  
  
 <span data-ttu-id="5e898-127">如果您完全理解您的方案中的安全情况，可以关闭对此应用程序的验证。</span><span class="sxs-lookup"><span data-stu-id="5e898-127">If you fully understand the security implications for your scenario, you can turn off validation for this application.</span></span> <span data-ttu-id="5e898-128">请注意，验证是一个管理选项，可以关闭系统验证，也可以只关闭对此特定应用程序进行验证。</span><span class="sxs-lookup"><span data-stu-id="5e898-128">Note that validation is an administration option which can be turned off for the system or just for this particular application.</span></span>