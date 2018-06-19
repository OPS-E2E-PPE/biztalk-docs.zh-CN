---
title: 单一登录： 事件 11036 |Microsoft 文档
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
ms.openlocfilehash: 63b11005248471c222f63c88439a0e60571b341e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277149"
---
# <a name="single-sign-on-event-11036"></a><span data-ttu-id="317b7-102">单一登录： 事件 11036</span><span class="sxs-lookup"><span data-stu-id="317b7-102">Single Sign-On: Event 11036</span></span>
## <a name="details"></a><span data-ttu-id="317b7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="317b7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="317b7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="317b7-104">Product Name</span></span>|<span data-ttu-id="317b7-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="317b7-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="317b7-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="317b7-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="317b7-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="317b7-107">Event ID</span></span>|<span data-ttu-id="317b7-108">11036</span><span class="sxs-lookup"><span data-stu-id="317b7-108">11036</span></span>|  
|<span data-ttu-id="317b7-109">事件源</span><span class="sxs-lookup"><span data-stu-id="317b7-109">Event Source</span></span>|<span data-ttu-id="317b7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="317b7-110">ENTSSO</span></span>|  
|<span data-ttu-id="317b7-111">组件</span><span class="sxs-lookup"><span data-stu-id="317b7-111">Component</span></span>|<span data-ttu-id="317b7-112">N/A</span><span class="sxs-lookup"><span data-stu-id="317b7-112">N/A</span></span>|  
|<span data-ttu-id="317b7-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="317b7-113">Symbolic Name</span></span>|<span data-ttu-id="317b7-114">SSO_INFO_PS_WIN_CHANGE_ADAPTER_NO_SYNC</span><span class="sxs-lookup"><span data-stu-id="317b7-114">SSO_INFO_PS_WIN_CHANGE_ADAPTER_NO_SYNC</span></span>|  
|<span data-ttu-id="317b7-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="317b7-115">Message Text</span></span>|<span data-ttu-id="317b7-116">Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="317b7-116">Windows password change.</span></span> <span data-ttu-id="317b7-117">已检测到此 Windows 帐户的映射，但是被忽略，原因是为此应用程序配置的适配器不支持将密码同步到外部系统。%r</span><span class="sxs-lookup"><span data-stu-id="317b7-117">A mapping for this Windows account has been detected but ignored because the adapter configured for this application does not support password sync to external systems.%r</span></span><br /><br /> <span data-ttu-id="317b7-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="317b7-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="317b7-119">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="317b7-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="317b7-120">应用程序: %3 %r</span><span class="sxs-lookup"><span data-stu-id="317b7-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="317b7-121">适配器: %4 %r</span><span class="sxs-lookup"><span data-stu-id="317b7-121">Adapter: %4%r</span></span><br /><br /> <span data-ttu-id="317b7-122">客户端用户： %5</span><span class="sxs-lookup"><span data-stu-id="317b7-122">Client User: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="317b7-123">解释</span><span class="sxs-lookup"><span data-stu-id="317b7-123">Explanation</span></span>  
 <span data-ttu-id="317b7-124">已检测到此 Windows 帐户的映射，但是被忽略，原因是为此应用程序配置的适配器不支持将密码同步到外部系统。</span><span class="sxs-lookup"><span data-stu-id="317b7-124">A mapping for this Windows account has been detected but ignored because the adapter configured for this application does not support password sync to external systems.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="317b7-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="317b7-125">User Action</span></span>  
 <span data-ttu-id="317b7-126">检查适配器配置。</span><span class="sxs-lookup"><span data-stu-id="317b7-126">Check your adapter configuration.</span></span>  
  
 <span data-ttu-id="317b7-127">有关密码同步的信息，请参阅[密码同步](../core/password-synchronization2.md)。</span><span class="sxs-lookup"><span data-stu-id="317b7-127">For information on Password Sync, see [Password Synchronization](../core/password-synchronization2.md).</span></span>