---
title: 单一登录： 事件 10524 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55e26da3-f67f-4f87-92e5-2f8765b19989
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c79da37aaa54f44daaa39048fcdf58e67064f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271837"
---
# <a name="single-sign-on-event-10524"></a><span data-ttu-id="f7262-102">单一登录： 事件 10524</span><span class="sxs-lookup"><span data-stu-id="f7262-102">Single Sign-On: Event 10524</span></span>
## <a name="details"></a><span data-ttu-id="f7262-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f7262-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f7262-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f7262-104">Product Name</span></span>|<span data-ttu-id="f7262-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f7262-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f7262-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f7262-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f7262-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f7262-107">Event ID</span></span>|<span data-ttu-id="f7262-108">10524</span><span class="sxs-lookup"><span data-stu-id="f7262-108">10524</span></span>|  
|<span data-ttu-id="f7262-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f7262-109">Event Source</span></span>|<span data-ttu-id="f7262-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f7262-110">ENTSSO</span></span>|  
|<span data-ttu-id="f7262-111">组件</span><span class="sxs-lookup"><span data-stu-id="f7262-111">Component</span></span>|<span data-ttu-id="f7262-112">N\A</span><span class="sxs-lookup"><span data-stu-id="f7262-112">N\A</span></span>|  
|<span data-ttu-id="f7262-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f7262-113">Symbolic Name</span></span>|<span data-ttu-id="f7262-114">SSO_ERROR_RESTORE_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="f7262-114">SSO_ERROR_RESTORE_SECRET_FAILED</span></span>|  
|<span data-ttu-id="f7262-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f7262-115">Message Text</span></span>|<span data-ttu-id="f7262-116">无法还原主密钥 secrets.%r</span><span class="sxs-lookup"><span data-stu-id="f7262-116">Failed to restore the master secrets.%r</span></span><br /><br /> <span data-ttu-id="f7262-117">文件名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f7262-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="f7262-118">当前 MSID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f7262-118">Current MSID: %2%r</span></span><br /><br /> <span data-ttu-id="f7262-119">上一个 MSID: %3 %r</span><span class="sxs-lookup"><span data-stu-id="f7262-119">Previous MSID: %3%r</span></span><br /><br /> <span data-ttu-id="f7262-120">客户端用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="f7262-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="f7262-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="f7262-121">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f7262-122">解释</span><span class="sxs-lookup"><span data-stu-id="f7262-122">Explanation</span></span>  
 <span data-ttu-id="f7262-123">此错误事件指示用户尝试从备份文件还原主密钥失败。</span><span class="sxs-lookup"><span data-stu-id="f7262-123">This Error event indicates that a user attempt to restore the master secrets from a backup file failed.</span></span> <span data-ttu-id="f7262-124">这可能是由于权限问题（您必须是 SSO 管理员才能还原主密钥）或者可能是备份文件损坏。</span><span class="sxs-lookup"><span data-stu-id="f7262-124">This might be due to permissions issues (you must be an SSO Administrator to restore the master secret) or possibly due to file corruption of the backup file.</span></span> <span data-ttu-id="f7262-125">在这些情况下应用程序事件日志中应会出现相关的消息。</span><span class="sxs-lookup"><span data-stu-id="f7262-125">In these cases there should be related messages in the Application event log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f7262-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="f7262-126">User Action</span></span>  
 <span data-ttu-id="f7262-127">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="f7262-127">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="f7262-128">请检查关联的事件或错误的应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="f7262-128">Check the Application event log for associated events or errors.</span></span>  
  
-   <span data-ttu-id="f7262-129">检查您是否具有相应的 SSO 管理员权限。</span><span class="sxs-lookup"><span data-stu-id="f7262-129">Check that you have the appropriate SSO Administrator permissions.</span></span>  
  
 <span data-ttu-id="f7262-130">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="f7262-130">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="f7262-131">如何还原主密钥</span><span class="sxs-lookup"><span data-stu-id="f7262-131">How to Restore the Master Secret</span></span>](../core/how-to-restore-the-master-secret.md)  
  
-   [<span data-ttu-id="f7262-132">如何备份主密钥</span><span class="sxs-lookup"><span data-stu-id="f7262-132">How to Back Up the Master Secret</span></span>](../core/how-to-back-up-the-master-secret.md)  
  
-   [<span data-ttu-id="f7262-133">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="f7262-133">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)