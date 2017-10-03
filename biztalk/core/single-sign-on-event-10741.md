---
title: "单一登录： 事件 10741 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58b6b093-d136-498f-a3b5-c413150da956
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52ad76e20937bfa4af1dbec6d71ba59003874435
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10741"></a><span data-ttu-id="31259-102">单一登录： 事件 10741</span><span class="sxs-lookup"><span data-stu-id="31259-102">Single Sign-On: Event 10741</span></span>
## <a name="details"></a><span data-ttu-id="31259-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="31259-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="31259-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="31259-104">Product Name</span></span>|<span data-ttu-id="31259-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="31259-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="31259-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="31259-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="31259-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="31259-107">Event ID</span></span>|<span data-ttu-id="31259-108">10741</span><span class="sxs-lookup"><span data-stu-id="31259-108">10741</span></span>|  
|<span data-ttu-id="31259-109">事件源</span><span class="sxs-lookup"><span data-stu-id="31259-109">Event Source</span></span>|<span data-ttu-id="31259-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="31259-110">ENTSSO</span></span>|  
|<span data-ttu-id="31259-111">组件</span><span class="sxs-lookup"><span data-stu-id="31259-111">Component</span></span>|<span data-ttu-id="31259-112">N\A</span><span class="sxs-lookup"><span data-stu-id="31259-112">N\A</span></span>|  
|<span data-ttu-id="31259-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="31259-113">Symbolic Name</span></span>|<span data-ttu-id="31259-114">SSO_WARN_SAVING_REPLAY_FILE</span><span class="sxs-lookup"><span data-stu-id="31259-114">SSO_WARN_SAVING_REPLAY_FILE</span></span>|  
|<span data-ttu-id="31259-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="31259-115">Message Text</span></span>|<span data-ttu-id="31259-116">正在保存重播文件或进度文件。%r</span><span class="sxs-lookup"><span data-stu-id="31259-116">Saving replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="31259-117">保存文件: %1 %r</span><span class="sxs-lookup"><span data-stu-id="31259-117">Saved File: %1%r</span></span><br /><br /> <span data-ttu-id="31259-118">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="31259-118">Error Code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="31259-119">解释</span><span class="sxs-lookup"><span data-stu-id="31259-119">Explanation</span></span>  
 <span data-ttu-id="31259-120">此警告事件表明 SSO 正在保存重播文件或进度文件。</span><span class="sxs-lookup"><span data-stu-id="31259-120">This Warning event indicates that SSO is saving a replay or progress file.</span></span>  
  
 <span data-ttu-id="31259-121">ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="31259-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="31259-122">进度文件指示距离通过 SSO 时能够读取文件的情况下与 SSO 数据库的联系重播再次将丢失。</span><span class="sxs-lookup"><span data-stu-id="31259-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="31259-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="31259-123">User Action</span></span>  
  
-   <span data-ttu-id="31259-124">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="31259-124">No user action is necessary.</span></span>  
  
 <span data-ttu-id="31259-125">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="31259-125">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="31259-126">密码同步</span><span class="sxs-lookup"><span data-stu-id="31259-126">Password Synchronization</span></span>](../core/password-synchronization2.md)