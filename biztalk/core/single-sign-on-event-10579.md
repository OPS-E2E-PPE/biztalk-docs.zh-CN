---
title: 单一登录：Event 10579 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64e18f6d-9dda-49bf-a901-bb28f4cd9a84
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15a1ab9bc79e04c3e87a5db7b09770e3f87edd95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303444"
---
# <a name="single-sign-on-event-10579"></a><span data-ttu-id="dcf5c-102">单一登录：事件 10579</span><span class="sxs-lookup"><span data-stu-id="dcf5c-102">Single Sign-On: Event 10579</span></span>
## <a name="details"></a><span data-ttu-id="dcf5c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="dcf5c-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="dcf5c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="dcf5c-104">Product Name</span></span>   |                                                                                                          <span data-ttu-id="dcf5c-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="dcf5c-105">Enterprise Single Sign-On</span></span>                                                                                                           |
| <span data-ttu-id="dcf5c-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="dcf5c-106">Product Version</span></span> |                                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                          |
|    <span data-ttu-id="dcf5c-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="dcf5c-107">Event ID</span></span>     |                                                                                                                    <span data-ttu-id="dcf5c-108">10579</span><span class="sxs-lookup"><span data-stu-id="dcf5c-108">10579</span></span>                                                                                                                     |
|  <span data-ttu-id="dcf5c-109">事件源</span><span class="sxs-lookup"><span data-stu-id="dcf5c-109">Event Source</span></span>   |                                                                                                                    <span data-ttu-id="dcf5c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="dcf5c-110">ENTSSO</span></span>                                                                                                                    |
|    <span data-ttu-id="dcf5c-111">组件</span><span class="sxs-lookup"><span data-stu-id="dcf5c-111">Component</span></span>    |                                                                                                                     <span data-ttu-id="dcf5c-112">不可用</span><span class="sxs-lookup"><span data-stu-id="dcf5c-112">N/A</span></span>                                                                                                                      |
|  <span data-ttu-id="dcf5c-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="dcf5c-113">Symbolic Name</span></span>  |                                                                                                       <span data-ttu-id="dcf5c-114">SSO_INFO_CHANGED_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="dcf5c-114">SSO_INFO_CHANGED_APP_ADMIN_GROUP</span></span>                                                                                                       |
|  <span data-ttu-id="dcf5c-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="dcf5c-115">Message Text</span></span>   | <span data-ttu-id="dcf5c-116">更新应用程序 Administrators account.%r</span><span class="sxs-lookup"><span data-stu-id="dcf5c-116">Updated Application Administrators account.%r</span></span><br /><br /> <span data-ttu-id="dcf5c-117">新的 Application Administrators: %1 %r</span><span class="sxs-lookup"><span data-stu-id="dcf5c-117">New Application Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="dcf5c-118">旧的 Application Administrators: %2 %r</span><span class="sxs-lookup"><span data-stu-id="dcf5c-118">Old Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="dcf5c-119">跟踪 ID: %3 %r</span><span class="sxs-lookup"><span data-stu-id="dcf5c-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="dcf5c-120">客户端用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="dcf5c-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="dcf5c-121">应用程序名称： %5</span><span class="sxs-lookup"><span data-stu-id="dcf5c-121">Application Name: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="dcf5c-122">解释</span><span class="sxs-lookup"><span data-stu-id="dcf5c-122">Explanation</span></span>  
 <span data-ttu-id="dcf5c-123">这是一条信息性消息，也可用于跟踪 SSO 系统中的发生的与安全相关的重要事件。</span><span class="sxs-lookup"><span data-stu-id="dcf5c-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="dcf5c-124">此消息表明已更新应用程序管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="dcf5c-124">This message states that the Application Administrators account has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dcf5c-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="dcf5c-125">User Action</span></span>  
 <span data-ttu-id="dcf5c-126">不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="dcf5c-126">No user action is required.</span></span>