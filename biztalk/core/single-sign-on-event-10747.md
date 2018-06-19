---
title: 单一登录： 事件 10747 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63ae1ab4-0f4e-45a7-83c1-31b8037e4dd7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e26960bcba1ff3c640c88cd3fb6f5e4bd7dfceb6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270893"
---
# <a name="single-sign-on-event-10747"></a><span data-ttu-id="f84a8-102">单一登录： 事件 10747</span><span class="sxs-lookup"><span data-stu-id="f84a8-102">Single Sign-On: Event 10747</span></span>
## <a name="details"></a><span data-ttu-id="f84a8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f84a8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f84a8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f84a8-104">Product Name</span></span>|<span data-ttu-id="f84a8-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f84a8-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f84a8-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f84a8-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f84a8-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f84a8-107">Event ID</span></span>|<span data-ttu-id="f84a8-108">10747</span><span class="sxs-lookup"><span data-stu-id="f84a8-108">10747</span></span>|  
|<span data-ttu-id="f84a8-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f84a8-109">Event Source</span></span>|<span data-ttu-id="f84a8-110">N\A</span><span class="sxs-lookup"><span data-stu-id="f84a8-110">N\A</span></span>|  
|<span data-ttu-id="f84a8-111">组件</span><span class="sxs-lookup"><span data-stu-id="f84a8-111">Component</span></span>|<span data-ttu-id="f84a8-112">N\A</span><span class="sxs-lookup"><span data-stu-id="f84a8-112">N\A</span></span>|  
|<span data-ttu-id="f84a8-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f84a8-113">Symbolic Name</span></span>|<span data-ttu-id="f84a8-114">SSO_ERROR_UNKNOWN_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="f84a8-114">SSO_ERROR_UNKNOWN_NOTIFICATION</span></span>|  
|<span data-ttu-id="f84a8-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f84a8-115">Message Text</span></span>|<span data-ttu-id="f84a8-116">收到未知通知类型。%r</span><span class="sxs-lookup"><span data-stu-id="f84a8-116">An unknown notification type was received.%r</span></span><br /><br /> <span data-ttu-id="f84a8-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f84a8-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="f84a8-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f84a8-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="f84a8-119">通知类型： %3</span><span class="sxs-lookup"><span data-stu-id="f84a8-119">Notification Type: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f84a8-120">解释</span><span class="sxs-lookup"><span data-stu-id="f84a8-120">Explanation</span></span>  
 <span data-ttu-id="f84a8-121">此错误事件表明 SSO 服务检测到具有无效通知类型的内部错误。</span><span class="sxs-lookup"><span data-stu-id="f84a8-121">This Error event indicates that an internal error with an invalid notification type was detected by the SSO service.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f84a8-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="f84a8-122">User Action</span></span>  
 <span data-ttu-id="f84a8-123">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f84a8-123">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="f84a8-124">检查系统和应用程序事件日志中有相关事件。</span><span class="sxs-lookup"><span data-stu-id="f84a8-124">Check the system and application event logs for associated events.</span></span>  
  
 <span data-ttu-id="f84a8-125">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="f84a8-125">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="f84a8-126">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="f84a8-126">Using SSO</span></span>](../core/using-sso.md)