---
title: 单一登录：Event 11023 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feeb4ede-6045-46bf-9f2b-65062c583faa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 525c2bd0759aa24c191991e075276bd75233d6d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266537"
---
# <a name="single-sign-on-event-11023"></a><span data-ttu-id="95423-102">单一登录：事件 11023</span><span class="sxs-lookup"><span data-stu-id="95423-102">Single Sign-On: Event 11023</span></span>
## <a name="details"></a><span data-ttu-id="95423-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="95423-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="95423-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="95423-104">Product Name</span></span>   |                                                                                                                                 <span data-ttu-id="95423-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="95423-105">Enterprise Single Sign-On</span></span>                                                                                                                                  |
| <span data-ttu-id="95423-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="95423-106">Product Version</span></span> |                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                 |
|    <span data-ttu-id="95423-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="95423-107">Event ID</span></span>     |                                                                                                                                           <span data-ttu-id="95423-108">11023</span><span class="sxs-lookup"><span data-stu-id="95423-108">11023</span></span>                                                                                                                                            |
|  <span data-ttu-id="95423-109">事件源</span><span class="sxs-lookup"><span data-stu-id="95423-109">Event Source</span></span>   |                                                                                                                                           <span data-ttu-id="95423-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="95423-110">ENTSSO</span></span>                                                                                                                                           |
|    <span data-ttu-id="95423-111">组件</span><span class="sxs-lookup"><span data-stu-id="95423-111">Component</span></span>    |                                                                                                                                            <span data-ttu-id="95423-112">不可用</span><span class="sxs-lookup"><span data-stu-id="95423-112">N/A</span></span>                                                                                                                                             |
|  <span data-ttu-id="95423-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="95423-113">Symbolic Name</span></span>  |                                                                                                                             <span data-ttu-id="95423-114">SSO_WARN_WINDOWS_PASSWORD_DELETED</span><span class="sxs-lookup"><span data-stu-id="95423-114">SSO_WARN_WINDOWS_PASSWORD_DELETED</span></span>                                                                                                                              |
|  <span data-ttu-id="95423-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="95423-115">Message Text</span></span>   | <span data-ttu-id="95423-116">已删除 SSO 数据库中无效的 Windows 密码以阻止帐户 lockout.%r</span><span class="sxs-lookup"><span data-stu-id="95423-116">An invalid Windows password in the SSO database was deleted to prevent account lockout.%r</span></span><br /><br /> <span data-ttu-id="95423-117">使用 SSO 管理工具设置为此 Windows account.%r 的外部凭据</span><span class="sxs-lookup"><span data-stu-id="95423-117">Use the SSO administration tools to set the external credentials for this Windows account.%r</span></span><br /><br /> <span data-ttu-id="95423-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="95423-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="95423-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="95423-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="95423-120">Windows 帐户： %3</span><span class="sxs-lookup"><span data-stu-id="95423-120">Windows Account: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="95423-121">解释</span><span class="sxs-lookup"><span data-stu-id="95423-121">Explanation</span></span>  
 <span data-ttu-id="95423-122">无效的 Windows 密码已被删除。</span><span class="sxs-lookup"><span data-stu-id="95423-122">An invalid Windows password has been deleted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="95423-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="95423-123">User Action</span></span>  
 <span data-ttu-id="95423-124">使用 SSO 管理工具来设置此 Windows 帐户的外部凭据。</span><span class="sxs-lookup"><span data-stu-id="95423-124">Use the SSO administration tools to set the external credentials for this Windows account.</span></span> <span data-ttu-id="95423-125">有关详细信息，请参阅[使用 SSO](../core/using-sso.md)。</span><span class="sxs-lookup"><span data-stu-id="95423-125">For more information, see [Using SSO](../core/using-sso.md).</span></span>