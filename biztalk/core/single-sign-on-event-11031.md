---
title: 单一登录： 事件 11031 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ecd24c2-e251-4eb9-b3ca-ec0f095bb23a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f90be8f631bbd9503de3401bc84d27af32aa991a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015078"
---
# <a name="single-sign-on-event-11031"></a><span data-ttu-id="b9884-102">单一登录： 事件 11031</span><span class="sxs-lookup"><span data-stu-id="b9884-102">Single Sign-On: Event 11031</span></span>
## <a name="details"></a><span data-ttu-id="b9884-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b9884-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b9884-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b9884-104">Product Name</span></span>   |                                                                                                                                <span data-ttu-id="b9884-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b9884-105">Enterprise Single Sign-On</span></span>                                                                                                                                |
| <span data-ttu-id="b9884-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="b9884-106">Product Version</span></span> |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                |
|    <span data-ttu-id="b9884-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b9884-107">Event ID</span></span>     |                                                                                                                                          <span data-ttu-id="b9884-108">11031</span><span class="sxs-lookup"><span data-stu-id="b9884-108">11031</span></span>                                                                                                                                          |
|  <span data-ttu-id="b9884-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b9884-109">Event Source</span></span>   |                                                                                                                                         <span data-ttu-id="b9884-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b9884-110">ENTSSO</span></span>                                                                                                                                          |
|    <span data-ttu-id="b9884-111">组件</span><span class="sxs-lookup"><span data-stu-id="b9884-111">Component</span></span>    |                                                                                                                                           <span data-ttu-id="b9884-112">N/A</span><span class="sxs-lookup"><span data-stu-id="b9884-112">N/A</span></span>                                                                                                                                           |
|  <span data-ttu-id="b9884-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b9884-113">Symbolic Name</span></span>  |                                                                                                                         <span data-ttu-id="b9884-114">SSO_INFO_PS_WIN_CHANGE_INVALID_MAPPING</span><span class="sxs-lookup"><span data-stu-id="b9884-114">SSO_INFO_PS_WIN_CHANGE_INVALID_MAPPING</span></span>                                                                                                                          |
|  <span data-ttu-id="b9884-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b9884-115">Message Text</span></span>   | <span data-ttu-id="b9884-116">Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="b9884-116">Windows password change.</span></span> <span data-ttu-id="b9884-117">已检测到此 Windows 帐户的映射，但此映射由于不再有效而被忽略。%r</span><span class="sxs-lookup"><span data-stu-id="b9884-117">A mapping for this Windows account has been detected but ignored because it is no longer valid.%r</span></span><br /><br /> <span data-ttu-id="b9884-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="b9884-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="b9884-119">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="b9884-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="b9884-120">应用程序: %3 %r</span><span class="sxs-lookup"><span data-stu-id="b9884-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="b9884-121">外部帐户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="b9884-121">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="b9884-122">客户端用户： %5</span><span class="sxs-lookup"><span data-stu-id="b9884-122">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b9884-123">解释</span><span class="sxs-lookup"><span data-stu-id="b9884-123">Explanation</span></span>  
 <span data-ttu-id="b9884-124">可能是因为 Windows 帐户存在且有效，但不在应用程序用户帐户中。</span><span class="sxs-lookup"><span data-stu-id="b9884-124">It may be that the Windows account exists and is valid, but is not in the Application Users account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b9884-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="b9884-125">User Action</span></span>  
 <span data-ttu-id="b9884-126">删除映射，然后尝试重新创建该映射。</span><span class="sxs-lookup"><span data-stu-id="b9884-126">Delete the mapping and try to recreate it.</span></span>