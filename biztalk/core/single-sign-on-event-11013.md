---
title: 单一登录： 事件 11013 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 450836dc-ddeb-4423-9966-69ad173f2c87
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4765f542f7694b8ca5019af9effb8eace1ffbb60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277941"
---
# <a name="single-sign-on-event-11013"></a><span data-ttu-id="c9b84-102">单一登录： 事件 11013</span><span class="sxs-lookup"><span data-stu-id="c9b84-102">Single Sign-On: Event 11013</span></span>
## <a name="details"></a><span data-ttu-id="c9b84-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c9b84-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c9b84-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c9b84-104">Product Name</span></span>|<span data-ttu-id="c9b84-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="c9b84-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="c9b84-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="c9b84-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="c9b84-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c9b84-107">Event ID</span></span>|<span data-ttu-id="c9b84-108">11013</span><span class="sxs-lookup"><span data-stu-id="c9b84-108">11013</span></span>|  
|<span data-ttu-id="c9b84-109">事件源</span><span class="sxs-lookup"><span data-stu-id="c9b84-109">Event Source</span></span>|<span data-ttu-id="c9b84-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c9b84-110">ENTSSO</span></span>|  
|<span data-ttu-id="c9b84-111">组件</span><span class="sxs-lookup"><span data-stu-id="c9b84-111">Component</span></span>|<span data-ttu-id="c9b84-112">N/A</span><span class="sxs-lookup"><span data-stu-id="c9b84-112">N/A</span></span>|  
|<span data-ttu-id="c9b84-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="c9b84-113">Symbolic Name</span></span>|<span data-ttu-id="c9b84-114">SSO_WARN_NOT_APP_USER</span><span class="sxs-lookup"><span data-stu-id="c9b84-114">SSO_WARN_NOT_APP_USER</span></span>|  
|<span data-ttu-id="c9b84-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="c9b84-115">Message Text</span></span>|<span data-ttu-id="c9b84-116">客户端用户不是应用程序用户帐户的成员。%r</span><span class="sxs-lookup"><span data-stu-id="c9b84-116">Client user is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="c9b84-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c9b84-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="c9b84-118">客户端用户： %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="c9b84-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="c9b84-119">应用程序名称: %4 %r</span><span class="sxs-lookup"><span data-stu-id="c9b84-119">Application Name: %4%r</span></span><br /><br /> <span data-ttu-id="c9b84-120">Application Users: %5</span><span class="sxs-lookup"><span data-stu-id="c9b84-120">Application Users: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c9b84-121">解释</span><span class="sxs-lookup"><span data-stu-id="c9b84-121">Explanation</span></span>  
 <span data-ttu-id="c9b84-122">客户端用户不是应用程序用户帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="c9b84-122">The client user is not a member of the Application Users account.</span></span> <span data-ttu-id="c9b84-123">只有当审核级别设置为高时，才会出现此警告。</span><span class="sxs-lookup"><span data-stu-id="c9b84-123">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c9b84-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="c9b84-124">User Action</span></span>  
 <span data-ttu-id="c9b84-125">为避免此情况，您必须使客户端用户成为应用程序用户帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="c9b84-125">To remedy the situation, you must make the client user a member of the Application Users account.</span></span> <span data-ttu-id="c9b84-126">若要阻止以后出现此警告，您可以降低审核级别。</span><span class="sxs-lookup"><span data-stu-id="c9b84-126">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>