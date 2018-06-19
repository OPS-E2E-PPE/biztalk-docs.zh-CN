---
title: 单一登录： 事件 11071 |Microsoft 文档
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
ms.openlocfilehash: e744e4f477ee45e6f634e8e4b2ca976754cbecf1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276293"
---
# <a name="single-sign-on-event-11071"></a><span data-ttu-id="901df-102">单一登录： 事件 11071</span><span class="sxs-lookup"><span data-stu-id="901df-102">Single Sign-On: Event 11071</span></span>
## <a name="details"></a><span data-ttu-id="901df-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="901df-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="901df-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="901df-104">Product Name</span></span>|<span data-ttu-id="901df-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="901df-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="901df-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="901df-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="901df-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="901df-107">Event ID</span></span>|<span data-ttu-id="901df-108">11071</span><span class="sxs-lookup"><span data-stu-id="901df-108">11071</span></span>|  
|<span data-ttu-id="901df-109">事件源</span><span class="sxs-lookup"><span data-stu-id="901df-109">Event Source</span></span>|<span data-ttu-id="901df-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="901df-110">ENTSSO</span></span>|  
|<span data-ttu-id="901df-111">组件</span><span class="sxs-lookup"><span data-stu-id="901df-111">Component</span></span>|<span data-ttu-id="901df-112">N/A</span><span class="sxs-lookup"><span data-stu-id="901df-112">N/A</span></span>|  
|<span data-ttu-id="901df-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="901df-113">Symbolic Name</span></span>|<span data-ttu-id="901df-114">SSO_WARN_PS_WIN_CHANGE_DISCARDED_ZERO_LENGTH</span><span class="sxs-lookup"><span data-stu-id="901df-114">SSO_WARN_PS_WIN_CHANGE_DISCARDED_ZERO_LENGTH</span></span>|  
|<span data-ttu-id="901df-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="901df-115">Message Text</span></span>|<span data-ttu-id="901df-116">已放弃 Windows 密码更改，因为 Windows 密码长度为零个字符。%r</span><span class="sxs-lookup"><span data-stu-id="901df-116">A Windows password change was discarded because the Windows password length is zero characters.%r</span></span><br /><br /> <span data-ttu-id="901df-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="901df-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="901df-118">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="901df-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="901df-119">客户端用户： %3</span><span class="sxs-lookup"><span data-stu-id="901df-119">Client User: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="901df-120">解释</span><span class="sxs-lookup"><span data-stu-id="901df-120">Explanation</span></span>  
 <span data-ttu-id="901df-121">已放弃 Windows 密码更改，因为 Windows 密码长度为零个字符。</span><span class="sxs-lookup"><span data-stu-id="901df-121">A Windows password change was discarded because the Windows password length is zero characters.</span></span> <span data-ttu-id="901df-122">已提供 Windows 帐户和客户端用户名。</span><span class="sxs-lookup"><span data-stu-id="901df-122">The Windows account and client user name are provided.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="901df-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="901df-123">User Action</span></span>  
 <span data-ttu-id="901df-124">使用 SSO 系统要求的字符的个数和类型重新更改密码。</span><span class="sxs-lookup"><span data-stu-id="901df-124">Change the password again, using the number and type of characters required by your SSO system.</span></span>