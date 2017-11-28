---
title: "单一登录： 事件 10743 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2908bc9-1fac-4ab9-869f-0c5512864da4
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8368b39ff73307e36a4789d85c9771657bdf8e26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10743"></a><span data-ttu-id="f3f74-102">单一登录： 事件 10743</span><span class="sxs-lookup"><span data-stu-id="f3f74-102">Single Sign-On: Event 10743</span></span>
## <a name="details"></a><span data-ttu-id="f3f74-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f3f74-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f3f74-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f3f74-104">Product Name</span></span>|<span data-ttu-id="f3f74-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f3f74-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f3f74-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f3f74-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f3f74-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f3f74-107">Event ID</span></span>|<span data-ttu-id="f3f74-108">10743</span><span class="sxs-lookup"><span data-stu-id="f3f74-108">10743</span></span>|  
|<span data-ttu-id="f3f74-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f3f74-109">Event Source</span></span>|<span data-ttu-id="f3f74-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f3f74-110">ENTSSO</span></span>|  
|<span data-ttu-id="f3f74-111">组件</span><span class="sxs-lookup"><span data-stu-id="f3f74-111">Component</span></span>|<span data-ttu-id="f3f74-112">N\A</span><span class="sxs-lookup"><span data-stu-id="f3f74-112">N\A</span></span>|  
|<span data-ttu-id="f3f74-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f3f74-113">Symbolic Name</span></span>|<span data-ttu-id="f3f74-114">SSO_ERROR_REPLAY_STOPPED</span><span class="sxs-lookup"><span data-stu-id="f3f74-114">SSO_ERROR_REPLAY_STOPPED</span></span>|  
|<span data-ttu-id="f3f74-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f3f74-115">Message Text</span></span>|<span data-ttu-id="f3f74-116">由于发生错误，已停止重播存储的外部密码更改。%r</span><span class="sxs-lookup"><span data-stu-id="f3f74-116">Replay of stored external password changes stopped due to errors.%r</span></span><br /><br /> <span data-ttu-id="f3f74-117">重播文件: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f3f74-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="f3f74-118">其他数据: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f3f74-118">Additional Data: %2%r</span></span><br /><br /> <span data-ttu-id="f3f74-119">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="f3f74-119">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f3f74-120">解释</span><span class="sxs-lookup"><span data-stu-id="f3f74-120">Explanation</span></span>  
 <span data-ttu-id="f3f74-121">此错误事件表示，由于发生某些错误，已停止重播存储的外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="f3f74-121">This Error event indicates that replay of stored external password changes stopped due to errors.</span></span>  
  
 <span data-ttu-id="f3f74-122">ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="f3f74-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="f3f74-123">进度文件指示距离通过 SSO 时能够读取文件的情况下与 SSO 数据库的联系重播再次将丢失。</span><span class="sxs-lookup"><span data-stu-id="f3f74-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f3f74-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="f3f74-124">User Action</span></span>  
 <span data-ttu-id="f3f74-125">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f3f74-125">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="f3f74-126">检查有相关事件的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="f3f74-126">Check System and Application event logs for associated events.</span></span>  
  
 <span data-ttu-id="f3f74-127">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="f3f74-127">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="f3f74-128">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="f3f74-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="f3f74-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="f3f74-129">Password Synchronization</span></span>](../core/password-synchronization2.md)