---
title: "单一登录： 事件 10672 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2422c7d-51bc-4f12-8830-193d71d2bce9
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03eb6a72be53f928c8c173ac84556f709df0723c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10672"></a><span data-ttu-id="80b0b-102">单一登录： 事件 10672</span><span class="sxs-lookup"><span data-stu-id="80b0b-102">Single Sign-On: Event 10672</span></span>
## <a name="details"></a><span data-ttu-id="80b0b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="80b0b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="80b0b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="80b0b-104">Product Name</span></span>|<span data-ttu-id="80b0b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="80b0b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="80b0b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="80b0b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="80b0b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="80b0b-107">Event ID</span></span>|<span data-ttu-id="80b0b-108">10672</span><span class="sxs-lookup"><span data-stu-id="80b0b-108">10672</span></span>|  
|<span data-ttu-id="80b0b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="80b0b-109">Event Source</span></span>|<span data-ttu-id="80b0b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="80b0b-110">ENTSSO</span></span>|  
|<span data-ttu-id="80b0b-111">组件</span><span class="sxs-lookup"><span data-stu-id="80b0b-111">Component</span></span>|<span data-ttu-id="80b0b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="80b0b-112">N\A</span></span>|  
|<span data-ttu-id="80b0b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="80b0b-113">Symbolic Name</span></span>|<span data-ttu-id="80b0b-114">SSO_WARN_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="80b0b-114">SSO_WARN_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="80b0b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="80b0b-115">Message Text</span></span>|<span data-ttu-id="80b0b-116">一个 Windows 密码更改可能会造成对同一个外部系统上的多个帐户进行更改。%r</span><span class="sxs-lookup"><span data-stu-id="80b0b-116">A Windows password change would have caused changes to more than one account on the same external system.%r</span></span><br /><br /> <span data-ttu-id="80b0b-117">此操作已被阻止，因为此外部系统的适配器配置为不允许映射冲突。%r</span><span class="sxs-lookup"><span data-stu-id="80b0b-117">This has been prevented because the adapter for this external system is configured to not allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="80b0b-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="80b0b-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="80b0b-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="80b0b-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="80b0b-120">Windows 帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="80b0b-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="80b0b-121">外部帐户 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="80b0b-121">External Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="80b0b-122">外部帐户 2: %5</span><span class="sxs-lookup"><span data-stu-id="80b0b-122">External Account 2: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="80b0b-123">解释</span><span class="sxs-lookup"><span data-stu-id="80b0b-123">Explanation</span></span>  
 <span data-ttu-id="80b0b-124">此警告事件表示，Windows 密码更改可能会导致对同一个外部系统上的多个帐户进行更改。</span><span class="sxs-lookup"><span data-stu-id="80b0b-124">This Warning event indicates that a Windows password change would have caused changes to more than one account on the same external system.</span></span> <span data-ttu-id="80b0b-125">已阻止此更改，因为适配器配置不允许进行此项更改。</span><span class="sxs-lookup"><span data-stu-id="80b0b-125">This change was prevented because the adapter configuration would not allow it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="80b0b-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="80b0b-126">User Action</span></span>  
  
-   <span data-ttu-id="80b0b-127">使用 SSO 管理工具来配置**允许映射冲突**密码同步适配器属性。</span><span class="sxs-lookup"><span data-stu-id="80b0b-127">Use the SSO Admin tools to configure the **Allow Mapping Conflicts** property for the Password Sync Adapter.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="80b0b-128">详细信息</span><span class="sxs-lookup"><span data-stu-id="80b0b-128">More info</span></span>
  
-   <span data-ttu-id="80b0b-129">**密码同步适配器属性： 选项**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="80b0b-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   [<span data-ttu-id="80b0b-130">密码同步</span><span class="sxs-lookup"><span data-stu-id="80b0b-130">Password Synchronization</span></span>](../core/password-synchronization2.md)