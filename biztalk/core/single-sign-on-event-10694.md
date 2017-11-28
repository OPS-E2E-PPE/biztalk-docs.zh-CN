---
title: "单一登录： 事件 10694 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75faca65-48d9-45f6-b079-2b612ef3de76
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c11d30b30f55c04b8f3023740a8e0f488c5762e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10694"></a><span data-ttu-id="8863a-102">单一登录： 事件 10694</span><span class="sxs-lookup"><span data-stu-id="8863a-102">Single Sign-On: Event 10694</span></span>
## <a name="details"></a><span data-ttu-id="8863a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8863a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8863a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8863a-104">Product Name</span></span>|<span data-ttu-id="8863a-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="8863a-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="8863a-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="8863a-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="8863a-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8863a-107">Event ID</span></span>|<span data-ttu-id="8863a-108">10694</span><span class="sxs-lookup"><span data-stu-id="8863a-108">10694</span></span>|  
|<span data-ttu-id="8863a-109">事件源</span><span class="sxs-lookup"><span data-stu-id="8863a-109">Event Source</span></span>|<span data-ttu-id="8863a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8863a-110">ENTSSO</span></span>|  
|<span data-ttu-id="8863a-111">组件</span><span class="sxs-lookup"><span data-stu-id="8863a-111">Component</span></span>|<span data-ttu-id="8863a-112">N\A</span><span class="sxs-lookup"><span data-stu-id="8863a-112">N\A</span></span>|  
|<span data-ttu-id="8863a-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="8863a-113">Symbolic Name</span></span>|<span data-ttu-id="8863a-114">SSO_ERROR_REPLAY_INCORRECT_VERSION</span><span class="sxs-lookup"><span data-stu-id="8863a-114">SSO_ERROR_REPLAY_INCORRECT_VERSION</span></span>|  
|<span data-ttu-id="8863a-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="8863a-115">Message Text</span></span>|<span data-ttu-id="8863a-116">重播文件或进度 file.%r 中检测到损坏</span><span class="sxs-lookup"><span data-stu-id="8863a-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="8863a-117">文件名： %1</span><span class="sxs-lookup"><span data-stu-id="8863a-117">File Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8863a-118">解释</span><span class="sxs-lookup"><span data-stu-id="8863a-118">Explanation</span></span>  
 <span data-ttu-id="8863a-119">SSO 已重新建立与 SSO 数据库的联系，但无法读取重播文件，因为损坏，该值指示此错误事件。</span><span class="sxs-lookup"><span data-stu-id="8863a-119">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="8863a-120">如果 SSO 无法打开重播文件，将会继续执行下一步的重播文件 （如果有）。</span><span class="sxs-lookup"><span data-stu-id="8863a-120">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  
  
 <span data-ttu-id="8863a-121">ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="8863a-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="8863a-122">进度文件指示距离通过 SSO 时能够读取文件的情况下与 SSO 数据库的联系重播再次将丢失。</span><span class="sxs-lookup"><span data-stu-id="8863a-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8863a-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="8863a-123">User Action</span></span>  
 <span data-ttu-id="8863a-124">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8863a-124">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="8863a-125">检查有相关事件的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="8863a-125">Check System and Application event logs for associated events.</span></span>  
  
 <span data-ttu-id="8863a-126">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="8863a-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="8863a-127">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="8863a-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="8863a-128">密码同步</span><span class="sxs-lookup"><span data-stu-id="8863a-128">Password Synchronization</span></span>](../core/password-synchronization2.md)