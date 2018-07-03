---
title: 单一登录： 事件 11033 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eed8e984-2b6c-4a9e-8603-175fdcabeb0a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25db9678dbef67672c2d86273f8938e94de09000
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011718"
---
# <a name="single-sign-on-event-11033"></a><span data-ttu-id="2eddb-102">单一登录： 事件 11033</span><span class="sxs-lookup"><span data-stu-id="2eddb-102">Single Sign-On: Event 11033</span></span>
## <a name="details"></a><span data-ttu-id="2eddb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2eddb-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2eddb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2eddb-104">Product Name</span></span>   |                                                                                                                                   <span data-ttu-id="2eddb-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="2eddb-105">Enterprise Single Sign-On</span></span>                                                                                                                                   |
| <span data-ttu-id="2eddb-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="2eddb-106">Product Version</span></span> |                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                   |
|    <span data-ttu-id="2eddb-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2eddb-107">Event ID</span></span>     |                                                                                                                                             <span data-ttu-id="2eddb-108">11033</span><span class="sxs-lookup"><span data-stu-id="2eddb-108">11033</span></span>                                                                                                                                             |
|  <span data-ttu-id="2eddb-109">事件源</span><span class="sxs-lookup"><span data-stu-id="2eddb-109">Event Source</span></span>   |                                                                                                                                            <span data-ttu-id="2eddb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2eddb-110">ENTSSO</span></span>                                                                                                                                             |
|    <span data-ttu-id="2eddb-111">组件</span><span class="sxs-lookup"><span data-stu-id="2eddb-111">Component</span></span>    |                                                                                                                                              <span data-ttu-id="2eddb-112">N/A</span><span class="sxs-lookup"><span data-stu-id="2eddb-112">N/A</span></span>                                                                                                                                              |
|  <span data-ttu-id="2eddb-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="2eddb-113">Symbolic Name</span></span>  |                                                                                                                              <span data-ttu-id="2eddb-114">SSO_INFO_PS_WIN_CHANGE_APP_DISABLED</span><span class="sxs-lookup"><span data-stu-id="2eddb-114">SSO_INFO_PS_WIN_CHANGE_APP_DISABLED</span></span>                                                                                                                              |
|  <span data-ttu-id="2eddb-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="2eddb-115">Message Text</span></span>   | <span data-ttu-id="2eddb-116">Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="2eddb-116">Windows password change.</span></span> <span data-ttu-id="2eddb-117">已检测到但被忽略，因为应用程序被 disabled.%r 此 Windows 帐户的映射</span><span class="sxs-lookup"><span data-stu-id="2eddb-117">A mapping for this Windows account has been detected but ignored because the application is disabled.%r</span></span><br /><br /> <span data-ttu-id="2eddb-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="2eddb-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="2eddb-119">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="2eddb-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="2eddb-120">应用程序: %3 %r</span><span class="sxs-lookup"><span data-stu-id="2eddb-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="2eddb-121">外部帐户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="2eddb-121">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="2eddb-122">客户端用户： %5</span><span class="sxs-lookup"><span data-stu-id="2eddb-122">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="2eddb-123">解释</span><span class="sxs-lookup"><span data-stu-id="2eddb-123">Explanation</span></span>  
 <span data-ttu-id="2eddb-124">已检测到此 Windows 帐户的映射，但被忽略，因为禁用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="2eddb-124">A mapping for this Windows account has been detected but ignored because the application is disabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2eddb-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="2eddb-125">User Action</span></span>  
 <span data-ttu-id="2eddb-126">若要使应用程序，请参阅[如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md)。</span><span class="sxs-lookup"><span data-stu-id="2eddb-126">To enable the application, see [How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md).</span></span>