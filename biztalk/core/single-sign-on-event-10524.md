---
title: 单一登录： 事件 10524 |Microsoft Docs
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
ms.openlocfilehash: 3f873dab5d4d5f00897e498e2bb88b6ae9a2f040
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009502"
---
# <a name="single-sign-on-event-10524"></a><span data-ttu-id="848c1-102">单一登录： 事件 10524</span><span class="sxs-lookup"><span data-stu-id="848c1-102">Single Sign-On: Event 10524</span></span>
## <a name="details"></a><span data-ttu-id="848c1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="848c1-103">Details</span></span>  

|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="848c1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="848c1-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="848c1-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="848c1-105">Enterprise Single Sign-On</span></span>                                                                                  |
| <span data-ttu-id="848c1-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="848c1-106">Product Version</span></span> |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="848c1-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="848c1-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="848c1-108">10524</span><span class="sxs-lookup"><span data-stu-id="848c1-108">10524</span></span>                                                                                            |
|  <span data-ttu-id="848c1-109">事件源</span><span class="sxs-lookup"><span data-stu-id="848c1-109">Event Source</span></span>   |                                                                                           <span data-ttu-id="848c1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="848c1-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="848c1-111">组件</span><span class="sxs-lookup"><span data-stu-id="848c1-111">Component</span></span>    |                                                                                             <span data-ttu-id="848c1-112">N\A</span><span class="sxs-lookup"><span data-stu-id="848c1-112">N\A</span></span>                                                                                             |
|  <span data-ttu-id="848c1-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="848c1-113">Symbolic Name</span></span>  |                                                                               <span data-ttu-id="848c1-114">SSO_ERROR_RESTORE_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="848c1-114">SSO_ERROR_RESTORE_SECRET_FAILED</span></span>                                                                               |
|  <span data-ttu-id="848c1-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="848c1-115">Message Text</span></span>   | <span data-ttu-id="848c1-116">无法还原主密钥 secrets.%r</span><span class="sxs-lookup"><span data-stu-id="848c1-116">Failed to restore the master secrets.%r</span></span><br /><br /> <span data-ttu-id="848c1-117">文件名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="848c1-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="848c1-118">当前 MSID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="848c1-118">Current MSID: %2%r</span></span><br /><br /> <span data-ttu-id="848c1-119">上一个 MSID: %3 %r</span><span class="sxs-lookup"><span data-stu-id="848c1-119">Previous MSID: %3%r</span></span><br /><br /> <span data-ttu-id="848c1-120">客户端用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="848c1-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="848c1-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="848c1-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="848c1-122">解释</span><span class="sxs-lookup"><span data-stu-id="848c1-122">Explanation</span></span>  
 <span data-ttu-id="848c1-123">此错误事件表示用户尝试从备份文件还原主密钥失败。</span><span class="sxs-lookup"><span data-stu-id="848c1-123">This Error event indicates that a user attempt to restore the master secrets from a backup file failed.</span></span> <span data-ttu-id="848c1-124">这可能是由于权限问题（您必须是 SSO 管理员才能还原主密钥）或者可能是备份文件损坏。</span><span class="sxs-lookup"><span data-stu-id="848c1-124">This might be due to permissions issues (you must be an SSO Administrator to restore the master secret) or possibly due to file corruption of the backup file.</span></span> <span data-ttu-id="848c1-125">在这些情况下应该有相关的邮件应用程序事件日志中。</span><span class="sxs-lookup"><span data-stu-id="848c1-125">In these cases there should be related messages in the Application event log.</span></span>  

## <a name="user-action"></a><span data-ttu-id="848c1-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="848c1-126">User Action</span></span>  
 <span data-ttu-id="848c1-127">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="848c1-127">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="848c1-128">检查应用程序事件日志关联的事件或错误。</span><span class="sxs-lookup"><span data-stu-id="848c1-128">Check the Application event log for associated events or errors.</span></span>  

- <span data-ttu-id="848c1-129">检查您是否具有相应的 SSO 管理员权限。</span><span class="sxs-lookup"><span data-stu-id="848c1-129">Check that you have the appropriate SSO Administrator permissions.</span></span>  

  <span data-ttu-id="848c1-130">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="848c1-130">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="848c1-131">如何还原主密钥</span><span class="sxs-lookup"><span data-stu-id="848c1-131">How to Restore the Master Secret</span></span>](../core/how-to-restore-the-master-secret.md)  

- [<span data-ttu-id="848c1-132">如何备份主密钥</span><span class="sxs-lookup"><span data-stu-id="848c1-132">How to Back Up the Master Secret</span></span>](../core/how-to-back-up-the-master-secret.md)  

- [<span data-ttu-id="848c1-133">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="848c1-133">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)
