---
title: 单一登录： 事件 11057 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e165e24-fe43-4899-ab6e-1437f639f534
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca69661d1421433c44472e0572c5d4d4bf76a13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278085"
---
# <a name="single-sign-on-event-11057"></a><span data-ttu-id="6542b-102">单一登录： 事件 11057</span><span class="sxs-lookup"><span data-stu-id="6542b-102">Single Sign-On: Event 11057</span></span>
## <a name="details"></a><span data-ttu-id="6542b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="6542b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6542b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="6542b-104">Product Name</span></span>|<span data-ttu-id="6542b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="6542b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="6542b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="6542b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="6542b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6542b-107">Event ID</span></span>|<span data-ttu-id="6542b-108">11057</span><span class="sxs-lookup"><span data-stu-id="6542b-108">11057</span></span>|  
|<span data-ttu-id="6542b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="6542b-109">Event Source</span></span>|<span data-ttu-id="6542b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6542b-110">ENTSSO</span></span>|  
|<span data-ttu-id="6542b-111">组件</span><span class="sxs-lookup"><span data-stu-id="6542b-111">Component</span></span>|<span data-ttu-id="6542b-112">N/A</span><span class="sxs-lookup"><span data-stu-id="6542b-112">N/A</span></span>|  
|<span data-ttu-id="6542b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="6542b-113">Symbolic Name</span></span>|<span data-ttu-id="6542b-114">SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="6542b-114">SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS</span></span>|  
|<span data-ttu-id="6542b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="6542b-115">Message Text</span></span>|<span data-ttu-id="6542b-116">直接密码更改。</span><span class="sxs-lookup"><span data-stu-id="6542b-116">Direct password change.</span></span> <span data-ttu-id="6542b-117">已将此映射的某些缺少的外部凭据字段设置为默认值。%r</span><span class="sxs-lookup"><span data-stu-id="6542b-117">Some missing external credential fields for this mapping have been set to default values.%r</span></span><br /><br /> <span data-ttu-id="6542b-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="6542b-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="6542b-119">应用程序名称: %2 %r</span><span class="sxs-lookup"><span data-stu-id="6542b-119">Application Name: %2%r</span></span><br /><br /> <span data-ttu-id="6542b-120">Windows 帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="6542b-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="6542b-121">外部帐户： %4</span><span class="sxs-lookup"><span data-stu-id="6542b-121">External Account: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6542b-122">解释</span><span class="sxs-lookup"><span data-stu-id="6542b-122">Explanation</span></span>  
 <span data-ttu-id="6542b-123">尽管可以使用直接密码同步来更改密码，但此功能只支持一个外部凭据字段。</span><span class="sxs-lookup"><span data-stu-id="6542b-123">While it is possible to change passwords using Direct Password Sync, this feature only supports one external credential field.</span></span> <span data-ttu-id="6542b-124">在这种情况下 ENTSSO 系统遇到多个外部凭据字段，并已将这些字段设置为默认 （空白） 值。</span><span class="sxs-lookup"><span data-stu-id="6542b-124">In this case the ENTSSO System has encountered more than one external credential field, and has set those fields to default (blank) values.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6542b-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="6542b-125">User Action</span></span>  
 <span data-ttu-id="6542b-126">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="6542b-126">No user action is necessary.</span></span>