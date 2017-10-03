---
title: "单一登录： 事件 11010 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22fcd9f3-83bb-44b0-88fc-197c2ef3e72d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f81bef87439c4607a32f2547d5bf44b19491140b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11010"></a><span data-ttu-id="d226f-102">单一登录： 事件 11010</span><span class="sxs-lookup"><span data-stu-id="d226f-102">Single Sign-On: Event 11010</span></span>
## <a name="details"></a><span data-ttu-id="d226f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d226f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d226f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d226f-104">Product Name</span></span>|<span data-ttu-id="d226f-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="d226f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="d226f-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="d226f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="d226f-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d226f-107">Event ID</span></span>|<span data-ttu-id="d226f-108">11010</span><span class="sxs-lookup"><span data-stu-id="d226f-108">11010</span></span>|  
|<span data-ttu-id="d226f-109">事件源</span><span class="sxs-lookup"><span data-stu-id="d226f-109">Event Source</span></span>|<span data-ttu-id="d226f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d226f-110">ENTSSO</span></span>|  
|<span data-ttu-id="d226f-111">组件</span><span class="sxs-lookup"><span data-stu-id="d226f-111">Component</span></span>|<span data-ttu-id="d226f-112">N/A</span><span class="sxs-lookup"><span data-stu-id="d226f-112">N/A</span></span>|  
|<span data-ttu-id="d226f-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="d226f-113">Symbolic Name</span></span>|<span data-ttu-id="d226f-114">SSO_WARN_NOT_SSO_AFF_ADMIN</span><span class="sxs-lookup"><span data-stu-id="d226f-114">SSO_WARN_NOT_SSO_AFF_ADMIN</span></span>|  
|<span data-ttu-id="d226f-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="d226f-115">Message Text</span></span>|<span data-ttu-id="d226f-116">客户端用户不是 SSO 关联管理员帐户的成员。%r</span><span class="sxs-lookup"><span data-stu-id="d226f-116">Client user is not a member of the SSO Affiliate Administrators account.%r</span></span><br /><br /> <span data-ttu-id="d226f-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d226f-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="d226f-118">客户端用户： %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="d226f-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="d226f-119">SSO Affiliate Administrators: %4</span><span class="sxs-lookup"><span data-stu-id="d226f-119">SSO Affiliate Administrators: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d226f-120">解释</span><span class="sxs-lookup"><span data-stu-id="d226f-120">Explanation</span></span>  
 <span data-ttu-id="d226f-121">客户端用户不是 SSO 关联管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="d226f-121">The client user is not a member of the SSO Affiliate Administrators account.</span></span> <span data-ttu-id="d226f-122">只有当审核级别设置为高时，才会出现此警告。</span><span class="sxs-lookup"><span data-stu-id="d226f-122">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d226f-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="d226f-123">User Action</span></span>  
 <span data-ttu-id="d226f-124">为避免此情况，您必须使客户端用户成为 SSO 关联管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="d226f-124">To remedy the situation, you must make the client user a member of the SSO Affiliate Administrators account.</span></span> <span data-ttu-id="d226f-125">若要阻止以后出现此警告，您可以降低审核级别。</span><span class="sxs-lookup"><span data-stu-id="d226f-125">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>