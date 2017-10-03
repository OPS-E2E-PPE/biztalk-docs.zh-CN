---
title: "单一登录： 事件 10682 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46f0f425-3946-4bac-a412-488c4afe460d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79aeff556fbbbbbbbcf41f63a37ab3b47311d697
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10682"></a><span data-ttu-id="4a2bb-102">单一登录： 事件 10682</span><span class="sxs-lookup"><span data-stu-id="4a2bb-102">Single Sign-On: Event 10682</span></span>
## <a name="details"></a><span data-ttu-id="4a2bb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="4a2bb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4a2bb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="4a2bb-104">Product Name</span></span>|<span data-ttu-id="4a2bb-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="4a2bb-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="4a2bb-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="4a2bb-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="4a2bb-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4a2bb-107">Event ID</span></span>|<span data-ttu-id="4a2bb-108">10682</span><span class="sxs-lookup"><span data-stu-id="4a2bb-108">10682</span></span>|  
|<span data-ttu-id="4a2bb-109">事件源</span><span class="sxs-lookup"><span data-stu-id="4a2bb-109">Event Source</span></span>|<span data-ttu-id="4a2bb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4a2bb-110">ENTSSO</span></span>|  
|<span data-ttu-id="4a2bb-111">组件</span><span class="sxs-lookup"><span data-stu-id="4a2bb-111">Component</span></span>|<span data-ttu-id="4a2bb-112">N\A</span><span class="sxs-lookup"><span data-stu-id="4a2bb-112">N\A</span></span>|  
|<span data-ttu-id="4a2bb-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="4a2bb-113">Symbolic Name</span></span>|<span data-ttu-id="4a2bb-114">SSO_WARN_REPLAY_INVALID_DIR_FOUND</span><span class="sxs-lookup"><span data-stu-id="4a2bb-114">SSO_WARN_REPLAY_INVALID_DIR_FOUND</span></span>|  
|<span data-ttu-id="4a2bb-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="4a2bb-115">Message Text</span></span>|<span data-ttu-id="4a2bb-116">找到一个目录中重播文件目录-它将 ignored.%r</span><span class="sxs-lookup"><span data-stu-id="4a2bb-116">A directory was found in the replay files directory - it will be ignored.%r</span></span><br /><span data-ttu-id="4a2bb-117">目录： %1</span><span class="sxs-lookup"><span data-stu-id="4a2bb-117">Directory: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4a2bb-118">解释</span><span class="sxs-lookup"><span data-stu-id="4a2bb-118">Explanation</span></span>  
 <span data-ttu-id="4a2bb-119">此警告事件表明在重播文件目录中找到一个目录。</span><span class="sxs-lookup"><span data-stu-id="4a2bb-119">This Warning event indicates that a directory was found in the replay files directory.</span></span> <span data-ttu-id="4a2bb-120">ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="4a2bb-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="4a2bb-121">在这种情况下，密码更改存储在临时加密文件中，并在该文件再次可用时重播回 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="4a2bb-121">In this case the password changes are stored in a temporary encrypted file, and are replayed back to the SSO database when it becomes available again.</span></span> <span data-ttu-id="4a2bb-122">重播文件目录应只包含重播文件（如果找到一个目录，则会发出此错误消息）。</span><span class="sxs-lookup"><span data-stu-id="4a2bb-122">The replay files directory is expected to contain only replay files – this error message is issued if a directory is found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4a2bb-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="4a2bb-123">User Action</span></span>  
 <span data-ttu-id="4a2bb-124">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="4a2bb-124">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="4a2bb-125">使用命令行工具 ssoconfig-replayFiles 更改您的重播目录。</span><span class="sxs-lookup"><span data-stu-id="4a2bb-125">Use command line tool ssoconfig -replayFiles to  change your replay directory.</span></span>  
  
-   <span data-ttu-id="4a2bb-126">删除损坏的目录（如果未使用）。</span><span class="sxs-lookup"><span data-stu-id="4a2bb-126">Delete the bad directory if it is not in use.</span></span>  
  
 <span data-ttu-id="4a2bb-127">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="4a2bb-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="4a2bb-128">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="4a2bb-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="4a2bb-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="4a2bb-129">Password Synchronization</span></span>](../core/password-synchronization2.md)