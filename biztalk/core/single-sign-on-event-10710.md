---
title: "单一登录： 事件 10710 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 469dc407-be7a-45a1-bcf5-2ba7060a19e2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1a3dafe3dd5b7dbdf0e5934218af6539427184f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10710"></a><span data-ttu-id="086e9-102">单一登录： 事件 10710</span><span class="sxs-lookup"><span data-stu-id="086e9-102">Single Sign-On: Event 10710</span></span>
## <a name="details"></a><span data-ttu-id="086e9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="086e9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="086e9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="086e9-104">Product Name</span></span>|<span data-ttu-id="086e9-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="086e9-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="086e9-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="086e9-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="086e9-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="086e9-107">Event ID</span></span>|<span data-ttu-id="086e9-108">10710</span><span class="sxs-lookup"><span data-stu-id="086e9-108">10710</span></span>|  
|<span data-ttu-id="086e9-109">事件源</span><span class="sxs-lookup"><span data-stu-id="086e9-109">Event Source</span></span>|<span data-ttu-id="086e9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="086e9-110">ENTSSO</span></span>|  
|<span data-ttu-id="086e9-111">组件</span><span class="sxs-lookup"><span data-stu-id="086e9-111">Component</span></span>|<span data-ttu-id="086e9-112">N\A</span><span class="sxs-lookup"><span data-stu-id="086e9-112">N\A</span></span>|  
|<span data-ttu-id="086e9-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="086e9-113">Symbolic Name</span></span>|<span data-ttu-id="086e9-114">SSO_INFO_PS_WIN_CHANGE_DAMPED</span><span class="sxs-lookup"><span data-stu-id="086e9-114">SSO_INFO_PS_WIN_CHANGE_DAMPED</span></span>|  
|<span data-ttu-id="086e9-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="086e9-115">Message Text</span></span>|<span data-ttu-id="086e9-116">Windows 密码更改被阻止（检测为复制和丢弃）。%r</span><span class="sxs-lookup"><span data-stu-id="086e9-116">A Windows password change was damped (detected as a duplicate and discarded).%r</span></span><br /><br /> <span data-ttu-id="086e9-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="086e9-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="086e9-118">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="086e9-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="086e9-119">客户端用户： %3</span><span class="sxs-lookup"><span data-stu-id="086e9-119">Client User: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="086e9-120">解释</span><span class="sxs-lookup"><span data-stu-id="086e9-120">Explanation</span></span>  
 <span data-ttu-id="086e9-121">此信息事件表明 Windows 密码更改由于被检测为重复而被丢弃。</span><span class="sxs-lookup"><span data-stu-id="086e9-121">This Information event indicates that a Windows password change was discarded because it was detected as a duplicate.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="086e9-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="086e9-122">User Action</span></span>  
  
-   <span data-ttu-id="086e9-123">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="086e9-123">No user action is necessary.</span></span>  
  
 <span data-ttu-id="086e9-124">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="086e9-124">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="086e9-125">密码同步</span><span class="sxs-lookup"><span data-stu-id="086e9-125">Password Synchronization</span></span>](../core/password-synchronization2.md)