---
title: 消息部分缺少元素 |Microsoft 文档
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
ms.openlocfilehash: 1dd5a423a34d8b6ddf8f4689351b0f6dbcef53c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263037"
---
# <a name="message-part-missing-element"></a><span data-ttu-id="38131-102">消息部分缺少元素</span><span class="sxs-lookup"><span data-stu-id="38131-102">Message part missing element</span></span>
## <a name="details"></a><span data-ttu-id="38131-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="38131-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="38131-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="38131-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="38131-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="38131-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="38131-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="38131-106">Event ID</span></span>|<span data-ttu-id="38131-107">0</span><span class="sxs-lookup"><span data-stu-id="38131-107">0</span></span>|  
|<span data-ttu-id="38131-108">事件源</span><span class="sxs-lookup"><span data-stu-id="38131-108">Event Source</span></span>|<span data-ttu-id="38131-109">0</span><span class="sxs-lookup"><span data-stu-id="38131-109">0</span></span>|  
|<span data-ttu-id="38131-110">组件</span><span class="sxs-lookup"><span data-stu-id="38131-110">Component</span></span>|<span data-ttu-id="38131-111">0</span><span class="sxs-lookup"><span data-stu-id="38131-111">0</span></span>|  
|<span data-ttu-id="38131-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="38131-112">Symbolic Name</span></span>|<span data-ttu-id="38131-113">0</span><span class="sxs-lookup"><span data-stu-id="38131-113">0</span></span>|  
|<span data-ttu-id="38131-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="38131-114">Message Text</span></span>|<span data-ttu-id="38131-115">消息部分丢失元素。</span><span class="sxs-lookup"><span data-stu-id="38131-115">Message part missing element.</span></span> <span data-ttu-id="38131-116">更正服务说明"{0}"消息类型"{1}"部分"{2}"，然后重新运行该向导</span><span class="sxs-lookup"><span data-stu-id="38131-116">Correct service description "{0}" message type "{1}" part "{2}" and rerun the wizard</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="38131-117">解释</span><span class="sxs-lookup"><span data-stu-id="38131-117">Explanation</span></span>  
 <span data-ttu-id="38131-118">此错误表示尝试使用的服务不具有标识消息类型的元素标签。</span><span class="sxs-lookup"><span data-stu-id="38131-118">This error indicates the service that is trying to be consumed does not have the element tag identifying the type of message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="38131-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="38131-119">User Action</span></span>  
 <span data-ttu-id="38131-120">将服务更正为具有正确的消息类型，然后尝试使用此服务（如果您拥有要尝试使用的 WCF 服务）。</span><span class="sxs-lookup"><span data-stu-id="38131-120">Correct the service with the appropriate message type and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="38131-121">否则，请与服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="38131-121">Otherwise, contact the service provider.</span></span>  
  
 <span data-ttu-id="38131-122">有关消息的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="38131-122">For additional information on messages, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="38131-123">构造 Web 消息</span><span class="sxs-lookup"><span data-stu-id="38131-123">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)