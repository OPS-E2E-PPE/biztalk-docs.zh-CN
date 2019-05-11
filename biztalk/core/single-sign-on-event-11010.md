---
title: 单一登录：Event 11010 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22fcd9f3-83bb-44b0-88fc-197c2ef3e72d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b2bc9357644c48a7b17acc38582d8b386dd28e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306529"
---
# <a name="single-sign-on-event-11010"></a><span data-ttu-id="0e6b6-102">单一登录：事件 11010</span><span class="sxs-lookup"><span data-stu-id="0e6b6-102">Single Sign-On: Event 11010</span></span>
## <a name="details"></a><span data-ttu-id="0e6b6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0e6b6-103">Details</span></span>  
  
|                 |                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0e6b6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0e6b6-104">Product Name</span></span>   |                                                                                <span data-ttu-id="0e6b6-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0e6b6-105">Enterprise Single Sign-On</span></span>                                                                                |
| <span data-ttu-id="0e6b6-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0e6b6-106">Product Version</span></span> |                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                |
|    <span data-ttu-id="0e6b6-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0e6b6-107">Event ID</span></span>     |                                                                                          <span data-ttu-id="0e6b6-108">11010</span><span class="sxs-lookup"><span data-stu-id="0e6b6-108">11010</span></span>                                                                                          |
|  <span data-ttu-id="0e6b6-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0e6b6-109">Event Source</span></span>   |                                                                                         <span data-ttu-id="0e6b6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0e6b6-110">ENTSSO</span></span>                                                                                          |
|    <span data-ttu-id="0e6b6-111">组件</span><span class="sxs-lookup"><span data-stu-id="0e6b6-111">Component</span></span>    |                                                                                           <span data-ttu-id="0e6b6-112">不可用</span><span class="sxs-lookup"><span data-stu-id="0e6b6-112">N/A</span></span>                                                                                           |
|  <span data-ttu-id="0e6b6-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0e6b6-113">Symbolic Name</span></span>  |                                                                               <span data-ttu-id="0e6b6-114">SSO_WARN_NOT_SSO_AFF_ADMIN</span><span class="sxs-lookup"><span data-stu-id="0e6b6-114">SSO_WARN_NOT_SSO_AFF_ADMIN</span></span>                                                                                |
|  <span data-ttu-id="0e6b6-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0e6b6-115">Message Text</span></span>   | <span data-ttu-id="0e6b6-116">客户端用户不是 SSO Affiliate Administrators account.%r 的成员</span><span class="sxs-lookup"><span data-stu-id="0e6b6-116">Client user is not a member of the SSO Affiliate Administrators account.%r</span></span><br /><br /> <span data-ttu-id="0e6b6-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0e6b6-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="0e6b6-118">客户端用户： %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="0e6b6-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="0e6b6-119">SSO 关联管理员： %4</span><span class="sxs-lookup"><span data-stu-id="0e6b6-119">SSO Affiliate Administrators: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0e6b6-120">解释</span><span class="sxs-lookup"><span data-stu-id="0e6b6-120">Explanation</span></span>  
 <span data-ttu-id="0e6b6-121">客户端用户不是 SSO Affiliate Administrators 帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-121">The client user is not a member of the SSO Affiliate Administrators account.</span></span> <span data-ttu-id="0e6b6-122">审核级别设置为高时，才会显示此警告。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-122">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0e6b6-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="0e6b6-123">User Action</span></span>  
 <span data-ttu-id="0e6b6-124">若要纠正这种情况，您必须使客户端用户的 SSO Affiliate Administrators 帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-124">To remedy the situation, you must make the client user a member of the SSO Affiliate Administrators account.</span></span> <span data-ttu-id="0e6b6-125">若要停止在将来出现此警告消息，则可以降低审核级别。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-125">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>