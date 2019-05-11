---
title: 单一登录：Event 10599 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd671aa5-b243-4081-9a4e-87103be9a1d7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 263d2b0b50e43b485e60a56ebd74e0164dab8b0f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397812"
---
# <a name="single-sign-on-event-10599"></a><span data-ttu-id="e61c3-102">单一登录：事件 10599</span><span class="sxs-lookup"><span data-stu-id="e61c3-102">Single Sign-On: Event 10599</span></span>
## <a name="details"></a><span data-ttu-id="e61c3-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e61c3-103">Details</span></span>  
  
|                 |                                                                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e61c3-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e61c3-104">Product Name</span></span>   |                                                                             <span data-ttu-id="e61c3-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e61c3-105">Enterprise Single Sign-On</span></span>                                                                              |
| <span data-ttu-id="e61c3-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e61c3-106">Product Version</span></span> |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    <span data-ttu-id="e61c3-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e61c3-107">Event ID</span></span>     |                                                                                       <span data-ttu-id="e61c3-108">10599</span><span class="sxs-lookup"><span data-stu-id="e61c3-108">10599</span></span>                                                                                        |
|  <span data-ttu-id="e61c3-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e61c3-109">Event Source</span></span>   |                                                                                       <span data-ttu-id="e61c3-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e61c3-110">ENTSSO</span></span>                                                                                       |
|    <span data-ttu-id="e61c3-111">组件</span><span class="sxs-lookup"><span data-stu-id="e61c3-111">Component</span></span>    |                                                                                        <span data-ttu-id="e61c3-112">不可用</span><span class="sxs-lookup"><span data-stu-id="e61c3-112">N/A</span></span>                                                                                         |
|  <span data-ttu-id="e61c3-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e61c3-113">Symbolic Name</span></span>  |                                                                              <span data-ttu-id="e61c3-114">SSO_WARN_ENTSSO_IS_ADMIN</span><span class="sxs-lookup"><span data-stu-id="e61c3-114">SSO_WARN_ENTSSO_IS_ADMIN</span></span>                                                                              |
|  <span data-ttu-id="e61c3-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e61c3-115">Message Text</span></span>   | <span data-ttu-id="e61c3-116">SSO 服务正在本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="e61c3-116">The SSO service is running under a local administrator account.</span></span> <span data-ttu-id="e61c3-117">出于安全原因，这不被建议。</span><span class="sxs-lookup"><span data-stu-id="e61c3-117">This is not recommended for security reasons.</span></span> <span data-ttu-id="e61c3-118">请参阅 details.%r 文档</span><span class="sxs-lookup"><span data-stu-id="e61c3-118">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="e61c3-119">SSO 服务帐户： %1</span><span class="sxs-lookup"><span data-stu-id="e61c3-119">SSO Service Account: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e61c3-120">解释</span><span class="sxs-lookup"><span data-stu-id="e61c3-120">Explanation</span></span>  
 <span data-ttu-id="e61c3-121">指定的 SSO 服务正在本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="e61c3-121">The SSO service specified is running under a local administrator account.</span></span> <span data-ttu-id="e61c3-122">出于安全原因，这不被建议。</span><span class="sxs-lookup"><span data-stu-id="e61c3-122">This is not recommended for security reasons.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e61c3-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="e61c3-123">User Action</span></span>  
 <span data-ttu-id="e61c3-124">有关详细信息，请参阅[SSO 安全建议](../core/sso-security-recommendations.md)。</span><span class="sxs-lookup"><span data-stu-id="e61c3-124">For more information, see [SSO Security Recommendations](../core/sso-security-recommendations.md).</span></span>