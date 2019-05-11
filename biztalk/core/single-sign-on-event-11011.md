---
title: 单一登录：事件 11011 |Microsoft Docs
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
ms.openlocfilehash: 35e22fca920554dccb36157a85419ee53993e255
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306539"
---
# <a name="single-sign-on-event-11011"></a><span data-ttu-id="9c814-102">单一登录：事件 11011</span><span class="sxs-lookup"><span data-stu-id="9c814-102">Single Sign-On: Event 11011</span></span>
## <a name="details"></a><span data-ttu-id="9c814-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9c814-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9c814-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9c814-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="9c814-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="9c814-105">Enterprise Single Sign-On</span></span>                                                                                                |
| <span data-ttu-id="9c814-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="9c814-106">Product Version</span></span> |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="9c814-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9c814-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="9c814-108">11011</span><span class="sxs-lookup"><span data-stu-id="9c814-108">11011</span></span>                                                                                                          |
|  <span data-ttu-id="9c814-109">事件源</span><span class="sxs-lookup"><span data-stu-id="9c814-109">Event Source</span></span>   |                                                                                                         <span data-ttu-id="9c814-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9c814-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="9c814-111">组件</span><span class="sxs-lookup"><span data-stu-id="9c814-111">Component</span></span>    |                                                                                                          <span data-ttu-id="9c814-112">不可用</span><span class="sxs-lookup"><span data-stu-id="9c814-112">N/A</span></span>                                                                                                           |
|  <span data-ttu-id="9c814-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="9c814-113">Symbolic Name</span></span>  |                                                                                                 <span data-ttu-id="9c814-114">SSO_WARN_NOT_APP_ADMIN</span><span class="sxs-lookup"><span data-stu-id="9c814-114">SSO_WARN_NOT_APP_ADMIN</span></span>                                                                                                 |
|  <span data-ttu-id="9c814-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="9c814-115">Message Text</span></span>   | <span data-ttu-id="9c814-116">客户端用户不是应用程序管理员 account.%r 的成员</span><span class="sxs-lookup"><span data-stu-id="9c814-116">Client user is not a member of the Application Administrators account.%r</span></span><br /><br /> <span data-ttu-id="9c814-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="9c814-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="9c814-118">客户端用户： %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="9c814-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="9c814-119">应用程序名称: %4 %r</span><span class="sxs-lookup"><span data-stu-id="9c814-119">Application Name: %4%r</span></span><br /><br /> <span data-ttu-id="9c814-120">应用程序管理员： %5</span><span class="sxs-lookup"><span data-stu-id="9c814-120">Application Administrators: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9c814-121">解释</span><span class="sxs-lookup"><span data-stu-id="9c814-121">Explanation</span></span>  
 <span data-ttu-id="9c814-122">客户端用户不是应用程序管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="9c814-122">The client user is not a member of the Application Administrators account.</span></span> <span data-ttu-id="9c814-123">审核级别设置为高时，才会显示此警告。</span><span class="sxs-lookup"><span data-stu-id="9c814-123">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9c814-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="9c814-124">User Action</span></span>  
 <span data-ttu-id="9c814-125">若要纠正这种情况，您必须使客户端用户应用程序管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="9c814-125">To remedy the situation, you must make the client user a member of the Application Administrators account.</span></span> <span data-ttu-id="9c814-126">若要停止在将来出现此警告消息，则可以降低审核级别。</span><span class="sxs-lookup"><span data-stu-id="9c814-126">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>