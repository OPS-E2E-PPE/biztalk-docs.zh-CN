---
title: 配置错误。 在单向 HTTP 上请求了同步 MDN 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bd38eb3-321f-4738-b35e-390f4f54673e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1e52f0d7107a09357af0b6ab35db15ad0a8514c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391529"
---
# <a name="configuration-error-synchronous-mdn-requested-on-one-way-http-send-port"></a><span data-ttu-id="c9fb2-103">配置错误。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-103">Configuration error.</span></span> <span data-ttu-id="c9fb2-104">在单向 HTTP 上请求了同步 MDN 发送端口</span><span class="sxs-lookup"><span data-stu-id="c9fb2-104">Synchronous MDN requested on one way HTTP send port</span></span>
## <a name="details"></a><span data-ttu-id="c9fb2-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="c9fb2-105">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c9fb2-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="c9fb2-106">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c9fb2-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="c9fb2-107">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c9fb2-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c9fb2-108">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c9fb2-109">事件源</span><span class="sxs-lookup"><span data-stu-id="c9fb2-109">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c9fb2-110">EDI</span><span class="sxs-lookup"><span data-stu-id="c9fb2-110">EDI</span></span> |
|    <span data-ttu-id="c9fb2-111">组件</span><span class="sxs-lookup"><span data-stu-id="c9fb2-111">Component</span></span>    |                                       <span data-ttu-id="c9fb2-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="c9fb2-112">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c9fb2-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="c9fb2-113">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="c9fb2-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="c9fb2-114">Message Text</span></span>   |       <span data-ttu-id="c9fb2-115">配置错误。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-115">Configuration error.</span></span> <span data-ttu-id="c9fb2-116">在单向 HTTP 发送端口上请求了同步 MDN。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-116">Synchronous MDN requested on one way HTTP send port.</span></span>        |
  
## <a name="explanation"></a><span data-ttu-id="c9fb2-117">解释</span><span class="sxs-lookup"><span data-stu-id="c9fb2-117">Explanation</span></span>  
 <span data-ttu-id="c9fb2-118">此错误/警告/信息事件表明在发送 AS2 消息后 BizTalk Server 无法接收同步 MDN，因为发送 AS2 消息的 HTTP 发送端口是单向端口。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-118">This Error/Warning/Information event indicates that BizTalk Server could not receive a synchronous MDN after sending an AS2 message because the HTTP send port that sent the AS2 message was a one-way port.</span></span> <span data-ttu-id="c9fb2-119">处理为了响应端口发送的 AS2 消息而返回的同步 MDN，需要双向要求-响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-119">A two-way solicit-response send port is required to process a synchronous MDN returned in response to an AS2 message sent by the port.</span></span> <span data-ttu-id="c9fb2-120">这种情况下，必须同步返回 MDN，因为在 AS2 消息接收方的参与方的配置中，选中了“请求 MDN”属性，但清除了“请求异步 MDN”属性。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-120">In this case, the MDN must be returned synchronously because in the configuration for the party as an AS2 Message Receiver, the Request MDN property is checked, and the Request asynchronous MDN property is cleared.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c9fb2-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="c9fb2-121">User Action</span></span>  
 <span data-ttu-id="c9fb2-122">若要解决此错误，请将发送 AS2 消息的发送端口更改为静态要求-响应发送端口，而不是单向发送端口。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-122">To resolve this error, change the send port that is sending the AS2 message to be a static solicit-response send port, rather than a one-way send port.</span></span> <span data-ttu-id="c9fb2-123">将要求-响应发送端口的接收管道设置为 AS2EdiReceive（针对 EDI 交换）或 AS2Receive（针对非 EDI 交换）。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-123">Set the receive pipeline of the solicit-response send port to be AS2EdiReceive for an EDI interchange or AS2Receive for a non-EDI interchange.</span></span>