---
title: "单一登录： 事件 10698 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f467934d-fef5-4962-a341-18f272d84108
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ca4d65927e7e9d01f7c73eb64a19bc613496f5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10698"></a><span data-ttu-id="42c19-102">单一登录： 事件 10698</span><span class="sxs-lookup"><span data-stu-id="42c19-102">Single Sign-On: Event 10698</span></span>
## <a name="details"></a><span data-ttu-id="42c19-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="42c19-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42c19-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="42c19-104">Product Name</span></span>|<span data-ttu-id="42c19-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="42c19-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="42c19-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="42c19-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="42c19-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="42c19-107">Event ID</span></span>|<span data-ttu-id="42c19-108">10698</span><span class="sxs-lookup"><span data-stu-id="42c19-108">10698</span></span>|  
|<span data-ttu-id="42c19-109">事件源</span><span class="sxs-lookup"><span data-stu-id="42c19-109">Event Source</span></span>|<span data-ttu-id="42c19-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="42c19-110">ENTSSO</span></span>|  
|<span data-ttu-id="42c19-111">组件</span><span class="sxs-lookup"><span data-stu-id="42c19-111">Component</span></span>|<span data-ttu-id="42c19-112">N\A</span><span class="sxs-lookup"><span data-stu-id="42c19-112">N\A</span></span>|  
|<span data-ttu-id="42c19-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="42c19-113">Symbolic Name</span></span>|<span data-ttu-id="42c19-114">SSO_INFO_REPLAY_FILE_DELETED</span><span class="sxs-lookup"><span data-stu-id="42c19-114">SSO_INFO_REPLAY_FILE_DELETED</span></span>|  
|<span data-ttu-id="42c19-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="42c19-115">Message Text</span></span>|<span data-ttu-id="42c19-116">重播文件或进度文件已 deleted.%r</span><span class="sxs-lookup"><span data-stu-id="42c19-116">The replay or progress file was deleted.%r</span></span><br /><br /> <span data-ttu-id="42c19-117">文件名： %1</span><span class="sxs-lookup"><span data-stu-id="42c19-117">File Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="42c19-118">解释</span><span class="sxs-lookup"><span data-stu-id="42c19-118">Explanation</span></span>  
 <span data-ttu-id="42c19-119">此信息事件指示 SSO 已删除了某个重播和/或进度文件。</span><span class="sxs-lookup"><span data-stu-id="42c19-119">This Information event indicates that SSO has deleted a replay and\or progress file.</span></span>  
  
 <span data-ttu-id="42c19-120">ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="42c19-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="42c19-121">进度文件指示距离通过 SSO 时能够读取文件的情况下与 SSO 数据库的联系重播再次将丢失。</span><span class="sxs-lookup"><span data-stu-id="42c19-121">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="42c19-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="42c19-122">User Action</span></span>  
  
-   <span data-ttu-id="42c19-123">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="42c19-123">No user action is necessary.</span></span>  
  
 <span data-ttu-id="42c19-124">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="42c19-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="42c19-125">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="42c19-125">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="42c19-126">密码同步</span><span class="sxs-lookup"><span data-stu-id="42c19-126">Password Synchronization</span></span>](../core/password-synchronization2.md)