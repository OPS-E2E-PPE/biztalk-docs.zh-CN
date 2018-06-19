---
title: 单一登录： 事件 10679 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 645f2b74-2cbe-4c6a-b0f5-7e31f93f88c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f612f3cf6540340124a3f11ed99fe736df65296b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271741"
---
# <a name="single-sign-on-event-10679"></a><span data-ttu-id="e564b-102">单一登录： 事件 10679</span><span class="sxs-lookup"><span data-stu-id="e564b-102">Single Sign-On: Event 10679</span></span>
## <a name="details"></a><span data-ttu-id="e564b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e564b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e564b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e564b-104">Product Name</span></span>|<span data-ttu-id="e564b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e564b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="e564b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e564b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="e564b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e564b-107">Event ID</span></span>|<span data-ttu-id="e564b-108">10679</span><span class="sxs-lookup"><span data-stu-id="e564b-108">10679</span></span>|  
|<span data-ttu-id="e564b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e564b-109">Event Source</span></span>|<span data-ttu-id="e564b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e564b-110">ENTSSO</span></span>|  
|<span data-ttu-id="e564b-111">组件</span><span class="sxs-lookup"><span data-stu-id="e564b-111">Component</span></span>|<span data-ttu-id="e564b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="e564b-112">N\A</span></span>|  
|<span data-ttu-id="e564b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e564b-113">Symbolic Name</span></span>|<span data-ttu-id="e564b-114">SSO_WARN_PS_MAPPING_DISABLED</span><span class="sxs-lookup"><span data-stu-id="e564b-114">SSO_WARN_PS_MAPPING_DISABLED</span></span>|  
|<span data-ttu-id="e564b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e564b-115">Message Text</span></span>|<span data-ttu-id="e564b-116">外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="e564b-116">External password change.</span></span> <span data-ttu-id="e564b-117">由于已禁用映射，因此未更改外部帐户的密码。%r</span><span class="sxs-lookup"><span data-stu-id="e564b-117">The password was not changed for the external account because the mapping is disabled.%r</span></span><br /><br /> <span data-ttu-id="e564b-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e564b-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="e564b-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="e564b-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="e564b-120">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="e564b-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="e564b-121">外部帐户： %4</span><span class="sxs-lookup"><span data-stu-id="e564b-121">External Account: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e564b-122">解释</span><span class="sxs-lookup"><span data-stu-id="e564b-122">Explanation</span></span>  
 <span data-ttu-id="e564b-123">此警告事件表明由于已禁用映射而未更改外部帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="e564b-123">This Warning event indicates that the password was not changed for the external account because the mapping is disabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e564b-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="e564b-124">User Action</span></span>  
 <span data-ttu-id="e564b-125">要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e564b-125">To resolve this warning do the following:</span></span>  
  
-   <span data-ttu-id="e564b-126">使用 SSO 管理工具启用此适配器的映射。</span><span class="sxs-lookup"><span data-stu-id="e564b-126">Use the SSO administration tools to enable mapping for this adapter.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="e564b-127">详细信息</span><span class="sxs-lookup"><span data-stu-id="e564b-127">More info</span></span>
  
-   [<span data-ttu-id="e564b-128">密码同步</span><span class="sxs-lookup"><span data-stu-id="e564b-128">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   <span data-ttu-id="e564b-129">**密码同步适配器属性： 选项**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="e564b-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>