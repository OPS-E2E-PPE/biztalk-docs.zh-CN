---
title: 单一登录： 事件 11011 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4ef430a-fb3b-4bf7-936f-a866262a6c3a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75ba98bf7fb3f57fdf9ce082028f2fff9ea7f618
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972966"
---
# <a name="single-sign-on-event-11011"></a><span data-ttu-id="10c19-102">单一登录： 事件 11011</span><span class="sxs-lookup"><span data-stu-id="10c19-102">Single Sign-On: Event 11011</span></span>
## <a name="details"></a><span data-ttu-id="10c19-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="10c19-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="10c19-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="10c19-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="10c19-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="10c19-105">Enterprise Single Sign-On</span></span>                                                                                                |
| <span data-ttu-id="10c19-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="10c19-106">Product Version</span></span> |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="10c19-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="10c19-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="10c19-108">11011</span><span class="sxs-lookup"><span data-stu-id="10c19-108">11011</span></span>                                                                                                          |
|  <span data-ttu-id="10c19-109">事件源</span><span class="sxs-lookup"><span data-stu-id="10c19-109">Event Source</span></span>   |                                                                                                         <span data-ttu-id="10c19-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="10c19-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="10c19-111">组件</span><span class="sxs-lookup"><span data-stu-id="10c19-111">Component</span></span>    |                                                                                                          <span data-ttu-id="10c19-112">N/A</span><span class="sxs-lookup"><span data-stu-id="10c19-112">N/A</span></span>                                                                                                           |
|  <span data-ttu-id="10c19-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="10c19-113">Symbolic Name</span></span>  |                                                                                                 <span data-ttu-id="10c19-114">SSO_WARN_NOT_APP_ADMIN</span><span class="sxs-lookup"><span data-stu-id="10c19-114">SSO_WARN_NOT_APP_ADMIN</span></span>                                                                                                 |
|  <span data-ttu-id="10c19-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="10c19-115">Message Text</span></span>   | <span data-ttu-id="10c19-116">客户端用户不是应用程序管理员帐户的成员。%r</span><span class="sxs-lookup"><span data-stu-id="10c19-116">Client user is not a member of the Application Administrators account.%r</span></span><br /><br /> <span data-ttu-id="10c19-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="10c19-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="10c19-118">客户端用户： %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="10c19-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="10c19-119">应用程序名称: %4 %r</span><span class="sxs-lookup"><span data-stu-id="10c19-119">Application Name: %4%r</span></span><br /><br /> <span data-ttu-id="10c19-120">应用程序管理员： %5</span><span class="sxs-lookup"><span data-stu-id="10c19-120">Application Administrators: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="10c19-121">解释</span><span class="sxs-lookup"><span data-stu-id="10c19-121">Explanation</span></span>  
 <span data-ttu-id="10c19-122">客户端用户不是应用程序管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="10c19-122">The client user is not a member of the Application Administrators account.</span></span> <span data-ttu-id="10c19-123">只有当审核级别设置为高时，才会出现此警告。</span><span class="sxs-lookup"><span data-stu-id="10c19-123">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="10c19-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="10c19-124">User Action</span></span>  
 <span data-ttu-id="10c19-125">若要修复此情形，您必须使客户端用户成为应用程序管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="10c19-125">To remedy the situation, you must make the client user a member of the Application Administrators account.</span></span> <span data-ttu-id="10c19-126">若要阻止以后出现此警告，您可以降低审核级别。</span><span class="sxs-lookup"><span data-stu-id="10c19-126">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>