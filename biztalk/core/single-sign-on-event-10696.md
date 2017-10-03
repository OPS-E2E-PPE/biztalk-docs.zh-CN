---
title: "单一登录： 事件 10696 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4dff6d08-8a1f-4137-bda7-55271071da55
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1a2b704b45774e0489f9c765cee45326bf0ff59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10696"></a><span data-ttu-id="0738c-102">单一登录： 事件 10696</span><span class="sxs-lookup"><span data-stu-id="0738c-102">Single Sign-On: Event 10696</span></span>
## <a name="details"></a><span data-ttu-id="0738c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0738c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0738c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0738c-104">Product Name</span></span>|<span data-ttu-id="0738c-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0738c-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0738c-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0738c-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0738c-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0738c-107">Event ID</span></span>|<span data-ttu-id="0738c-108">10696</span><span class="sxs-lookup"><span data-stu-id="0738c-108">10696</span></span>|  
|<span data-ttu-id="0738c-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0738c-109">Event Source</span></span>|<span data-ttu-id="0738c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0738c-110">ENTSSO</span></span>|  
|<span data-ttu-id="0738c-111">组件</span><span class="sxs-lookup"><span data-stu-id="0738c-111">Component</span></span>|<span data-ttu-id="0738c-112">N\A</span><span class="sxs-lookup"><span data-stu-id="0738c-112">N\A</span></span>|  
|<span data-ttu-id="0738c-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0738c-113">Symbolic Name</span></span>|<span data-ttu-id="0738c-114">SSO_ERROR_PROGRESS_INCORRECT_RECORD_VERSION</span><span class="sxs-lookup"><span data-stu-id="0738c-114">SSO_ERROR_PROGRESS_INCORRECT_RECORD_VERSION</span></span>|  
|<span data-ttu-id="0738c-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0738c-115">Message Text</span></span>|<span data-ttu-id="0738c-116">检测到进度文件已损坏。%r</span><span class="sxs-lookup"><span data-stu-id="0738c-116">Corruption was detected in the progress file.%r</span></span><br /><br /> <span data-ttu-id="0738c-117">文件名： %1</span><span class="sxs-lookup"><span data-stu-id="0738c-117">File Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0738c-118">解释</span><span class="sxs-lookup"><span data-stu-id="0738c-118">Explanation</span></span>  
 <span data-ttu-id="0738c-119">此错误事件表明 SSO 已与 SSO 数据库重新建立联系，但是由于进度文件损坏而无法对其进行读取。</span><span class="sxs-lookup"><span data-stu-id="0738c-119">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the progress file because of corruption.</span></span> <span data-ttu-id="0738c-120">如果 SSO 无法打开进度文件，则将在第一个重播文件的开始记录处启动。</span><span class="sxs-lookup"><span data-stu-id="0738c-120">If SSO cannot open a progress file, it will start at the beginning record of the first replay file.</span></span>  
  
 <span data-ttu-id="0738c-121">ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="0738c-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="0738c-122">进度文件指示距离通过 SSO 时能够读取文件的情况下与 SSO 数据库的联系重播再次将丢失。</span><span class="sxs-lookup"><span data-stu-id="0738c-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0738c-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="0738c-123">User Action</span></span>  
 <span data-ttu-id="0738c-124">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0738c-124">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="0738c-125">检查有相关事件的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="0738c-125">Check System and Application event logs for associated events.</span></span>  
  
 <span data-ttu-id="0738c-126">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="0738c-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="0738c-127">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="0738c-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="0738c-128">密码同步</span><span class="sxs-lookup"><span data-stu-id="0738c-128">Password Synchronization</span></span>](../core/password-synchronization2.md)