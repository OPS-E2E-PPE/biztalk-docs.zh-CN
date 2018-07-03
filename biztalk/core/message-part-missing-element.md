---
title: 消息部分缺少元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b519315f-d51d-4ca3-a0e6-d08bb920c6c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 412b25d2f7ea027de53818b032b50562faab9865
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009438"
---
# <a name="message-part-missing-element"></a><span data-ttu-id="08940-102">消息部分缺少元素</span><span class="sxs-lookup"><span data-stu-id="08940-102">Message part missing element</span></span>
## <a name="details"></a><span data-ttu-id="08940-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="08940-103">Details</span></span>  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="08940-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="08940-104">Product Name</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| <span data-ttu-id="08940-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="08940-105">Product Version</span></span> |                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                             |
|    <span data-ttu-id="08940-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="08940-106">Event ID</span></span>     |                                                         <span data-ttu-id="08940-107">0</span><span class="sxs-lookup"><span data-stu-id="08940-107">0</span></span>                                                          |
|  <span data-ttu-id="08940-108">事件源</span><span class="sxs-lookup"><span data-stu-id="08940-108">Event Source</span></span>   |                                                         <span data-ttu-id="08940-109">0</span><span class="sxs-lookup"><span data-stu-id="08940-109">0</span></span>                                                          |
|    <span data-ttu-id="08940-110">组件</span><span class="sxs-lookup"><span data-stu-id="08940-110">Component</span></span>    |                                                         <span data-ttu-id="08940-111">0</span><span class="sxs-lookup"><span data-stu-id="08940-111">0</span></span>                                                          |
|  <span data-ttu-id="08940-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="08940-112">Symbolic Name</span></span>  |                                                         <span data-ttu-id="08940-113">0</span><span class="sxs-lookup"><span data-stu-id="08940-113">0</span></span>                                                          |
|  <span data-ttu-id="08940-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="08940-114">Message Text</span></span>   | <span data-ttu-id="08940-115">消息部分丢失元素。</span><span class="sxs-lookup"><span data-stu-id="08940-115">Message part missing element.</span></span> <span data-ttu-id="08940-116">更正服务说明"{0}"消息类型"{1}"部分"{2}"，然后重新运行向导</span><span class="sxs-lookup"><span data-stu-id="08940-116">Correct service description "{0}" message type "{1}" part "{2}" and rerun the wizard</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="08940-117">解释</span><span class="sxs-lookup"><span data-stu-id="08940-117">Explanation</span></span>  
 <span data-ttu-id="08940-118">此错误表示尝试使用的服务不具有标识消息类型的元素标签。</span><span class="sxs-lookup"><span data-stu-id="08940-118">This error indicates the service that is trying to be consumed does not have the element tag identifying the type of message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="08940-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="08940-119">User Action</span></span>  
 <span data-ttu-id="08940-120">将服务更正为具有正确的消息类型，然后尝试使用此服务（如果您拥有要尝试使用的 WCF 服务）。</span><span class="sxs-lookup"><span data-stu-id="08940-120">Correct the service with the appropriate message type and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="08940-121">否则，请与服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="08940-121">Otherwise, contact the service provider.</span></span>  
  
 <span data-ttu-id="08940-122">有关消息的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="08940-122">For additional information on messages, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="08940-123">构造 Web 消息</span><span class="sxs-lookup"><span data-stu-id="08940-123">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)