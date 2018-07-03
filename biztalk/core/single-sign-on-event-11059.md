---
title: 单一登录： 事件 11059 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac5b6ce7-8819-4b9d-85f7-f5dfaf940487
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a22b2a68acc6cd4be3d5cf854a4d965d897e302
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965774"
---
# <a name="single-sign-on-event-11059"></a><span data-ttu-id="93ea1-102">单一登录： 事件 11059</span><span class="sxs-lookup"><span data-stu-id="93ea1-102">Single Sign-On: Event 11059</span></span>
## <a name="details"></a><span data-ttu-id="93ea1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="93ea1-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="93ea1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="93ea1-104">Product Name</span></span>   |                                                                                                               <span data-ttu-id="93ea1-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="93ea1-105">Enterprise Single Sign-On</span></span>                                                                                                               |
| <span data-ttu-id="93ea1-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="93ea1-106">Product Version</span></span> |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    <span data-ttu-id="93ea1-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="93ea1-107">Event ID</span></span>     |                                                                                                                         <span data-ttu-id="93ea1-108">11059</span><span class="sxs-lookup"><span data-stu-id="93ea1-108">11059</span></span>                                                                                                                         |
|  <span data-ttu-id="93ea1-109">事件源</span><span class="sxs-lookup"><span data-stu-id="93ea1-109">Event Source</span></span>   |                                                                                                                        <span data-ttu-id="93ea1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="93ea1-110">ENTSSO</span></span>                                                                                                                         |
|    <span data-ttu-id="93ea1-111">组件</span><span class="sxs-lookup"><span data-stu-id="93ea1-111">Component</span></span>    |                                                                                                                          <span data-ttu-id="93ea1-112">N/A</span><span class="sxs-lookup"><span data-stu-id="93ea1-112">N/A</span></span>                                                                                                                          |
|  <span data-ttu-id="93ea1-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="93ea1-113">Symbolic Name</span></span>  |                                                                                                          <span data-ttu-id="93ea1-114">SSO_INFO_INVALID_USER_NOT_IN_GROUP</span><span class="sxs-lookup"><span data-stu-id="93ea1-114">SSO_INFO_INVALID_USER_NOT_IN_GROUP</span></span>                                                                                                           |
|  <span data-ttu-id="93ea1-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="93ea1-115">Message Text</span></span>   | <span data-ttu-id="93ea1-116">无法创建映射，因为指定的用户不是“应用程序用户”帐户的成员。%r</span><span class="sxs-lookup"><span data-stu-id="93ea1-116">A mapping could not be created because the specified user is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="93ea1-117">Windows 帐户： %1\\%2 %r</span><span class="sxs-lookup"><span data-stu-id="93ea1-117">Windows Account: %1\\%2%r</span></span><br /><br /> <span data-ttu-id="93ea1-118">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="93ea1-118">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="93ea1-119">应用程序用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="93ea1-119">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="93ea1-120">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="93ea1-120">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="93ea1-121">解释</span><span class="sxs-lookup"><span data-stu-id="93ea1-121">Explanation</span></span>  
 <span data-ttu-id="93ea1-122">无法创建映射，因为指定的用户不是“应用程序用户”帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="93ea1-122">The mapping could not be created because the specified user is not a member of the Application Users account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="93ea1-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="93ea1-123">User Action</span></span>  
 <span data-ttu-id="93ea1-124">请与 ENTSSO 管理员联系，了解成为“应用程序用户”帐户成员的相关信息。</span><span class="sxs-lookup"><span data-stu-id="93ea1-124">Contact your ENTSSO Administrator about becoming a member of the Application Users account.</span></span>