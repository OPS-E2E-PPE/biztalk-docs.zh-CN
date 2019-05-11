---
title: 消息类型不支持部分没有 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0bfb042-feda-4282-a7fa-c13be4ff6254
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef2ef118aab93f10d766aeaf34af74a23908822
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394537"
---
# <a name="message-types-without-parts-are-not-supported"></a><span data-ttu-id="51669-102">不支持没有部分消息类型</span><span class="sxs-lookup"><span data-stu-id="51669-102">Message types without parts are not supported</span></span>
## <a name="details"></a><span data-ttu-id="51669-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="51669-103">Details</span></span>  
  
|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="51669-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="51669-104">Product Name</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| <span data-ttu-id="51669-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="51669-105">Product Version</span></span> |                                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                 |
|    <span data-ttu-id="51669-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="51669-106">Event ID</span></span>     |                                                             <span data-ttu-id="51669-107">0</span><span class="sxs-lookup"><span data-stu-id="51669-107">0</span></span>                                                             |
|  <span data-ttu-id="51669-108">事件源</span><span class="sxs-lookup"><span data-stu-id="51669-108">Event Source</span></span>   |                                                             <span data-ttu-id="51669-109">0</span><span class="sxs-lookup"><span data-stu-id="51669-109">0</span></span>                                                             |
|    <span data-ttu-id="51669-110">组件</span><span class="sxs-lookup"><span data-stu-id="51669-110">Component</span></span>    |                                                             <span data-ttu-id="51669-111">0</span><span class="sxs-lookup"><span data-stu-id="51669-111">0</span></span>                                                             |
|  <span data-ttu-id="51669-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="51669-112">Symbolic Name</span></span>  |                                                             <span data-ttu-id="51669-113">0</span><span class="sxs-lookup"><span data-stu-id="51669-113">0</span></span>                                                             |
|  <span data-ttu-id="51669-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="51669-114">Message Text</span></span>   | <span data-ttu-id="51669-115">不支持没有部分的消息类型。</span><span class="sxs-lookup"><span data-stu-id="51669-115">Message types without parts are not supported.</span></span> <span data-ttu-id="51669-116">更正服务说明"{0}"消息类型"{1}"，然后重新运行该向导。</span><span class="sxs-lookup"><span data-stu-id="51669-116">Correct service description "{0}" message type "{1}" and rerun the wizard.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="51669-117">解释</span><span class="sxs-lookup"><span data-stu-id="51669-117">Explanation</span></span>  
 <span data-ttu-id="51669-118">此错误表示尝试使用该服务不具有定义的消息类型。</span><span class="sxs-lookup"><span data-stu-id="51669-118">This error indicates the service that is trying to be consumed does not have a message type defined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="51669-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="51669-119">User Action</span></span>  
 <span data-ttu-id="51669-120">更正服务与相应的消息类型，然后尝试使用 （如果您拥有要尝试使用的 WCF 服务）。</span><span class="sxs-lookup"><span data-stu-id="51669-120">Correct the service with the appropriate message type and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="51669-121">否则，请联系服务提供商。</span><span class="sxs-lookup"><span data-stu-id="51669-121">Otherwise, contact the serviced provider.</span></span>  <span data-ttu-id="51669-122">有关消息的其他信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="51669-122">For additional information on messages, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Help:</span></span>  
  
-   [<span data-ttu-id="51669-123">构造 Web 消息</span><span class="sxs-lookup"><span data-stu-id="51669-123">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)