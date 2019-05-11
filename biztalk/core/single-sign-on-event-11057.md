---
title: 单一登录：Event 11057 | Microsoft Docs
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
ms.openlocfilehash: ff6e7a5c811c983ebe9f48fc6cdd85ed79f3ee16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400868"
---
# <a name="single-sign-on-event-11057"></a><span data-ttu-id="7a113-102">单一登录：事件 11057</span><span class="sxs-lookup"><span data-stu-id="7a113-102">Single Sign-On: Event 11057</span></span>
## <a name="details"></a><span data-ttu-id="7a113-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7a113-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7a113-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7a113-104">Product Name</span></span>   |                                                                                                                <span data-ttu-id="7a113-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="7a113-105">Enterprise Single Sign-On</span></span>                                                                                                                |
| <span data-ttu-id="7a113-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="7a113-106">Product Version</span></span> |                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                |
|    <span data-ttu-id="7a113-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7a113-107">Event ID</span></span>     |                                                                                                                          <span data-ttu-id="7a113-108">11057</span><span class="sxs-lookup"><span data-stu-id="7a113-108">11057</span></span>                                                                                                                          |
|  <span data-ttu-id="7a113-109">事件源</span><span class="sxs-lookup"><span data-stu-id="7a113-109">Event Source</span></span>   |                                                                                                                         <span data-ttu-id="7a113-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7a113-110">ENTSSO</span></span>                                                                                                                          |
|    <span data-ttu-id="7a113-111">组件</span><span class="sxs-lookup"><span data-stu-id="7a113-111">Component</span></span>    |                                                                                                                           <span data-ttu-id="7a113-112">不可用</span><span class="sxs-lookup"><span data-stu-id="7a113-112">N/A</span></span>                                                                                                                           |
|  <span data-ttu-id="7a113-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="7a113-113">Symbolic Name</span></span>  |                                                                                                        <span data-ttu-id="7a113-114">SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="7a113-114">SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS</span></span>                                                                                                         |
|  <span data-ttu-id="7a113-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="7a113-115">Message Text</span></span>   | <span data-ttu-id="7a113-116">直接密码更改。</span><span class="sxs-lookup"><span data-stu-id="7a113-116">Direct password change.</span></span> <span data-ttu-id="7a113-117">此映射某些缺少的外部凭据字段已设置为默认 values.%r</span><span class="sxs-lookup"><span data-stu-id="7a113-117">Some missing external credential fields for this mapping have been set to default values.%r</span></span><br /><br /> <span data-ttu-id="7a113-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7a113-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="7a113-119">应用程序名称: %2 %r</span><span class="sxs-lookup"><span data-stu-id="7a113-119">Application Name: %2%r</span></span><br /><br /> <span data-ttu-id="7a113-120">Windows 帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="7a113-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="7a113-121">外部帐户： %4</span><span class="sxs-lookup"><span data-stu-id="7a113-121">External Account: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7a113-122">解释</span><span class="sxs-lookup"><span data-stu-id="7a113-122">Explanation</span></span>  
 <span data-ttu-id="7a113-123">无法更改使用直接密码同步的密码时，此功能仅支持一个外部凭据字段。</span><span class="sxs-lookup"><span data-stu-id="7a113-123">While it is possible to change passwords using Direct Password Sync, this feature only supports one external credential field.</span></span> <span data-ttu-id="7a113-124">在这种情况下 ENTSSO 系统遇到了多个外部凭据字段中，并且已将这些字段设置为默认 （空） 值。</span><span class="sxs-lookup"><span data-stu-id="7a113-124">In this case the ENTSSO System has encountered more than one external credential field, and has set those fields to default (blank) values.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7a113-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="7a113-125">User Action</span></span>  
 <span data-ttu-id="7a113-126">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="7a113-126">No user action is necessary.</span></span>