---
title: "配置错误。 上一种方法的 HTTP 请求的同步 MDN 发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bd38eb3-321f-4738-b35e-390f4f54673e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a0a240593aa21b102c401a2a6886ea24baa42c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-error-synchronous-mdn-requested-on-one-way-http-send-port"></a><span data-ttu-id="a8542-103">配置错误。</span><span class="sxs-lookup"><span data-stu-id="a8542-103">Configuration error.</span></span> <span data-ttu-id="a8542-104">在单向 HTTP 发送端口上请求了同步 MDN</span><span class="sxs-lookup"><span data-stu-id="a8542-104">Synchronous MDN requested on one way HTTP send port</span></span>
## <a name="details"></a><span data-ttu-id="a8542-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="a8542-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a8542-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="a8542-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a8542-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="a8542-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="a8542-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a8542-108">Event ID</span></span>|-|  
|<span data-ttu-id="a8542-109">事件源</span><span class="sxs-lookup"><span data-stu-id="a8542-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a8542-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="a8542-110"> EDI</span></span>|  
|<span data-ttu-id="a8542-111">组件</span><span class="sxs-lookup"><span data-stu-id="a8542-111">Component</span></span>|<span data-ttu-id="a8542-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="a8542-112">EDI Engine</span></span>|  
|<span data-ttu-id="a8542-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="a8542-113">Symbolic Name</span></span>|-|  
|<span data-ttu-id="a8542-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="a8542-114">Message Text</span></span>|<span data-ttu-id="a8542-115">配置错误。</span><span class="sxs-lookup"><span data-stu-id="a8542-115">Configuration error.</span></span> <span data-ttu-id="a8542-116">在单向 HTTP 发送端口上请求了同步 MDN。</span><span class="sxs-lookup"><span data-stu-id="a8542-116">Synchronous MDN requested on one way HTTP send port.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a8542-117">解释</span><span class="sxs-lookup"><span data-stu-id="a8542-117">Explanation</span></span>  
 <span data-ttu-id="a8542-118">此错误/警告/信息事件表明在发送 AS2 消息后 BizTalk Server 无法接收同步 MDN，因为发送 AS2 消息的 HTTP 发送端口是单向端口。</span><span class="sxs-lookup"><span data-stu-id="a8542-118">This Error/Warning/Information event indicates that BizTalk Server could not receive a synchronous MDN after sending an AS2 message because the HTTP send port that sent the AS2 message was a one-way port.</span></span> <span data-ttu-id="a8542-119">处理为了响应端口发送的 AS2 消息而返回的同步 MDN，需要双向要求-响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="a8542-119">A two-way solicit-response send port is required to process a synchronous MDN returned in response to an AS2 message sent by the port.</span></span> <span data-ttu-id="a8542-120">这种情况下，必须同步返回 MDN，因为在 AS2 消息接收方的参与方的配置中，选中了“请求 MDN”属性，但清除了“请求异步 MDN”属性。</span><span class="sxs-lookup"><span data-stu-id="a8542-120">In this case, the MDN must be returned synchronously because in the configuration for the party as an AS2 Message Receiver, the Request MDN property is checked, and the Request asynchronous MDN property is cleared.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a8542-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="a8542-121">User Action</span></span>  
 <span data-ttu-id="a8542-122">若要解决此错误，请将发送 AS2 消息的发送端口更改为静态要求-响应发送端口，而不是单向发送端口。</span><span class="sxs-lookup"><span data-stu-id="a8542-122">To resolve this error, change the send port that is sending the AS2 message to be a static solicit-response send port, rather than a one-way send port.</span></span> <span data-ttu-id="a8542-123">将要求-响应发送端口的接收管道设置为 AS2EdiReceive（针对 EDI 交换）或 AS2Receive（针对非 EDI 交换）。</span><span class="sxs-lookup"><span data-stu-id="a8542-123">Set the receive pipeline of the solicit-response send port to be AS2EdiReceive for an EDI interchange or AS2Receive for a non-EDI interchange.</span></span>