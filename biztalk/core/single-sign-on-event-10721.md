---
title: "单一登录： 事件 10721 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90295307-2dfa-4f21-9697-aaafd0a0b85e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcf17d9e32d56bba9985fe476a6830257889052a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10721"></a><span data-ttu-id="b213b-102">单一登录： 事件 10721</span><span class="sxs-lookup"><span data-stu-id="b213b-102">Single Sign-On: Event 10721</span></span>
## <a name="details"></a><span data-ttu-id="b213b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b213b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b213b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b213b-104">Product Name</span></span>|<span data-ttu-id="b213b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b213b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="b213b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="b213b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="b213b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b213b-107">Event ID</span></span>|<span data-ttu-id="b213b-108">10721</span><span class="sxs-lookup"><span data-stu-id="b213b-108">10721</span></span>|  
|<span data-ttu-id="b213b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b213b-109">Event Source</span></span>|<span data-ttu-id="b213b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b213b-110">ENTSSO</span></span>|  
|<span data-ttu-id="b213b-111">组件</span><span class="sxs-lookup"><span data-stu-id="b213b-111">Component</span></span>|<span data-ttu-id="b213b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="b213b-112">N\A</span></span>|  
|<span data-ttu-id="b213b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b213b-113">Symbolic Name</span></span>|<span data-ttu-id="b213b-114">SSO_INFO_REPLAY_FILE_CLOSED_FULL</span><span class="sxs-lookup"><span data-stu-id="b213b-114">SSO_INFO_REPLAY_FILE_CLOSED_FULL</span></span>|  
|<span data-ttu-id="b213b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b213b-115">Message Text</span></span>|<span data-ttu-id="b213b-116">重播文件已关闭，因为它已满。%r</span><span class="sxs-lookup"><span data-stu-id="b213b-116">The replay file has been closed because it is full.%r</span></span><br /><br /> <span data-ttu-id="b213b-117">文件名： %1</span><span class="sxs-lookup"><span data-stu-id="b213b-117">File Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b213b-118">解释</span><span class="sxs-lookup"><span data-stu-id="b213b-118">Explanation</span></span>  
 <span data-ttu-id="b213b-119">此信息事件表明，重播文件已关闭，因为它已满。</span><span class="sxs-lookup"><span data-stu-id="b213b-119">This Information event indicates that the replay file has been closed because it is full.</span></span> <span data-ttu-id="b213b-120">如有必要，将创建一个新的重播文件。</span><span class="sxs-lookup"><span data-stu-id="b213b-120">If necessary, a new replay file will be created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b213b-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="b213b-121">User Action</span></span>  
  
-   <span data-ttu-id="b213b-122">不必进行用户操作。</span><span class="sxs-lookup"><span data-stu-id="b213b-122">No user action is necessary</span></span>  
  
 <span data-ttu-id="b213b-123">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="b213b-123">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="b213b-124">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="b213b-124">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="b213b-125">密码同步</span><span class="sxs-lookup"><span data-stu-id="b213b-125">Password Synchronization</span></span>](../core/password-synchronization2.md)