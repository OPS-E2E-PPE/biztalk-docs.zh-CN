---
title: "单一登录： 事件 10665 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d0de9d0-9b46-4f3a-b796-1ce3de01cf4c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a7d4d5c4140448914ff77b09a692cc3a2136dfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10665"></a><span data-ttu-id="9cb5b-102">单一登录： 事件 10665</span><span class="sxs-lookup"><span data-stu-id="9cb5b-102">Single Sign-On: Event 10665</span></span>
## <a name="details"></a><span data-ttu-id="9cb5b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9cb5b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9cb5b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9cb5b-104">Product Name</span></span>|<span data-ttu-id="9cb5b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="9cb5b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="9cb5b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="9cb5b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="9cb5b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9cb5b-107">Event ID</span></span>|<span data-ttu-id="9cb5b-108">10665</span><span class="sxs-lookup"><span data-stu-id="9cb5b-108">10665</span></span>|  
|<span data-ttu-id="9cb5b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="9cb5b-109">Event Source</span></span>|<span data-ttu-id="9cb5b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9cb5b-110">ENTSSO</span></span>|  
|<span data-ttu-id="9cb5b-111">组件</span><span class="sxs-lookup"><span data-stu-id="9cb5b-111">Component</span></span>|<span data-ttu-id="9cb5b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="9cb5b-112">N\A</span></span>|  
|<span data-ttu-id="9cb5b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="9cb5b-113">Symbolic Name</span></span>|<span data-ttu-id="9cb5b-114">SSO_WARN_NO_PROPERTIES</span><span class="sxs-lookup"><span data-stu-id="9cb5b-114">SSO_WARN_NO_PROPERTIES</span></span>|  
|<span data-ttu-id="9cb5b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="9cb5b-115">Message Text</span></span>|<span data-ttu-id="9cb5b-116">读取密码同步适配器属性时出错。</span><span class="sxs-lookup"><span data-stu-id="9cb5b-116">Error reading password sync adapter properties.</span></span> <span data-ttu-id="9cb5b-117">将使用默认值。%r</span><span class="sxs-lookup"><span data-stu-id="9cb5b-117">Using defaults.%r</span></span><br /><br /> <span data-ttu-id="9cb5b-118">适配器: %1 %r</span><span class="sxs-lookup"><span data-stu-id="9cb5b-118">Adapter: %1%r</span></span><br /><br /> <span data-ttu-id="9cb5b-119">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="9cb5b-119">Error Code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9cb5b-120">解释</span><span class="sxs-lookup"><span data-stu-id="9cb5b-120">Explanation</span></span>  
 <span data-ttu-id="9cb5b-121">此警告事件表明，读取默认密码同步适配器属性时出错。</span><span class="sxs-lookup"><span data-stu-id="9cb5b-121">This Warning event indicates that there was an error reading the default password sync adapter properties.</span></span> <span data-ttu-id="9cb5b-122">每个密码同步适配器都具有与其关联的配置属性。</span><span class="sxs-lookup"><span data-stu-id="9cb5b-122">Each password sync adapter has configuration properties associated with it.</span></span> <span data-ttu-id="9cb5b-123">这些属性存储在 SSO 配置存储中，是在创建密码同步适配器时由 SSO 命令行工具或 SSO 管理 MMC 创建的。</span><span class="sxs-lookup"><span data-stu-id="9cb5b-123">These properties are stored in the SSO config store and are created by the SSO command line tools or the SSO Admin MMC when the password sync adapter is created.</span></span>  <span data-ttu-id="9cb5b-124">如果密码同步适配器是通过任何其他方法创建的，则可能会缺少某些属性，从而导致出现此错误。</span><span class="sxs-lookup"><span data-stu-id="9cb5b-124">There can be missing properties if the password sync adapter was created by any other means, then this error can be issued.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9cb5b-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="9cb5b-125">User Action</span></span>  
 <span data-ttu-id="9cb5b-126">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="9cb5b-126">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="9cb5b-127">验证密码同步适配器属性是否正确无误。</span><span class="sxs-lookup"><span data-stu-id="9cb5b-127">Verify password sync adapter properties.</span></span>  
  
-   <span data-ttu-id="9cb5b-128">重新创建密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="9cb5b-128">Recreate the password sync adapter</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="9cb5b-129">详细信息</span><span class="sxs-lookup"><span data-stu-id="9cb5b-129">More info</span></span>
  
-   <span data-ttu-id="9cb5b-130">**密码同步适配器属性： 选项**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="9cb5b-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   [<span data-ttu-id="9cb5b-131">密码同步</span><span class="sxs-lookup"><span data-stu-id="9cb5b-131">Password Synchronization</span></span>](../core/password-synchronization2.md)