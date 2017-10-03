---
title: "单一登录： 事件 10699 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cff26533-e4d7-47b5-92d5-bd8c72fab89a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b6ceb4ffe1e25a3828f406b881d4070b74a8d9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10699"></a><span data-ttu-id="0e926-102">单一登录： 事件 10699</span><span class="sxs-lookup"><span data-stu-id="0e926-102">Single Sign-On: Event 10699</span></span>
## <a name="details"></a><span data-ttu-id="0e926-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0e926-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0e926-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0e926-104">Product Name</span></span>|<span data-ttu-id="0e926-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0e926-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0e926-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0e926-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0e926-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0e926-107">Event ID</span></span>|<span data-ttu-id="0e926-108">10699</span><span class="sxs-lookup"><span data-stu-id="0e926-108">10699</span></span>|  
|<span data-ttu-id="0e926-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0e926-109">Event Source</span></span>|<span data-ttu-id="0e926-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0e926-110">ENTSSO</span></span>|  
|<span data-ttu-id="0e926-111">组件</span><span class="sxs-lookup"><span data-stu-id="0e926-111">Component</span></span>|<span data-ttu-id="0e926-112">N\A</span><span class="sxs-lookup"><span data-stu-id="0e926-112">N\A</span></span>|  
|<span data-ttu-id="0e926-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0e926-113">Symbolic Name</span></span>|<span data-ttu-id="0e926-114">SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY</span><span class="sxs-lookup"><span data-stu-id="0e926-114">SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY</span></span>|  
|<span data-ttu-id="0e926-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0e926-115">Message Text</span></span>|<span data-ttu-id="0e926-116">从适配器（从重播文件）接收到一个外部密码更改。%r</span><span class="sxs-lookup"><span data-stu-id="0e926-116">An external password change was received from an adapter (from replay file).%r</span></span><br /><br /> <span data-ttu-id="0e926-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0e926-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="0e926-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="0e926-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="0e926-119">外部帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="0e926-119">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="0e926-120">客户端用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="0e926-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="0e926-121">记录数： %5</span><span class="sxs-lookup"><span data-stu-id="0e926-121">Record Number: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0e926-122">解释</span><span class="sxs-lookup"><span data-stu-id="0e926-122">Explanation</span></span>  
 <span data-ttu-id="0e926-123">此信息性事件表示，从适配器接收到一个外部密码更改，此项更改记录在一个重播文件中。</span><span class="sxs-lookup"><span data-stu-id="0e926-123">This Information event indicates that an external password change was received from an adapter that was recorded to a replay file.</span></span> <span data-ttu-id="0e926-124">SSO 正在重播来自重播文件的已存储外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="0e926-124">SSO is replaying the stored external password changes from the replay file.</span></span>  
  
 <span data-ttu-id="0e926-125">ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="0e926-125">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="0e926-126">进度文件指示距离通过 SSO 时能够读取文件的情况下与 SSO 数据库的联系重播再次将丢失。</span><span class="sxs-lookup"><span data-stu-id="0e926-126">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0e926-127">用户操作</span><span class="sxs-lookup"><span data-stu-id="0e926-127">User Action</span></span>  
  
-   <span data-ttu-id="0e926-128">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="0e926-128">No user action is necessary.</span></span>  
  
 <span data-ttu-id="0e926-129">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="0e926-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="0e926-130">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="0e926-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="0e926-131">密码同步</span><span class="sxs-lookup"><span data-stu-id="0e926-131">Password Synchronization</span></span>](../core/password-synchronization2.md)