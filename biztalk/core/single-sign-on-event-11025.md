---
title: 单一登录：事件 11025 |Microsoft Docs
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
ms.openlocfilehash: 3a3cd83ad3beab084a00190632df9457ee987ac6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379983"
---
# <a name="single-sign-on-event-11025"></a><span data-ttu-id="eef37-102">单一登录：事件 11025</span><span class="sxs-lookup"><span data-stu-id="eef37-102">Single Sign-On: Event 11025</span></span>
## <a name="details"></a><span data-ttu-id="eef37-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="eef37-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="eef37-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="eef37-104">Product Name</span></span>   |                                                                                                 <span data-ttu-id="eef37-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="eef37-105">Enterprise Single Sign-On</span></span>                                                                                                  |
| <span data-ttu-id="eef37-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="eef37-106">Product Version</span></span> |                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                 |
|    <span data-ttu-id="eef37-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="eef37-107">Event ID</span></span>     |                                                                                                           <span data-ttu-id="eef37-108">11025</span><span class="sxs-lookup"><span data-stu-id="eef37-108">11025</span></span>                                                                                                            |
|  <span data-ttu-id="eef37-109">事件源</span><span class="sxs-lookup"><span data-stu-id="eef37-109">Event Source</span></span>   |                                                                                                           <span data-ttu-id="eef37-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="eef37-110">ENTSSO</span></span>                                                                                                           |
|    <span data-ttu-id="eef37-111">组件</span><span class="sxs-lookup"><span data-stu-id="eef37-111">Component</span></span>    |                                                                                                            <span data-ttu-id="eef37-112">不可用</span><span class="sxs-lookup"><span data-stu-id="eef37-112">N/A</span></span>                                                                                                             |
|  <span data-ttu-id="eef37-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="eef37-113">Symbolic Name</span></span>  |                                                                                            <span data-ttu-id="eef37-114">SSO_WARN_INVALID_APP_TICKET_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eef37-114">SSO_WARN_INVALID_APP_TICKET_TIMEOUT</span></span>                                                                                             |
|  <span data-ttu-id="eef37-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="eef37-115">Message Text</span></span>   | <span data-ttu-id="eef37-116">票证超时值不能用于应用程序 update.%r</span><span class="sxs-lookup"><span data-stu-id="eef37-116">The ticket time-out value is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="eef37-117">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="eef37-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="eef37-118">票证超时： %2 分钟 %r</span><span class="sxs-lookup"><span data-stu-id="eef37-118">Ticket time-out: %2 minutes%r</span></span><br /><br /> <span data-ttu-id="eef37-119">最大票证超时： %3 分钟 %r</span><span class="sxs-lookup"><span data-stu-id="eef37-119">Maximum ticket time-out: %3 minutes%r</span></span><br /><br /> <span data-ttu-id="eef37-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="eef37-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="eef37-121">解释</span><span class="sxs-lookup"><span data-stu-id="eef37-121">Explanation</span></span>  
 <span data-ttu-id="eef37-122">票证超时值无效。</span><span class="sxs-lookup"><span data-stu-id="eef37-122">The ticket time-out value is not valid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eef37-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="eef37-123">User Action</span></span>  
 <span data-ttu-id="eef37-124">票证超时值的详细信息，请参阅[SSO 关联应用程序](../core/sso-affiliate-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="eef37-124">For more information on ticket time-outs, see [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>