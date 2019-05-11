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
ms.openlocfilehash: c2dfa36a5814b270da64eb95dc8e082a91674003
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325019"
---
# <a name="message-part-missing-element"></a><span data-ttu-id="ce105-102">消息部分缺少元素</span><span class="sxs-lookup"><span data-stu-id="ce105-102">Message part missing element</span></span>
## <a name="details"></a><span data-ttu-id="ce105-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ce105-103">Details</span></span>  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ce105-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ce105-104">Product Name</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| <span data-ttu-id="ce105-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ce105-105">Product Version</span></span> |                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                             |
|    <span data-ttu-id="ce105-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ce105-106">Event ID</span></span>     |                                                         <span data-ttu-id="ce105-107">0</span><span class="sxs-lookup"><span data-stu-id="ce105-107">0</span></span>                                                          |
|  <span data-ttu-id="ce105-108">事件源</span><span class="sxs-lookup"><span data-stu-id="ce105-108">Event Source</span></span>   |                                                         <span data-ttu-id="ce105-109">0</span><span class="sxs-lookup"><span data-stu-id="ce105-109">0</span></span>                                                          |
|    <span data-ttu-id="ce105-110">组件</span><span class="sxs-lookup"><span data-stu-id="ce105-110">Component</span></span>    |                                                         <span data-ttu-id="ce105-111">0</span><span class="sxs-lookup"><span data-stu-id="ce105-111">0</span></span>                                                          |
|  <span data-ttu-id="ce105-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="ce105-112">Symbolic Name</span></span>  |                                                         <span data-ttu-id="ce105-113">0</span><span class="sxs-lookup"><span data-stu-id="ce105-113">0</span></span>                                                          |
|  <span data-ttu-id="ce105-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="ce105-114">Message Text</span></span>   | <span data-ttu-id="ce105-115">消息部分缺少元素。</span><span class="sxs-lookup"><span data-stu-id="ce105-115">Message part missing element.</span></span> <span data-ttu-id="ce105-116">更正服务说明"{0}"消息类型"{1}"部分"{2}"，然后重新运行向导</span><span class="sxs-lookup"><span data-stu-id="ce105-116">Correct service description "{0}" message type "{1}" part "{2}" and rerun the wizard</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ce105-117">解释</span><span class="sxs-lookup"><span data-stu-id="ce105-117">Explanation</span></span>  
 <span data-ttu-id="ce105-118">此错误表示尝试使用该服务不具有标识消息类型的元素标记。</span><span class="sxs-lookup"><span data-stu-id="ce105-118">This error indicates the service that is trying to be consumed does not have the element tag identifying the type of message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ce105-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="ce105-119">User Action</span></span>  
 <span data-ttu-id="ce105-120">更正服务与相应的消息类型，然后尝试使用 （如果您拥有要尝试使用的 WCF 服务）。</span><span class="sxs-lookup"><span data-stu-id="ce105-120">Correct the service with the appropriate message type and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="ce105-121">否则，请与服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="ce105-121">Otherwise, contact the service provider.</span></span>  
  
 <span data-ttu-id="ce105-122">有关消息的其他信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="ce105-122">For additional information on messages, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="ce105-123">构造 Web 消息</span><span class="sxs-lookup"><span data-stu-id="ce105-123">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)