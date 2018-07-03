---
title: 单一登录： 事件 10575 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a691812-433c-42ba-a225-873ad1bfee99
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93ae664da9f4f9a36c82cdec2dea0edeeac6bdeb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968558"
---
# <a name="single-sign-on-event-10575"></a><span data-ttu-id="dd915-102">单一登录： 事件 10575</span><span class="sxs-lookup"><span data-stu-id="dd915-102">Single Sign-On: Event 10575</span></span>
## <a name="details"></a><span data-ttu-id="dd915-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="dd915-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="dd915-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="dd915-104">Product Name</span></span>   |                                                                                     <span data-ttu-id="dd915-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="dd915-105">Enterprise Single Sign-On</span></span>                                                                                     |
| <span data-ttu-id="dd915-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="dd915-106">Product Version</span></span> |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    <span data-ttu-id="dd915-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="dd915-107">Event ID</span></span>     |                                                                                               <span data-ttu-id="dd915-108">10575</span><span class="sxs-lookup"><span data-stu-id="dd915-108">10575</span></span>                                                                                               |
|  <span data-ttu-id="dd915-109">事件源</span><span class="sxs-lookup"><span data-stu-id="dd915-109">Event Source</span></span>   |                                                                                              <span data-ttu-id="dd915-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="dd915-110">ENTSSO</span></span>                                                                                               |
|    <span data-ttu-id="dd915-111">组件</span><span class="sxs-lookup"><span data-stu-id="dd915-111">Component</span></span>    |                                                                                                <span data-ttu-id="dd915-112">N/A</span><span class="sxs-lookup"><span data-stu-id="dd915-112">N/A</span></span>                                                                                                |
|  <span data-ttu-id="dd915-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="dd915-113">Symbolic Name</span></span>  |                                                                                  <span data-ttu-id="dd915-114">SSO_INFO_CHANGED_SECRET_SERVER</span><span class="sxs-lookup"><span data-stu-id="dd915-114">SSO_INFO_CHANGED_SECRET_SERVER</span></span>                                                                                   |
|  <span data-ttu-id="dd915-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="dd915-115">Message Text</span></span>   | <span data-ttu-id="dd915-116">已更新密钥服务器名称。%r</span><span class="sxs-lookup"><span data-stu-id="dd915-116">Updated secret server name.%r</span></span><br /><br /> <span data-ttu-id="dd915-117">新的服务器: %1 %r</span><span class="sxs-lookup"><span data-stu-id="dd915-117">New Secret Server: %1%r</span></span><br /><br /> <span data-ttu-id="dd915-118">旧密钥服务器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="dd915-118">Old Secret Server: %2%r</span></span><br /><br /> <span data-ttu-id="dd915-119">跟踪 ID: %3 %r</span><span class="sxs-lookup"><span data-stu-id="dd915-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="dd915-120">客户端计算机: %4 %r</span><span class="sxs-lookup"><span data-stu-id="dd915-120">Client Computer: %4%r</span></span><br /><br /> <span data-ttu-id="dd915-121">客户端用户： %5</span><span class="sxs-lookup"><span data-stu-id="dd915-121">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="dd915-122">解释</span><span class="sxs-lookup"><span data-stu-id="dd915-122">Explanation</span></span>  
 <span data-ttu-id="dd915-123">这是信息性消息，可以用于跟踪 SSO 系统中发生的与安全有关的重要事件。</span><span class="sxs-lookup"><span data-stu-id="dd915-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="dd915-124">此消息表明密钥服务器名称已经更新。</span><span class="sxs-lookup"><span data-stu-id="dd915-124">This message states that the secret server name has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dd915-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="dd915-125">User Action</span></span>  
 <span data-ttu-id="dd915-126">不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="dd915-126">No user action is required.</span></span>