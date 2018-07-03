---
title: 单一登录： 事件 11036 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dad0427-83dd-42ac-b0bc-d113abdc8e89
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f19a3ff1d35d3c2de04ec9c3846de94d7a2657a7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013910"
---
# <a name="single-sign-on-event-11036"></a><span data-ttu-id="bf2bb-102">单一登录： 事件 11036</span><span class="sxs-lookup"><span data-stu-id="bf2bb-102">Single Sign-On: Event 11036</span></span>
## <a name="details"></a><span data-ttu-id="bf2bb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="bf2bb-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bf2bb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="bf2bb-104">Product Name</span></span>   |                                                                                                                                                                <span data-ttu-id="bf2bb-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="bf2bb-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                |
| <span data-ttu-id="bf2bb-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="bf2bb-106">Product Version</span></span> |                                                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                |
|    <span data-ttu-id="bf2bb-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="bf2bb-107">Event ID</span></span>     |                                                                                                                                                                          <span data-ttu-id="bf2bb-108">11036</span><span class="sxs-lookup"><span data-stu-id="bf2bb-108">11036</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="bf2bb-109">事件源</span><span class="sxs-lookup"><span data-stu-id="bf2bb-109">Event Source</span></span>   |                                                                                                                                                                         <span data-ttu-id="bf2bb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bf2bb-110">ENTSSO</span></span>                                                                                                                                                                          |
|    <span data-ttu-id="bf2bb-111">组件</span><span class="sxs-lookup"><span data-stu-id="bf2bb-111">Component</span></span>    |                                                                                                                                                                           <span data-ttu-id="bf2bb-112">N/A</span><span class="sxs-lookup"><span data-stu-id="bf2bb-112">N/A</span></span>                                                                                                                                                                           |
|  <span data-ttu-id="bf2bb-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="bf2bb-113">Symbolic Name</span></span>  |                                                                                                                                                         <span data-ttu-id="bf2bb-114">SSO_INFO_PS_WIN_CHANGE_ADAPTER_NO_SYNC</span><span class="sxs-lookup"><span data-stu-id="bf2bb-114">SSO_INFO_PS_WIN_CHANGE_ADAPTER_NO_SYNC</span></span>                                                                                                                                                          |
|  <span data-ttu-id="bf2bb-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="bf2bb-115">Message Text</span></span>   | <span data-ttu-id="bf2bb-116">Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="bf2bb-116">Windows password change.</span></span> <span data-ttu-id="bf2bb-117">已检测到此 Windows 帐户的映射，但是被忽略，原因是为此应用程序配置的适配器不支持将密码同步到外部系统。%r</span><span class="sxs-lookup"><span data-stu-id="bf2bb-117">A mapping for this Windows account has been detected but ignored because the adapter configured for this application does not support password sync to external systems.%r</span></span><br /><br /> <span data-ttu-id="bf2bb-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="bf2bb-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="bf2bb-119">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="bf2bb-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="bf2bb-120">应用程序: %3 %r</span><span class="sxs-lookup"><span data-stu-id="bf2bb-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="bf2bb-121">适配器: %4 %r</span><span class="sxs-lookup"><span data-stu-id="bf2bb-121">Adapter: %4%r</span></span><br /><br /> <span data-ttu-id="bf2bb-122">客户端用户： %5</span><span class="sxs-lookup"><span data-stu-id="bf2bb-122">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="bf2bb-123">解释</span><span class="sxs-lookup"><span data-stu-id="bf2bb-123">Explanation</span></span>  
 <span data-ttu-id="bf2bb-124">已检测到此 Windows 帐户的映射，但是被忽略，原因是为此应用程序配置的适配器不支持将密码同步到外部系统。</span><span class="sxs-lookup"><span data-stu-id="bf2bb-124">A mapping for this Windows account has been detected but ignored because the adapter configured for this application does not support password sync to external systems.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bf2bb-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="bf2bb-125">User Action</span></span>  
 <span data-ttu-id="bf2bb-126">检查适配器配置。</span><span class="sxs-lookup"><span data-stu-id="bf2bb-126">Check your adapter configuration.</span></span>  
  
 <span data-ttu-id="bf2bb-127">有关密码同步的信息，请参阅[密码同步](../core/password-synchronization2.md)。</span><span class="sxs-lookup"><span data-stu-id="bf2bb-127">For information on Password Sync, see [Password Synchronization](../core/password-synchronization2.md).</span></span>