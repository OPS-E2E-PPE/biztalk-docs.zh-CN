---
title: 交换包含格式不正确的 ISA 或服务架构不可用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78d285f6-26fb-4a3b-a959-a17623321b20
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cce469b25a2ba15c3038ea9079c3f22fc4f8c0c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010710"
---
# <a name="the-interchange-contained-a-malformed-isa-or-the-service-schema-was-not-available"></a><span data-ttu-id="5508d-102">交换包含格式不正确的 ISA 或服务架构不可用</span><span class="sxs-lookup"><span data-stu-id="5508d-102">The interchange contained a malformed ISA or the Service schema was not available</span></span>
## <a name="details"></a><span data-ttu-id="5508d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5508d-103">Details</span></span>  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5508d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5508d-104">Product Name</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| <span data-ttu-id="5508d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="5508d-105">Product Version</span></span> |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                             |
|    <span data-ttu-id="5508d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5508d-106">Event ID</span></span>     |                                                         -                                                          |
|  <span data-ttu-id="5508d-107">事件源</span><span class="sxs-lookup"><span data-stu-id="5508d-107">Event Source</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5508d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="5508d-108"> EDI</span></span>               |
|    <span data-ttu-id="5508d-109">组件</span><span class="sxs-lookup"><span data-stu-id="5508d-109">Component</span></span>    |                                                     <span data-ttu-id="5508d-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="5508d-110">EDI Engine</span></span>                                                     |
|  <span data-ttu-id="5508d-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="5508d-111">Symbolic Name</span></span>  |                                                 <span data-ttu-id="5508d-112">MalformedIsaError</span><span class="sxs-lookup"><span data-stu-id="5508d-112">MalformedIsaError</span></span>                                                  |
|  <span data-ttu-id="5508d-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="5508d-113">Message Text</span></span>   | <span data-ttu-id="5508d-114">交换包含格式不正确的 ISA 或服务架构不可用，因此它被完全拒绝</span><span class="sxs-lookup"><span data-stu-id="5508d-114">The interchange contained a malformed ISA or the Service schema was not available, it is being rejected completely</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="5508d-115">解释</span><span class="sxs-lookup"><span data-stu-id="5508d-115">Explanation</span></span>  
 <span data-ttu-id="5508d-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中的 ISA 或 IEA 段不符合 X12ServiceSchema，或者未部署 X12ServiceSchema（在 BaseArtifacts.dll 中）。</span><span class="sxs-lookup"><span data-stu-id="5508d-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange, because the ISA or IEA segments in the interchange did not conform to the X12ServiceSchema, or the X12ServiceSchema (in BaseArtifacts.dll) was not deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5508d-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="5508d-117">User Action</span></span>  
 <span data-ttu-id="5508d-118">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="5508d-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="5508d-119">让交换的发送方更改 ISA 和 IEA 段，以便这些段符合 X12ServiceSchema。</span><span class="sxs-lookup"><span data-stu-id="5508d-119">Have the sender of the interchange change the ISA and IEA segments so that they conform to the X12ServiceSchema.</span></span>  
  
-   <span data-ttu-id="5508d-120">确保 BaseArtifacts.dll 包含 X12ServiceSchema 并且已部署。</span><span class="sxs-lookup"><span data-stu-id="5508d-120">Ensure that BaseArtifacts.dll includes the X12ServiceSchema and is deployed.</span></span> <span data-ttu-id="5508d-121">可以通过打开 BizTalk Server 管理控制台，打开“BizTalk EDI 应用程序”节点，然后“架构”节点并验证是否列出了 X12ServiceSchema 来执行该操作。</span><span class="sxs-lookup"><span data-stu-id="5508d-121">You can do so by opening the BizTalk Server Administration Console, opening the BizTalk EDI Application node and then the Schemas node, and verifying that X12ServiceSchema is listed.</span></span>