---
title: 单一登录：事件 11012 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 252bedc8-8dc3-4962-b078-465f9b064ead
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3775772225521941f03c213aa5b1d49ff8bcd04f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267281"
---
# <a name="single-sign-on-event-11012"></a><span data-ttu-id="31865-102">单一登录：事件 11012</span><span class="sxs-lookup"><span data-stu-id="31865-102">Single Sign-On: Event 11012</span></span>
## <a name="details"></a><span data-ttu-id="31865-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="31865-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="31865-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="31865-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="31865-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="31865-105">Enterprise Single Sign-On</span></span>                                                                                                |
| <span data-ttu-id="31865-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="31865-106">Product Version</span></span> |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="31865-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="31865-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="31865-108">11012</span><span class="sxs-lookup"><span data-stu-id="31865-108">11012</span></span>                                                                                                          |
|  <span data-ttu-id="31865-109">事件源</span><span class="sxs-lookup"><span data-stu-id="31865-109">Event Source</span></span>   |                                                                                                         <span data-ttu-id="31865-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="31865-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="31865-111">组件</span><span class="sxs-lookup"><span data-stu-id="31865-111">Component</span></span>    |                                                                                                          <span data-ttu-id="31865-112">不可用</span><span class="sxs-lookup"><span data-stu-id="31865-112">N/A</span></span>                                                                                                           |
|  <span data-ttu-id="31865-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="31865-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="31865-114">SSO_WARN_NOT_APP_ADMIN_ADMIN_SAME</span><span class="sxs-lookup"><span data-stu-id="31865-114">SSO_WARN_NOT_APP_ADMIN_ADMIN_SAME</span></span>                                                                                            |
|  <span data-ttu-id="31865-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="31865-115">Message Text</span></span>   | <span data-ttu-id="31865-116">客户端用户不是应用程序管理员 account.%r 的成员</span><span class="sxs-lookup"><span data-stu-id="31865-116">Client user is not a member of the Application Administrators account.%r</span></span><br /><br /> <span data-ttu-id="31865-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="31865-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="31865-118">客户端用户： %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="31865-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="31865-119">应用程序名称: %4 %r</span><span class="sxs-lookup"><span data-stu-id="31865-119">Application Name: %4%r</span></span><br /><br /> <span data-ttu-id="31865-120">应用程序管理员： %5</span><span class="sxs-lookup"><span data-stu-id="31865-120">Application Administrators: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="31865-121">解释</span><span class="sxs-lookup"><span data-stu-id="31865-121">Explanation</span></span>  
 <span data-ttu-id="31865-122">客户端用户不是应用程序管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="31865-122">The client user is not a member of the Application Administrators account.</span></span> <span data-ttu-id="31865-123">审核级别设置为高时，才会显示此警告。</span><span class="sxs-lookup"><span data-stu-id="31865-123">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="31865-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="31865-124">User Action</span></span>  
 <span data-ttu-id="31865-125">若要纠正这种情况，您必须使客户端用户应用程序管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="31865-125">To remedy the situation, you must make the client user a member of the Application Administrators account.</span></span> <span data-ttu-id="31865-126">若要停止在将来出现此警告消息，则可以降低审核级别。</span><span class="sxs-lookup"><span data-stu-id="31865-126">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>