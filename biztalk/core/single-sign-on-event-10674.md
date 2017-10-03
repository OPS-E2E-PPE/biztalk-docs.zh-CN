---
title: "单一登录： 事件 10674 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad0c0d9e-1e6d-4c3e-86e0-9e336a18f3d6
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d239353276657e85c7fbdcfa634c3c1268723724
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10674"></a><span data-ttu-id="0dc3c-102">单一登录： 事件 10674</span><span class="sxs-lookup"><span data-stu-id="0dc3c-102">Single Sign-On: Event 10674</span></span>
## <a name="details"></a><span data-ttu-id="0dc3c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0dc3c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0dc3c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0dc3c-104">Product Name</span></span>|<span data-ttu-id="0dc3c-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0dc3c-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0dc3c-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0dc3c-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0dc3c-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0dc3c-107">Event ID</span></span>|<span data-ttu-id="0dc3c-108">10674</span><span class="sxs-lookup"><span data-stu-id="0dc3c-108">10674</span></span>|  
|<span data-ttu-id="0dc3c-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0dc3c-109">Event Source</span></span>|<span data-ttu-id="0dc3c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0dc3c-110">ENTSSO</span></span>|  
|<span data-ttu-id="0dc3c-111">组件</span><span class="sxs-lookup"><span data-stu-id="0dc3c-111">Component</span></span>|<span data-ttu-id="0dc3c-112">N\A</span><span class="sxs-lookup"><span data-stu-id="0dc3c-112">N\A</span></span>|  
|<span data-ttu-id="0dc3c-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0dc3c-113">Symbolic Name</span></span>|<span data-ttu-id="0dc3c-114">SSO_WARN_WINDOWS_MAPPING_CONFLICT_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="0dc3c-114">SSO_WARN_WINDOWS_MAPPING_CONFLICT_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="0dc3c-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0dc3c-115">Message Text</span></span>|<span data-ttu-id="0dc3c-116">外部密码更改将导致多个 Windows 帐户更改。%r</span><span class="sxs-lookup"><span data-stu-id="0dc3c-116">An external password change would have caused changes to more than one Windows account.%r</span></span><br /><br /> <span data-ttu-id="0dc3c-117">此操作已被阻止，因为此外部系统的适配器配置为不允许映射冲突。%r</span><span class="sxs-lookup"><span data-stu-id="0dc3c-117">This has been prevented because the adapter for this external system is configured to not allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="0dc3c-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0dc3c-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="0dc3c-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="0dc3c-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="0dc3c-120">外部帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="0dc3c-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="0dc3c-121">Windows 帐户 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="0dc3c-121">Windows Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="0dc3c-122">Windows 帐户 2: %5</span><span class="sxs-lookup"><span data-stu-id="0dc3c-122">Windows Account 2: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0dc3c-123">解释</span><span class="sxs-lookup"><span data-stu-id="0dc3c-123">Explanation</span></span>  
 <span data-ttu-id="0dc3c-124">此警告事件表示，外部密码更改将导致多个 Windows 帐户更改。</span><span class="sxs-lookup"><span data-stu-id="0dc3c-124">This Warning event indicates that an external password change would have caused changes to more than one Windows account.</span></span> <span data-ttu-id="0dc3c-125">已阻止此更改，因为适配器配置不允许进行此项更改。</span><span class="sxs-lookup"><span data-stu-id="0dc3c-125">This change was prevented because the adapter configuration would not allow it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0dc3c-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="0dc3c-126">User Action</span></span>  
 <span data-ttu-id="0dc3c-127">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0dc3c-127">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="0dc3c-128">如果预期并且允许映射冲突，请使用 SSO 管理工具来配置**允许映射冲突**密码同步适配器属性。</span><span class="sxs-lookup"><span data-stu-id="0dc3c-128">If mapping conflicts are expected and allowed, use the SSO Admin tools to configure the **Allow Mapping Conflicts** property for the Password Sync Adapter.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="0dc3c-129">详细信息</span><span class="sxs-lookup"><span data-stu-id="0dc3c-129">More info</span></span>
  
-   <span data-ttu-id="0dc3c-130">**密码同步适配器属性： 选项**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="0dc3c-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   [<span data-ttu-id="0dc3c-131">密码同步</span><span class="sxs-lookup"><span data-stu-id="0dc3c-131">Password Synchronization</span></span>](../core/password-synchronization2.md)