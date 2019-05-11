---
title: 单一登录：Event 11059 | Microsoft Docs
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
ms.openlocfilehash: b851e468db974456fe5f9eca00dc201fdfe1e12d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258771"
---
# <a name="single-sign-on-event-11059"></a><span data-ttu-id="b07da-102">单一登录：事件 11059</span><span class="sxs-lookup"><span data-stu-id="b07da-102">Single Sign-On: Event 11059</span></span>
## <a name="details"></a><span data-ttu-id="b07da-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b07da-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b07da-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b07da-104">Product Name</span></span>   |                                                                                                               <span data-ttu-id="b07da-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b07da-105">Enterprise Single Sign-On</span></span>                                                                                                               |
| <span data-ttu-id="b07da-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="b07da-106">Product Version</span></span> |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    <span data-ttu-id="b07da-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b07da-107">Event ID</span></span>     |                                                                                                                         <span data-ttu-id="b07da-108">11059</span><span class="sxs-lookup"><span data-stu-id="b07da-108">11059</span></span>                                                                                                                         |
|  <span data-ttu-id="b07da-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b07da-109">Event Source</span></span>   |                                                                                                                        <span data-ttu-id="b07da-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b07da-110">ENTSSO</span></span>                                                                                                                         |
|    <span data-ttu-id="b07da-111">组件</span><span class="sxs-lookup"><span data-stu-id="b07da-111">Component</span></span>    |                                                                                                                          <span data-ttu-id="b07da-112">不可用</span><span class="sxs-lookup"><span data-stu-id="b07da-112">N/A</span></span>                                                                                                                          |
|  <span data-ttu-id="b07da-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b07da-113">Symbolic Name</span></span>  |                                                                                                          <span data-ttu-id="b07da-114">SSO_INFO_INVALID_USER_NOT_IN_GROUP</span><span class="sxs-lookup"><span data-stu-id="b07da-114">SSO_INFO_INVALID_USER_NOT_IN_GROUP</span></span>                                                                                                           |
|  <span data-ttu-id="b07da-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b07da-115">Message Text</span></span>   | <span data-ttu-id="b07da-116">无法创建映射，因为指定的用户不是应用程序用户 account.%r 的成员</span><span class="sxs-lookup"><span data-stu-id="b07da-116">A mapping could not be created because the specified user is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="b07da-117">Windows 帐户： %1\\%2 %r</span><span class="sxs-lookup"><span data-stu-id="b07da-117">Windows Account: %1\\%2%r</span></span><br /><br /> <span data-ttu-id="b07da-118">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="b07da-118">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="b07da-119">应用程序用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="b07da-119">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="b07da-120">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="b07da-120">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b07da-121">解释</span><span class="sxs-lookup"><span data-stu-id="b07da-121">Explanation</span></span>  
 <span data-ttu-id="b07da-122">无法创建映射，因为指定的用户不是应用程序用户帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="b07da-122">The mapping could not be created because the specified user is not a member of the Application Users account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b07da-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="b07da-123">User Action</span></span>  
 <span data-ttu-id="b07da-124">与 ENTSSO 管理员如何成为应用程序用户帐户的成员联系。</span><span class="sxs-lookup"><span data-stu-id="b07da-124">Contact your ENTSSO Administrator about becoming a member of the Application Users account.</span></span>