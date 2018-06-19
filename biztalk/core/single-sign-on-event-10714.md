---
title: 单一登录： 事件 10714 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59d8509f-cc3e-40fa-ba3d-3dcb0e73c67a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba63ab9197dcf9629f03f3d6c96f064345aaa46e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271373"
---
# <a name="single-sign-on-event-10714"></a><span data-ttu-id="e23e1-102">单一登录： 事件 10714</span><span class="sxs-lookup"><span data-stu-id="e23e1-102">Single Sign-On: Event 10714</span></span>
## <a name="details"></a><span data-ttu-id="e23e1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e23e1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e23e1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e23e1-104">Product Name</span></span>|<span data-ttu-id="e23e1-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e23e1-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="e23e1-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e23e1-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="e23e1-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e23e1-107">Event ID</span></span>|<span data-ttu-id="e23e1-108">10714</span><span class="sxs-lookup"><span data-stu-id="e23e1-108">10714</span></span>|  
|<span data-ttu-id="e23e1-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e23e1-109">Event Source</span></span>|<span data-ttu-id="e23e1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e23e1-110">ENTSSO</span></span>|  
|<span data-ttu-id="e23e1-111">组件</span><span class="sxs-lookup"><span data-stu-id="e23e1-111">Component</span></span>|<span data-ttu-id="e23e1-112">N\A</span><span class="sxs-lookup"><span data-stu-id="e23e1-112">N\A</span></span>|  
|<span data-ttu-id="e23e1-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e23e1-113">Symbolic Name</span></span>|<span data-ttu-id="e23e1-114">SSO_WARN_PS_NOTIFICATION_RETRIES_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="e23e1-114">SSO_WARN_PS_NOTIFICATION_RETRIES_EXPIRED</span></span>|  
|<span data-ttu-id="e23e1-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e23e1-115">Message Text</span></span>|<span data-ttu-id="e23e1-116">重试过期，丢弃通知。%r</span><span class="sxs-lookup"><span data-stu-id="e23e1-116">Retries expired, discarding notification.%r</span></span><br /><br /> <span data-ttu-id="e23e1-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e23e1-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="e23e1-118">适配器： %2</span><span class="sxs-lookup"><span data-stu-id="e23e1-118">Adapter: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e23e1-119">解释</span><span class="sxs-lookup"><span data-stu-id="e23e1-119">Explanation</span></span>  
 <span data-ttu-id="e23e1-120">此警告事件表明密码同步通知重试已过期，并已丢弃通知。</span><span class="sxs-lookup"><span data-stu-id="e23e1-120">This Warning event indicates that the Password Sync notification retries have expired, and the notification has been discarded.</span></span>  
  
 <span data-ttu-id="e23e1-121">将密码更改（从 Windows 到外部系统）传送到密码同步适配器时，密码同步适配器确认已经成功处理了密码更改。</span><span class="sxs-lookup"><span data-stu-id="e23e1-121">When a password change (from Windows to an external system) is delivered to a password sync adapter, the password sync adapter acknowledges that it has successfully processed the password change.</span></span> <span data-ttu-id="e23e1-122">如果在指定时间段内未发生密码更改，或者如果在更改期间发生了其他问题，则密码更改将再次传送到密码同步适配器。</span><span class="sxs-lookup"><span data-stu-id="e23e1-122">If the password change does not occur within a specified amount of time, or if another problem occurs during the change, the password change is delivered to the password sync adapter again.</span></span> <span data-ttu-id="e23e1-123">只能在有限次数（最大重试次数）内完成此操作，然后将丢弃密码更改通知。</span><span class="sxs-lookup"><span data-stu-id="e23e1-123">This is done a limited number of times (max retries) and then the password change notification is discarded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e23e1-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="e23e1-124">User Action</span></span>  
 <span data-ttu-id="e23e1-125">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e23e1-125">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="e23e1-126">检查有相关事件的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="e23e1-126">Check System and Application event logs for associated events.</span></span>  
  
 <span data-ttu-id="e23e1-127">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="e23e1-127">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="e23e1-128">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="e23e1-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="e23e1-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="e23e1-129">Password Synchronization</span></span>](../core/password-synchronization2.md)