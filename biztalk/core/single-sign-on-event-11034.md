---
title: 单一登录： 事件 11034 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 828bc5fb-12ab-4eea-94f2-2434ad0ee033
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c66245fe478dddeb539344503d8658719a604ed5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278213"
---
# <a name="single-sign-on-event-11034"></a><span data-ttu-id="a0266-102">单一登录： 事件 11034</span><span class="sxs-lookup"><span data-stu-id="a0266-102">Single Sign-On: Event 11034</span></span>
## <a name="details"></a><span data-ttu-id="a0266-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a0266-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a0266-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a0266-104">Product Name</span></span>|<span data-ttu-id="a0266-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="a0266-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="a0266-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="a0266-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="a0266-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a0266-107">Event ID</span></span>|<span data-ttu-id="a0266-108">11034</span><span class="sxs-lookup"><span data-stu-id="a0266-108">11034</span></span>|  
|<span data-ttu-id="a0266-109">事件源</span><span class="sxs-lookup"><span data-stu-id="a0266-109">Event Source</span></span>|<span data-ttu-id="a0266-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a0266-110">ENTSSO</span></span>|  
|<span data-ttu-id="a0266-111">组件</span><span class="sxs-lookup"><span data-stu-id="a0266-111">Component</span></span>|<span data-ttu-id="a0266-112">N/A</span><span class="sxs-lookup"><span data-stu-id="a0266-112">N/A</span></span>|  
|<span data-ttu-id="a0266-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="a0266-113">Symbolic Name</span></span>|<span data-ttu-id="a0266-114">SSO_INFO_PS_WIN_CHANGE_APP_INCORRECT_TYPE</span><span class="sxs-lookup"><span data-stu-id="a0266-114">SSO_INFO_PS_WIN_CHANGE_APP_INCORRECT_TYPE</span></span>|  
|<span data-ttu-id="a0266-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="a0266-115">Message Text</span></span>|<span data-ttu-id="a0266-116">Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="a0266-116">Windows password change.</span></span> <span data-ttu-id="a0266-117">检测到此 Windows 帐户的一个映射，但由于应用程序的类型不正确，此映射被忽略。</span><span class="sxs-lookup"><span data-stu-id="a0266-117">A mapping for this Windows account has been detected but ignored because the application is not the correct type.</span></span> <span data-ttu-id="a0266-118">只有“个人”或“组”类型的应用程序才支持 Windows 密码同步。%r</span><span class="sxs-lookup"><span data-stu-id="a0266-118">Only ‘Individual’ or ‘Group’ type applications support Windows password sync.%r</span></span><br /><br /> <span data-ttu-id="a0266-119">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a0266-119">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="a0266-120">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="a0266-120">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="a0266-121">应用程序: %3 %r</span><span class="sxs-lookup"><span data-stu-id="a0266-121">Application: %3%r</span></span><br /><br /> <span data-ttu-id="a0266-122">外部帐户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="a0266-122">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="a0266-123">客户端用户： %5</span><span class="sxs-lookup"><span data-stu-id="a0266-123">Client User: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a0266-124">解释</span><span class="sxs-lookup"><span data-stu-id="a0266-124">Explanation</span></span>  
 <span data-ttu-id="a0266-125">只有“个人”或“组”类型的应用程序才支持 Windows 密码同步。</span><span class="sxs-lookup"><span data-stu-id="a0266-125">Only ‘Individual’ or ‘Group’ type applications support Windows password sync.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a0266-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="a0266-126">User Action</span></span>  
 <span data-ttu-id="a0266-127">有关详细信息，请参阅[密码同步](../core/password-synchronization2.md)。</span><span class="sxs-lookup"><span data-stu-id="a0266-127">For more information, see [Password Synchronization](../core/password-synchronization2.md).</span></span>