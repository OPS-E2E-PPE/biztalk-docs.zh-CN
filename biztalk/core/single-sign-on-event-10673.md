---
title: 单一登录： 事件 10673 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa1d572a-1e9f-496e-a219-852e7d9228d5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8068d7ec43cc07dfd76b21dc749ca062226e49f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271389"
---
# <a name="single-sign-on-event-10673"></a><span data-ttu-id="bd6cd-102">单一登录： 事件 10673</span><span class="sxs-lookup"><span data-stu-id="bd6cd-102">Single Sign-On: Event 10673</span></span>
## <a name="details"></a><span data-ttu-id="bd6cd-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="bd6cd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd6cd-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="bd6cd-104">Product Name</span></span>|<span data-ttu-id="bd6cd-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="bd6cd-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="bd6cd-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="bd6cd-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="bd6cd-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="bd6cd-107">Event ID</span></span>|<span data-ttu-id="bd6cd-108">10673</span><span class="sxs-lookup"><span data-stu-id="bd6cd-108">10673</span></span>|  
|<span data-ttu-id="bd6cd-109">事件源</span><span class="sxs-lookup"><span data-stu-id="bd6cd-109">Event Source</span></span>|<span data-ttu-id="bd6cd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bd6cd-110">ENTSSO</span></span>|  
|<span data-ttu-id="bd6cd-111">组件</span><span class="sxs-lookup"><span data-stu-id="bd6cd-111">Component</span></span>|<span data-ttu-id="bd6cd-112">N\A</span><span class="sxs-lookup"><span data-stu-id="bd6cd-112">N\A</span></span>|  
|<span data-ttu-id="bd6cd-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="bd6cd-113">Symbolic Name</span></span>|<span data-ttu-id="bd6cd-114">SSO_INFO_WINDOWS_MAPPING_CONFLICT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="bd6cd-114">SSO_INFO_WINDOWS_MAPPING_CONFLICT_ALLOWED</span></span>|  
|<span data-ttu-id="bd6cd-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="bd6cd-115">Message Text</span></span>|<span data-ttu-id="bd6cd-116">外部密码更改将造成对多个 Windows 帐户的更改。%r</span><span class="sxs-lookup"><span data-stu-id="bd6cd-116">An external password change will cause changes to more than one Windows account.%r</span></span><br /><br /> <span data-ttu-id="bd6cd-117">这是允许的，因为此外部系统的适配器配置为允许映射冲突。%r</span><span class="sxs-lookup"><span data-stu-id="bd6cd-117">This is allowed because the adapter for this external system is configured to allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="bd6cd-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="bd6cd-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="bd6cd-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="bd6cd-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="bd6cd-120">外部帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="bd6cd-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="bd6cd-121">Windows 帐户 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="bd6cd-121">Windows Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="bd6cd-122">Windows 帐户 2: %5</span><span class="sxs-lookup"><span data-stu-id="bd6cd-122">Windows Account 2: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bd6cd-123">解释</span><span class="sxs-lookup"><span data-stu-id="bd6cd-123">Explanation</span></span>  
 <span data-ttu-id="bd6cd-124">此信息事件表示，外部密码更改将导致多个 Windows 帐户更改。</span><span class="sxs-lookup"><span data-stu-id="bd6cd-124">This Information event indicates that an external password change will cause changes to more than one Windows account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bd6cd-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="bd6cd-125">User Action</span></span>  
  
-   <span data-ttu-id="bd6cd-126">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="bd6cd-126">No user action is necessary.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="bd6cd-127">详细信息</span><span class="sxs-lookup"><span data-stu-id="bd6cd-127">More info</span></span>
  
-   [<span data-ttu-id="bd6cd-128">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="bd6cd-128">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  
  
-   <span data-ttu-id="bd6cd-129">**密码同步适配器属性： 选项**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="bd6cd-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   [<span data-ttu-id="bd6cd-130">密码同步</span><span class="sxs-lookup"><span data-stu-id="bd6cd-130">Password Synchronization</span></span>](../core/password-synchronization2.md)