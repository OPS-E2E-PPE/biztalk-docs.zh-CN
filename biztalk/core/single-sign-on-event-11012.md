---
title: "单一登录： 事件 11012 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 252bedc8-8dc3-4962-b078-465f9b064ead
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7c559f7416e0f882b4487629033e5b059802d20
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11012"></a><span data-ttu-id="c6517-102">单一登录： 事件 11012</span><span class="sxs-lookup"><span data-stu-id="c6517-102">Single Sign-On: Event 11012</span></span>
## <a name="details"></a><span data-ttu-id="c6517-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c6517-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c6517-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c6517-104">Product Name</span></span>|<span data-ttu-id="c6517-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="c6517-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="c6517-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="c6517-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="c6517-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c6517-107">Event ID</span></span>|<span data-ttu-id="c6517-108">11012</span><span class="sxs-lookup"><span data-stu-id="c6517-108">11012</span></span>|  
|<span data-ttu-id="c6517-109">事件源</span><span class="sxs-lookup"><span data-stu-id="c6517-109">Event Source</span></span>|<span data-ttu-id="c6517-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c6517-110">ENTSSO</span></span>|  
|<span data-ttu-id="c6517-111">组件</span><span class="sxs-lookup"><span data-stu-id="c6517-111">Component</span></span>|<span data-ttu-id="c6517-112">N/A</span><span class="sxs-lookup"><span data-stu-id="c6517-112">N/A</span></span>|  
|<span data-ttu-id="c6517-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="c6517-113">Symbolic Name</span></span>|<span data-ttu-id="c6517-114">SSO_WARN_NOT_APP_ADMIN_ADMIN_SAME</span><span class="sxs-lookup"><span data-stu-id="c6517-114">SSO_WARN_NOT_APP_ADMIN_ADMIN_SAME</span></span>|  
|<span data-ttu-id="c6517-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="c6517-115">Message Text</span></span>|<span data-ttu-id="c6517-116">客户端用户不是应用程序管理员帐户的成员。%r</span><span class="sxs-lookup"><span data-stu-id="c6517-116">Client user is not a member of the Application Administrators account.%r</span></span><br /><br /> <span data-ttu-id="c6517-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c6517-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="c6517-118">客户端用户： %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="c6517-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="c6517-119">应用程序名称: %4 %r</span><span class="sxs-lookup"><span data-stu-id="c6517-119">Application Name: %4%r</span></span><br /><br /> <span data-ttu-id="c6517-120">应用程序管理员： %5</span><span class="sxs-lookup"><span data-stu-id="c6517-120">Application Administrators: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c6517-121">解释</span><span class="sxs-lookup"><span data-stu-id="c6517-121">Explanation</span></span>  
 <span data-ttu-id="c6517-122">客户端用户不是应用程序管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="c6517-122">The client user is not a member of the Application Administrators account.</span></span> <span data-ttu-id="c6517-123">只有当审核级别设置为高时，才会出现此警告。</span><span class="sxs-lookup"><span data-stu-id="c6517-123">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c6517-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="c6517-124">User Action</span></span>  
 <span data-ttu-id="c6517-125">若要修复此情形，您必须使客户端用户成为应用程序管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="c6517-125">To remedy the situation, you must make the client user a member of the Application Administrators account.</span></span> <span data-ttu-id="c6517-126">若要阻止以后出现此警告，您可以降低审核级别。</span><span class="sxs-lookup"><span data-stu-id="c6517-126">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>