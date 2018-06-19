---
title: 单一登录： 事件 10666 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 103947bb-e843-4427-a28a-1cceec90e2ae
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46636aaab5d59e8809966ddfa8d9768eb4f7ec60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270581"
---
# <a name="single-sign-on-event-10666"></a><span data-ttu-id="e8a00-102">单一登录： 事件 10666</span><span class="sxs-lookup"><span data-stu-id="e8a00-102">Single Sign-On: Event 10666</span></span>
## <a name="details"></a><span data-ttu-id="e8a00-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e8a00-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e8a00-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e8a00-104">Product Name</span></span>|<span data-ttu-id="e8a00-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e8a00-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="e8a00-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e8a00-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="e8a00-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e8a00-107">Event ID</span></span>|<span data-ttu-id="e8a00-108">10666</span><span class="sxs-lookup"><span data-stu-id="e8a00-108">10666</span></span>|  
|<span data-ttu-id="e8a00-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e8a00-109">Event Source</span></span>|<span data-ttu-id="e8a00-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e8a00-110">ENTSSO</span></span>|  
|<span data-ttu-id="e8a00-111">组件</span><span class="sxs-lookup"><span data-stu-id="e8a00-111">Component</span></span>|<span data-ttu-id="e8a00-112">N\A</span><span class="sxs-lookup"><span data-stu-id="e8a00-112">N\A</span></span>|  
|<span data-ttu-id="e8a00-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e8a00-113">Symbolic Name</span></span>|<span data-ttu-id="e8a00-114">SSO_INFO_DAMPED_EXTERNAL_PASSWORD_CHANGE</span><span class="sxs-lookup"><span data-stu-id="e8a00-114">SSO_INFO_DAMPED_EXTERNAL_PASSWORD_CHANGE</span></span>|  
|<span data-ttu-id="e8a00-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e8a00-115">Message Text</span></span>|<span data-ttu-id="e8a00-116">外部密码更改已阻止 （检测到重复项，discarded).%r</span><span class="sxs-lookup"><span data-stu-id="e8a00-116">An external password change was damped (detected as a duplicate and discarded).%r</span></span><br /><br /> <span data-ttu-id="e8a00-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e8a00-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="e8a00-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="e8a00-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="e8a00-119">外部帐户： %3</span><span class="sxs-lookup"><span data-stu-id="e8a00-119">External Account: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e8a00-120">解释</span><span class="sxs-lookup"><span data-stu-id="e8a00-120">Explanation</span></span>  
 <span data-ttu-id="e8a00-121">此信息事件表示系统认为外部密码更改是重复操作，因此被放弃。</span><span class="sxs-lookup"><span data-stu-id="e8a00-121">This Information event indicates that an external password change was determined to be a duplicate and discarded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e8a00-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="e8a00-122">User Action</span></span>  
  
-   <span data-ttu-id="e8a00-123">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="e8a00-123">No user action is necessary.</span></span>  
  
 <span data-ttu-id="e8a00-124">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="e8a00-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="e8a00-125">密码同步</span><span class="sxs-lookup"><span data-stu-id="e8a00-125">Password Synchronization</span></span>](../core/password-synchronization2.md)