---
title: "单一登录： 事件 10688 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63fe4ac5-dc1d-4d5a-8ce3-40ed4556afcf
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96e93263c8be58fd7fd2cecb40d3daee16baae09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10688"></a><span data-ttu-id="185f7-102">单一登录： 事件 10688</span><span class="sxs-lookup"><span data-stu-id="185f7-102">Single Sign-On: Event 10688</span></span>
## <a name="details"></a><span data-ttu-id="185f7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="185f7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="185f7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="185f7-104">Product Name</span></span>|<span data-ttu-id="185f7-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="185f7-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="185f7-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="185f7-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="185f7-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="185f7-107">Event ID</span></span>|<span data-ttu-id="185f7-108">10688</span><span class="sxs-lookup"><span data-stu-id="185f7-108">10688</span></span>|  
|<span data-ttu-id="185f7-109">事件源</span><span class="sxs-lookup"><span data-stu-id="185f7-109">Event Source</span></span>|<span data-ttu-id="185f7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="185f7-110">ENTSSO</span></span>|  
|<span data-ttu-id="185f7-111">组件</span><span class="sxs-lookup"><span data-stu-id="185f7-111">Component</span></span>|<span data-ttu-id="185f7-112">N\A</span><span class="sxs-lookup"><span data-stu-id="185f7-112">N\A</span></span>|  
|<span data-ttu-id="185f7-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="185f7-113">Symbolic Name</span></span>|<span data-ttu-id="185f7-114">SSO_ERROR_REPLAY_FILE_UNEXPECTED_DATA</span><span class="sxs-lookup"><span data-stu-id="185f7-114">SSO_ERROR_REPLAY_FILE_UNEXPECTED_DATA</span></span>|  
|<span data-ttu-id="185f7-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="185f7-115">Message Text</span></span>|<span data-ttu-id="185f7-116">重播 file.%r 中检测到损坏</span><span class="sxs-lookup"><span data-stu-id="185f7-116">Corruption was detected in the replay file.%r</span></span><br /><br /> <span data-ttu-id="185f7-117">重播文件： %1</span><span class="sxs-lookup"><span data-stu-id="185f7-117">Replay File: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="185f7-118">解释</span><span class="sxs-lookup"><span data-stu-id="185f7-118">Explanation</span></span>  
 <span data-ttu-id="185f7-119">SSO 已重新建立与 SSO 数据库的联系，但无法读取重播文件，因为损坏，该值指示此错误事件。</span><span class="sxs-lookup"><span data-stu-id="185f7-119">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="185f7-120">如果 SSO 无法打开重播文件，将会继续执行下一步的重播文件 （如果有）。</span><span class="sxs-lookup"><span data-stu-id="185f7-120">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  
  
 <span data-ttu-id="185f7-121">ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="185f7-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="185f7-122">进度文件指示距离通过 SSO 时能够读取文件的情况下与 SSO 数据库的联系重播再次将丢失。</span><span class="sxs-lookup"><span data-stu-id="185f7-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="185f7-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="185f7-123">User Action</span></span>  
 <span data-ttu-id="185f7-124">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="185f7-124">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="185f7-125">检查有相关事件的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="185f7-125">Check System and Application event logs for associated events.</span></span>  
  
-   <span data-ttu-id="185f7-126">删除重播文件。</span><span class="sxs-lookup"><span data-stu-id="185f7-126">Delete the replay file.</span></span>  
  
 <span data-ttu-id="185f7-127">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="185f7-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="185f7-128">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="185f7-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="185f7-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="185f7-129">Password Synchronization</span></span>](../core/password-synchronization2.md)