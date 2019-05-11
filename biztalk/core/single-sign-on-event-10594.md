---
title: 单一登录：Event 10594 | Microsoft Docs
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
ms.openlocfilehash: 5c2f70c563113b7b7473d86046f2ac78eec4ea4a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397855"
---
# <a name="single-sign-on-event-10594"></a><span data-ttu-id="f2840-102">单一登录：事件 10594</span><span class="sxs-lookup"><span data-stu-id="f2840-102">Single Sign-On: Event 10594</span></span>
## <a name="details"></a><span data-ttu-id="f2840-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f2840-103">Details</span></span>  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f2840-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f2840-104">Product Name</span></span>   |                                                                                 <span data-ttu-id="f2840-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f2840-105">Enterprise Single Sign-On</span></span>                                                                                  |
| <span data-ttu-id="f2840-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f2840-106">Product Version</span></span> |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                 |
|    <span data-ttu-id="f2840-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f2840-107">Event ID</span></span>     |                                                                                           <span data-ttu-id="f2840-108">10594</span><span class="sxs-lookup"><span data-stu-id="f2840-108">10594</span></span>                                                                                            |
|  <span data-ttu-id="f2840-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f2840-109">Event Source</span></span>   |                                                                                           <span data-ttu-id="f2840-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f2840-110">ENTSSO</span></span>                                                                                           |
|    <span data-ttu-id="f2840-111">组件</span><span class="sxs-lookup"><span data-stu-id="f2840-111">Component</span></span>    |                                                                                            <span data-ttu-id="f2840-112">不可用</span><span class="sxs-lookup"><span data-stu-id="f2840-112">N/A</span></span>                                                                                             |
|  <span data-ttu-id="f2840-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f2840-113">Symbolic Name</span></span>  |                                                                              <span data-ttu-id="f2840-114">SSO_WARN_TICKET_VALIDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="f2840-114">SSO_WARN_TICKET_VALIDATE_FAILED</span></span>                                                                               |
|  <span data-ttu-id="f2840-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f2840-115">Message Text</span></span>   | <span data-ttu-id="f2840-116">票证验证失败。</span><span class="sxs-lookup"><span data-stu-id="f2840-116">Validation of the ticket failed.</span></span> <span data-ttu-id="f2840-117">发件人名称必须匹配的票证 issuer.%r</span><span class="sxs-lookup"><span data-stu-id="f2840-117">The sender name must match that of the ticket issuer.%r</span></span><br /><br /> <span data-ttu-id="f2840-118">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f2840-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="f2840-119">票证颁发者: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f2840-119">Ticket Issued By: %2%r</span></span><br /><br /> <span data-ttu-id="f2840-120">发件人姓名： %3</span><span class="sxs-lookup"><span data-stu-id="f2840-120">Sender Name: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f2840-121">解释</span><span class="sxs-lookup"><span data-stu-id="f2840-121">Explanation</span></span>  
 <span data-ttu-id="f2840-122">为了使票证进行验证，必须匹配 （中的警告消息） 的票证颁发者和发件人姓名字段。</span><span class="sxs-lookup"><span data-stu-id="f2840-122">In order for a ticket to be validated, the Ticket Issued By and Sender Name fields (in the warning message) must match.</span></span> <span data-ttu-id="f2840-123">如果，但是，通过 BizTalk 不受信任主机发送邮件，发件人名称获取更改为 BizTalk 主机的名称不受信任，并且票证将无效。</span><span class="sxs-lookup"><span data-stu-id="f2840-123">If, however, the message is sent through a BizTalk untrusted host, the Sender Name gets changed to the name of the BizTalk untrusted host, and the ticket will not validate.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f2840-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="f2840-124">User Action</span></span>  
 <span data-ttu-id="f2840-125">如果使用企业单一登录，请确保，您的消息只流经受信任的 BizTalk 主机。</span><span class="sxs-lookup"><span data-stu-id="f2840-125">If you are using Enterprise Single Sign-On, ensure that your message is flowing only through BizTalk trusted hosts.</span></span> <span data-ttu-id="f2840-126">这将减少与消息中的数据被篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="f2840-126">This will reduce the risk of tampering with the data in the message.</span></span>  
  
 <span data-ttu-id="f2840-127">如果您完全理解的安全隐患，为你的方案，可以关闭此应用程序的验证。</span><span class="sxs-lookup"><span data-stu-id="f2840-127">If you fully understand the security implications for your scenario, you can turn off validation for this application.</span></span> <span data-ttu-id="f2840-128">请注意，验证是一个管理选项，可以关闭状态的系统或只需为此特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="f2840-128">Note that validation is an administration option which can be turned off for the system or just for this particular application.</span></span>