---
title: 单一登录：事件 11071 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c0f61b9-cd86-482b-a8fe-0093a928c89b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43105808e83b06f780736e7168581d3854305439
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247483"
---
# <a name="single-sign-on-event-11071"></a><span data-ttu-id="44b76-102">单一登录：事件 11071</span><span class="sxs-lookup"><span data-stu-id="44b76-102">Single Sign-On: Event 11071</span></span>
## <a name="details"></a><span data-ttu-id="44b76-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="44b76-103">Details</span></span>  
  
|                 |                                                                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="44b76-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="44b76-104">Product Name</span></span>   |                                                                                   <span data-ttu-id="44b76-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="44b76-105">Enterprise Single Sign-On</span></span>                                                                                   |
| <span data-ttu-id="44b76-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="44b76-106">Product Version</span></span> |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                   |
|    <span data-ttu-id="44b76-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="44b76-107">Event ID</span></span>     |                                                                                             <span data-ttu-id="44b76-108">11071</span><span class="sxs-lookup"><span data-stu-id="44b76-108">11071</span></span>                                                                                             |
|  <span data-ttu-id="44b76-109">事件源</span><span class="sxs-lookup"><span data-stu-id="44b76-109">Event Source</span></span>   |                                                                                            <span data-ttu-id="44b76-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="44b76-110">ENTSSO</span></span>                                                                                             |
|    <span data-ttu-id="44b76-111">组件</span><span class="sxs-lookup"><span data-stu-id="44b76-111">Component</span></span>    |                                                                                              <span data-ttu-id="44b76-112">不可用</span><span class="sxs-lookup"><span data-stu-id="44b76-112">N/A</span></span>                                                                                              |
|  <span data-ttu-id="44b76-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="44b76-113">Symbolic Name</span></span>  |                                                                         <span data-ttu-id="44b76-114">SSO_WARN_PS_WIN_CHANGE_DISCARDED_ZERO_LENGTH</span><span class="sxs-lookup"><span data-stu-id="44b76-114">SSO_WARN_PS_WIN_CHANGE_DISCARDED_ZERO_LENGTH</span></span>                                                                          |
|  <span data-ttu-id="44b76-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="44b76-115">Message Text</span></span>   | <span data-ttu-id="44b76-116">已放弃 Windows 密码更改，因为 Windows 密码长度为零 characters.%r</span><span class="sxs-lookup"><span data-stu-id="44b76-116">A Windows password change was discarded because the Windows password length is zero characters.%r</span></span><br /><br /> <span data-ttu-id="44b76-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="44b76-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="44b76-118">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="44b76-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="44b76-119">客户端用户： %3</span><span class="sxs-lookup"><span data-stu-id="44b76-119">Client User: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="44b76-120">解释</span><span class="sxs-lookup"><span data-stu-id="44b76-120">Explanation</span></span>  
 <span data-ttu-id="44b76-121">Windows 密码更改已被丢弃，因为 Windows 密码长度为零个字符。</span><span class="sxs-lookup"><span data-stu-id="44b76-121">A Windows password change was discarded because the Windows password length is zero characters.</span></span> <span data-ttu-id="44b76-122">提供 Windows 帐户和客户端用户名。</span><span class="sxs-lookup"><span data-stu-id="44b76-122">The Windows account and client user name are provided.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="44b76-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="44b76-123">User Action</span></span>  
 <span data-ttu-id="44b76-124">同样，使用的数量和类型的字符所需的 SSO 系统更改的密码。</span><span class="sxs-lookup"><span data-stu-id="44b76-124">Change the password again, using the number and type of characters required by your SSO system.</span></span>