---
title: 单一登录： 事件 10615 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5dd0041-2dfd-4fd1-97ec-f9fc719a6fcc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86b99f901ba60749386d055ce771beed225e4a18
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008462"
---
# <a name="single-sign-on-event-10615"></a><span data-ttu-id="3aee7-102">单一登录： 事件 10615</span><span class="sxs-lookup"><span data-stu-id="3aee7-102">Single Sign-On: Event 10615</span></span>
## <a name="details"></a><span data-ttu-id="3aee7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3aee7-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3aee7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3aee7-104">Product Name</span></span>   |                                                                                                                <span data-ttu-id="3aee7-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="3aee7-105">Enterprise Single Sign-On</span></span>                                                                                                                |
| <span data-ttu-id="3aee7-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="3aee7-106">Product Version</span></span> |                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                |
|    <span data-ttu-id="3aee7-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3aee7-107">Event ID</span></span>     |                                                                                                                          <span data-ttu-id="3aee7-108">10615</span><span class="sxs-lookup"><span data-stu-id="3aee7-108">10615</span></span>                                                                                                                          |
|  <span data-ttu-id="3aee7-109">事件源</span><span class="sxs-lookup"><span data-stu-id="3aee7-109">Event Source</span></span>   |                                                                                                                         <span data-ttu-id="3aee7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3aee7-110">ENTSSO</span></span>                                                                                                                          |
|    <span data-ttu-id="3aee7-111">组件</span><span class="sxs-lookup"><span data-stu-id="3aee7-111">Component</span></span>    |                                                                                                                           <span data-ttu-id="3aee7-112">N/A</span><span class="sxs-lookup"><span data-stu-id="3aee7-112">N/A</span></span>                                                                                                                           |
|  <span data-ttu-id="3aee7-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="3aee7-113">Symbolic Name</span></span>  |                                                                                                            <span data-ttu-id="3aee7-114">SSO_WARN_NO_UPDATE_TICKET_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3aee7-114">SSO_WARN_NO_UPDATE_TICKET_TIMEOUT</span></span>                                                                                                            |
|  <span data-ttu-id="3aee7-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="3aee7-115">Message Text</span></span>   | <span data-ttu-id="3aee7-116">客户端用户必须是 SSO 管理员帐户的成员才能更改应用程序的票证超时值。%r</span><span class="sxs-lookup"><span data-stu-id="3aee7-116">The client user must be a member of the SSO Administrators account to change the ticket time-out for an application.%r</span></span><br /><br /> <span data-ttu-id="3aee7-117">客户端用户: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3aee7-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="3aee7-118">SSO Administrators: %2 %r</span><span class="sxs-lookup"><span data-stu-id="3aee7-118">SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="3aee7-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="3aee7-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="3aee7-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="3aee7-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3aee7-121">解释</span><span class="sxs-lookup"><span data-stu-id="3aee7-121">Explanation</span></span>  
 <span data-ttu-id="3aee7-122">客户端用户必须是 SSO 管理员帐户的成员才能更改应用程序的票证超时值。</span><span class="sxs-lookup"><span data-stu-id="3aee7-122">The client user must be a member of the SSO Administrators account to change the ticket time-out for an application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3aee7-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="3aee7-123">User Action</span></span>  
 <span data-ttu-id="3aee7-124">请系统管理员帮助您找到一个 SSO 管理员帐户成员来进行此更改。</span><span class="sxs-lookup"><span data-stu-id="3aee7-124">Have your system administrator help you find a member of the SSO Administrators account to make this change.</span></span>