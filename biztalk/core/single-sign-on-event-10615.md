---
title: "单一登录： 事件 10615 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5dd0041-2dfd-4fd1-97ec-f9fc719a6fcc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9570290f82821a80d22826f41d4ed669e29f5b4c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10615"></a><span data-ttu-id="ee599-102">单一登录： 事件 10615</span><span class="sxs-lookup"><span data-stu-id="ee599-102">Single Sign-On: Event 10615</span></span>
## <a name="details"></a><span data-ttu-id="ee599-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ee599-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ee599-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ee599-104">Product Name</span></span>|<span data-ttu-id="ee599-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ee599-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ee599-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ee599-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ee599-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ee599-107">Event ID</span></span>|<span data-ttu-id="ee599-108">10615</span><span class="sxs-lookup"><span data-stu-id="ee599-108">10615</span></span>|  
|<span data-ttu-id="ee599-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ee599-109">Event Source</span></span>|<span data-ttu-id="ee599-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ee599-110">ENTSSO</span></span>|  
|<span data-ttu-id="ee599-111">组件</span><span class="sxs-lookup"><span data-stu-id="ee599-111">Component</span></span>|<span data-ttu-id="ee599-112">N/A</span><span class="sxs-lookup"><span data-stu-id="ee599-112">N/A</span></span>|  
|<span data-ttu-id="ee599-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ee599-113">Symbolic Name</span></span>|<span data-ttu-id="ee599-114">SSO_WARN_NO_UPDATE_TICKET_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ee599-114">SSO_WARN_NO_UPDATE_TICKET_TIMEOUT</span></span>|  
|<span data-ttu-id="ee599-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ee599-115">Message Text</span></span>|<span data-ttu-id="ee599-116">客户端用户必须是 SSO 管理员帐户的成员才能更改应用程序的票证超时值。%r</span><span class="sxs-lookup"><span data-stu-id="ee599-116">The client user must be a member of the SSO Administrators account to change the ticket time-out for an application.%r</span></span><br /><br /> <span data-ttu-id="ee599-117">客户端用户: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ee599-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="ee599-118">SSO Administrators: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ee599-118">SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="ee599-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ee599-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="ee599-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="ee599-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ee599-121">解释</span><span class="sxs-lookup"><span data-stu-id="ee599-121">Explanation</span></span>  
 <span data-ttu-id="ee599-122">客户端用户必须是 SSO 管理员帐户的成员才能更改应用程序的票证超时值。</span><span class="sxs-lookup"><span data-stu-id="ee599-122">The client user must be a member of the SSO Administrators account to change the ticket time-out for an application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ee599-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="ee599-123">User Action</span></span>  
 <span data-ttu-id="ee599-124">请系统管理员帮助您找到一个 SSO 管理员帐户成员来进行此更改。</span><span class="sxs-lookup"><span data-stu-id="ee599-124">Have your system administrator help you find a member of the SSO Administrators account to make this change.</span></span>