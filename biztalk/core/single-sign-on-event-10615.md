---
title: 单一登录：Event 10615 | Microsoft Docs
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
ms.openlocfilehash: adece23afc79fcff2d4c0168aaee4b38819f5e50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397690"
---
# <a name="single-sign-on-event-10615"></a><span data-ttu-id="d5292-102">单一登录：事件 10615</span><span class="sxs-lookup"><span data-stu-id="d5292-102">Single Sign-On: Event 10615</span></span>
## <a name="details"></a><span data-ttu-id="d5292-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d5292-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d5292-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d5292-104">Product Name</span></span>   |                                                                                                                <span data-ttu-id="d5292-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="d5292-105">Enterprise Single Sign-On</span></span>                                                                                                                |
| <span data-ttu-id="d5292-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="d5292-106">Product Version</span></span> |                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                |
|    <span data-ttu-id="d5292-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d5292-107">Event ID</span></span>     |                                                                                                                          <span data-ttu-id="d5292-108">10615</span><span class="sxs-lookup"><span data-stu-id="d5292-108">10615</span></span>                                                                                                                          |
|  <span data-ttu-id="d5292-109">事件源</span><span class="sxs-lookup"><span data-stu-id="d5292-109">Event Source</span></span>   |                                                                                                                         <span data-ttu-id="d5292-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d5292-110">ENTSSO</span></span>                                                                                                                          |
|    <span data-ttu-id="d5292-111">组件</span><span class="sxs-lookup"><span data-stu-id="d5292-111">Component</span></span>    |                                                                                                                           <span data-ttu-id="d5292-112">不可用</span><span class="sxs-lookup"><span data-stu-id="d5292-112">N/A</span></span>                                                                                                                           |
|  <span data-ttu-id="d5292-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="d5292-113">Symbolic Name</span></span>  |                                                                                                            <span data-ttu-id="d5292-114">SSO_WARN_NO_UPDATE_TICKET_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d5292-114">SSO_WARN_NO_UPDATE_TICKET_TIMEOUT</span></span>                                                                                                            |
|  <span data-ttu-id="d5292-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="d5292-115">Message Text</span></span>   | <span data-ttu-id="d5292-116">客户端用户必须是 SSO 管理员帐户的成员，才能更改 application.%r 的票证超时值</span><span class="sxs-lookup"><span data-stu-id="d5292-116">The client user must be a member of the SSO Administrators account to change the ticket time-out for an application.%r</span></span><br /><br /> <span data-ttu-id="d5292-117">客户端用户: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d5292-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="d5292-118">SSO Administrators: %2 %r</span><span class="sxs-lookup"><span data-stu-id="d5292-118">SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="d5292-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="d5292-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="d5292-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="d5292-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d5292-121">解释</span><span class="sxs-lookup"><span data-stu-id="d5292-121">Explanation</span></span>  
 <span data-ttu-id="d5292-122">客户端用户必须是 SSO 管理员帐户的成员，才能更改应用程序的票证超时值。</span><span class="sxs-lookup"><span data-stu-id="d5292-122">The client user must be a member of the SSO Administrators account to change the ticket time-out for an application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d5292-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="d5292-123">User Action</span></span>  
 <span data-ttu-id="d5292-124">具有系统管理员帮助您找到要进行此更改 SSO 管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="d5292-124">Have your system administrator help you find a member of the SSO Administrators account to make this change.</span></span>