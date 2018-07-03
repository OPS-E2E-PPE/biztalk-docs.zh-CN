---
title: 单一登录： 事件 11025 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df5a733b-3c95-409c-8485-bf3f7feb3c50
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd8c25dc80669b4524c7e9ce848e4b0e28f773f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015894"
---
# <a name="single-sign-on-event-11025"></a><span data-ttu-id="95e34-102">单一登录： 事件 11025</span><span class="sxs-lookup"><span data-stu-id="95e34-102">Single Sign-On: Event 11025</span></span>
## <a name="details"></a><span data-ttu-id="95e34-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="95e34-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="95e34-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="95e34-104">Product Name</span></span>   |                                                                                                 <span data-ttu-id="95e34-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="95e34-105">Enterprise Single Sign-On</span></span>                                                                                                  |
| <span data-ttu-id="95e34-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="95e34-106">Product Version</span></span> |                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                 |
|    <span data-ttu-id="95e34-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="95e34-107">Event ID</span></span>     |                                                                                                           <span data-ttu-id="95e34-108">11025</span><span class="sxs-lookup"><span data-stu-id="95e34-108">11025</span></span>                                                                                                            |
|  <span data-ttu-id="95e34-109">事件源</span><span class="sxs-lookup"><span data-stu-id="95e34-109">Event Source</span></span>   |                                                                                                           <span data-ttu-id="95e34-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="95e34-110">ENTSSO</span></span>                                                                                                           |
|    <span data-ttu-id="95e34-111">组件</span><span class="sxs-lookup"><span data-stu-id="95e34-111">Component</span></span>    |                                                                                                            <span data-ttu-id="95e34-112">N/A</span><span class="sxs-lookup"><span data-stu-id="95e34-112">N/A</span></span>                                                                                                             |
|  <span data-ttu-id="95e34-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="95e34-113">Symbolic Name</span></span>  |                                                                                            <span data-ttu-id="95e34-114">SSO_WARN_INVALID_APP_TICKET_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="95e34-114">SSO_WARN_INVALID_APP_TICKET_TIMEOUT</span></span>                                                                                             |
|  <span data-ttu-id="95e34-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="95e34-115">Message Text</span></span>   | <span data-ttu-id="95e34-116">票证超时值对应用程序更新无效。%r</span><span class="sxs-lookup"><span data-stu-id="95e34-116">The ticket time-out value is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="95e34-117">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="95e34-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="95e34-118">票证超时： %2 分钟 %r</span><span class="sxs-lookup"><span data-stu-id="95e34-118">Ticket time-out: %2 minutes%r</span></span><br /><br /> <span data-ttu-id="95e34-119">最大票证超时： %3 分钟 %r</span><span class="sxs-lookup"><span data-stu-id="95e34-119">Maximum ticket time-out: %3 minutes%r</span></span><br /><br /> <span data-ttu-id="95e34-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="95e34-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="95e34-121">解释</span><span class="sxs-lookup"><span data-stu-id="95e34-121">Explanation</span></span>  
 <span data-ttu-id="95e34-122">票证超时值无效。</span><span class="sxs-lookup"><span data-stu-id="95e34-122">The ticket time-out value is not valid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="95e34-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="95e34-123">User Action</span></span>  
 <span data-ttu-id="95e34-124">票证超时值的详细信息，请参阅[SSO 关联应用程序](../core/sso-affiliate-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="95e34-124">For more information on ticket time-outs, see [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>