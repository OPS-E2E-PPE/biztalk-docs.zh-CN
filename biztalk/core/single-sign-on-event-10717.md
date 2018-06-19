---
title: 单一登录： 事件 10717 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14691e0f-a399-4b4d-9dd5-516bf8d3a167
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70195251b599daebd50b57f0b137dd026dd032e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270357"
---
# <a name="single-sign-on-event-10717"></a><span data-ttu-id="391e0-102">单一登录： 事件 10717</span><span class="sxs-lookup"><span data-stu-id="391e0-102">Single Sign-On: Event 10717</span></span>
## <a name="details"></a><span data-ttu-id="391e0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="391e0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="391e0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="391e0-104">Product Name</span></span>|<span data-ttu-id="391e0-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="391e0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="391e0-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="391e0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="391e0-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="391e0-107">Event ID</span></span>|<span data-ttu-id="391e0-108">10717</span><span class="sxs-lookup"><span data-stu-id="391e0-108">10717</span></span>|  
|<span data-ttu-id="391e0-109">事件源</span><span class="sxs-lookup"><span data-stu-id="391e0-109">Event Source</span></span>|<span data-ttu-id="391e0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="391e0-110">ENTSSO</span></span>|  
|<span data-ttu-id="391e0-111">组件</span><span class="sxs-lookup"><span data-stu-id="391e0-111">Component</span></span>|<span data-ttu-id="391e0-112">N\A</span><span class="sxs-lookup"><span data-stu-id="391e0-112">N\A</span></span>|  
|<span data-ttu-id="391e0-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="391e0-113">Symbolic Name</span></span>|<span data-ttu-id="391e0-114">SSO_ERROR_NEW_REPLAY_DIR_FAILED</span><span class="sxs-lookup"><span data-stu-id="391e0-114">SSO_ERROR_NEW_REPLAY_DIR_FAILED</span></span>|  
|<span data-ttu-id="391e0-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="391e0-115">Message Text</span></span>|<span data-ttu-id="391e0-116">创建重播文件目录失败。%r</span><span class="sxs-lookup"><span data-stu-id="391e0-116">Failed to create the replay files directory.%r</span></span><br /><br /> <span data-ttu-id="391e0-117">客户端用户: %1 %r</span><span class="sxs-lookup"><span data-stu-id="391e0-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="391e0-118">重播文件目录: %2 %r</span><span class="sxs-lookup"><span data-stu-id="391e0-118">Replay Files Directory: %2%r</span></span><br /><br /> <span data-ttu-id="391e0-119">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="391e0-119">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="391e0-120">解释</span><span class="sxs-lookup"><span data-stu-id="391e0-120">Explanation</span></span>  
 <span data-ttu-id="391e0-121">此错误事件表示无法创建重播文件目录。</span><span class="sxs-lookup"><span data-stu-id="391e0-121">This Error event indicates that a replay files directory could not be created.</span></span>  
  
 <span data-ttu-id="391e0-122">当 SSO 服务从密码同步适配器接收到密码更改时，这些更改存储在 SSO 数据库中。</span><span class="sxs-lookup"><span data-stu-id="391e0-122">When password changes are received by the SSO service from a password sync adapter, they are stored in the SSO database.</span></span> <span data-ttu-id="391e0-123">如果 SSO 数据库暂时不可用，则密码更改将存储在本地重播文件中。</span><span class="sxs-lookup"><span data-stu-id="391e0-123">If the SSO database is temporarily unavailable, the password changes are stored locally in replay files.</span></span> <span data-ttu-id="391e0-124">重播文件存储在重播文件目录中。</span><span class="sxs-lookup"><span data-stu-id="391e0-124">Replay files are stored in the replay files directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="391e0-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="391e0-125">User Action</span></span>  
 <span data-ttu-id="391e0-126">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="391e0-126">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="391e0-127">检查重播文件目录，如果该目录不存在，则尝试使用与 SSO 服务相同的服务帐户手动创建该目录。</span><span class="sxs-lookup"><span data-stu-id="391e0-127">Check the replay files directory, if one does not exist, attempt to create it manually using the same service account as the SSO service.</span></span> <span data-ttu-id="391e0-128">如果无法使用与 SSO 服务相同的帐户创建重播文件目录，则检查该帐户的权限。</span><span class="sxs-lookup"><span data-stu-id="391e0-128">If you cannot create a replay files directory using the same account as the SSO service, check permissions for that account.</span></span>  
  
 <span data-ttu-id="391e0-129">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="391e0-129">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="391e0-130">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="391e0-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="391e0-131">密码同步</span><span class="sxs-lookup"><span data-stu-id="391e0-131">Password Synchronization</span></span>](../core/password-synchronization2.md)