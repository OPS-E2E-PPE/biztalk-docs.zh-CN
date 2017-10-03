---
title: "单一登录： 事件 10677 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2894792b-e1c9-4c24-875d-9193cbb5cd35
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 876048e9c86cf908be9eda121340ec60354803c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10677"></a><span data-ttu-id="258f0-102">单一登录： 事件 10677</span><span class="sxs-lookup"><span data-stu-id="258f0-102">Single Sign-On: Event 10677</span></span>
## <a name="details"></a><span data-ttu-id="258f0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="258f0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="258f0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="258f0-104">Product Name</span></span>|<span data-ttu-id="258f0-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="258f0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="258f0-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="258f0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="258f0-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="258f0-107">Event ID</span></span>|<span data-ttu-id="258f0-108">10677</span><span class="sxs-lookup"><span data-stu-id="258f0-108">10677</span></span>|  
|<span data-ttu-id="258f0-109">事件源</span><span class="sxs-lookup"><span data-stu-id="258f0-109">Event Source</span></span>|<span data-ttu-id="258f0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="258f0-110">ENTSSO</span></span>|  
|<span data-ttu-id="258f0-111">组件</span><span class="sxs-lookup"><span data-stu-id="258f0-111">Component</span></span>|<span data-ttu-id="258f0-112">N\A</span><span class="sxs-lookup"><span data-stu-id="258f0-112">N\A</span></span>|  
|<span data-ttu-id="258f0-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="258f0-113">Symbolic Name</span></span>|<span data-ttu-id="258f0-114">SSO_WARN_NO_EXISTING_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="258f0-114">SSO_WARN_NO_EXISTING_PASSWORD</span></span>|  
|<span data-ttu-id="258f0-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="258f0-115">Message Text</span></span>|<span data-ttu-id="258f0-116">外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="258f0-116">External password change.</span></span> <span data-ttu-id="258f0-117">无法验证旧密码，因为没有可用于此外部帐户的现有凭据。%r</span><span class="sxs-lookup"><span data-stu-id="258f0-117">The old password cannot be verified because there are no existing credentials for this external account.%r</span></span><br /><br /> <span data-ttu-id="258f0-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="258f0-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="258f0-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="258f0-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="258f0-120">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="258f0-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="258f0-121">外部帐户： %4</span><span class="sxs-lookup"><span data-stu-id="258f0-121">External Account: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="258f0-122">解释</span><span class="sxs-lookup"><span data-stu-id="258f0-122">Explanation</span></span>  
 <span data-ttu-id="258f0-123">此警告事件表示由于旧密码没有现有凭据，因此外部密码更改无法完成。</span><span class="sxs-lookup"><span data-stu-id="258f0-123">This Warning event indicates that an external password change cannot occur because the old password does not have existing credentials.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="258f0-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="258f0-124">User Action</span></span>  
 <span data-ttu-id="258f0-125">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="258f0-125">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="258f0-126">确定分配到此适配器（事件日志消息中的名称）的应用程序，然后使用 SSO 管理工具设置此外部帐户的外部凭据。</span><span class="sxs-lookup"><span data-stu-id="258f0-126">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="258f0-127">必须在所有这些应用程序中设置外部密码（对于给定帐户）。</span><span class="sxs-lookup"><span data-stu-id="258f0-127">You must set the external password (for the given account) in all of those Applications.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="258f0-128">详细信息</span><span class="sxs-lookup"><span data-stu-id="258f0-128">More info</span></span>
  
-   [<span data-ttu-id="258f0-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="258f0-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   <span data-ttu-id="258f0-130">**密码同步适配器属性： 选项**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="258f0-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>