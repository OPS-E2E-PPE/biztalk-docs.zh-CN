---
title: 配置错误。 上一种方法的 HTTP 请求的同步 MDN 接收端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f140c7a4-46bf-4557-9679-cdaf2fbe66f4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa49120ecbdbd0a00de1bbd6cd552f56cb626ddd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232197"
---
# <a name="configuration-error-synchronous-mdn-requested-on-a-one-way-http-receive-port"></a><span data-ttu-id="d8fde-103">配置错误。</span><span class="sxs-lookup"><span data-stu-id="d8fde-103">Configuration error.</span></span> <span data-ttu-id="d8fde-104">在单向 HTTP 接收端口上请求了同步 MDN</span><span class="sxs-lookup"><span data-stu-id="d8fde-104">Synchronous MDN requested on a one way HTTP receive Port</span></span>
## <a name="details"></a><span data-ttu-id="d8fde-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="d8fde-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8fde-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="d8fde-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d8fde-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="d8fde-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d8fde-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d8fde-108">Event ID</span></span>|-|  
|<span data-ttu-id="d8fde-109">事件源</span><span class="sxs-lookup"><span data-stu-id="d8fde-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d8fde-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="d8fde-110"> EDI</span></span>|  
|<span data-ttu-id="d8fde-111">组件</span><span class="sxs-lookup"><span data-stu-id="d8fde-111">Component</span></span>|<span data-ttu-id="d8fde-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="d8fde-112">EDI Engine</span></span>|  
|<span data-ttu-id="d8fde-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="d8fde-113">Symbolic Name</span></span>|-|  
|<span data-ttu-id="d8fde-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="d8fde-114">Message Text</span></span>|<span data-ttu-id="d8fde-115">配置错误。</span><span class="sxs-lookup"><span data-stu-id="d8fde-115">Configuration error.</span></span> <span data-ttu-id="d8fde-116">在单向 HTTP 发送端口上请求了同步 MDN。</span><span class="sxs-lookup"><span data-stu-id="d8fde-116">Synchronous MDN requested on one way HTTP send port.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d8fde-117">解释</span><span class="sxs-lookup"><span data-stu-id="d8fde-117">Explanation</span></span>  
 <span data-ttu-id="d8fde-118">此错误/警告/信息事件表明在接收 AS2 消息后 BizTalk Server 无法返回同步 MDN，因为处理传入的 AS2 消息的 HTTP 接收端口是单向端口。</span><span class="sxs-lookup"><span data-stu-id="d8fde-118">This Error/Warning/Information event indicates that BizTalk Server could not return a synchronous MDN after receiving an AS2 message because the HTTP receive port that processed the incoming AS2 message was a one-way port.</span></span> <span data-ttu-id="d8fde-119">双向请求-响应接收端口需要响应传入 AS2 消息中返回同步的 MDN。</span><span class="sxs-lookup"><span data-stu-id="d8fde-119">A two-way request-response receive port is required to return a synchronous MDN in response to an incoming AS2 message.</span></span> <span data-ttu-id="d8fde-120">在这种情况下，必须同步返回 MDN，因为 AS2 消息包含 Disposition-Notification-To 标头，或者在作为 AS2 消息发送方的参与方的配置中，选中了属性“替代入站消息属性”，选中了“生成 MDN”属性，并且清除了“异步传输 MDN”属性。</span><span class="sxs-lookup"><span data-stu-id="d8fde-120">In this case, the MDN must be returned synchronously because the AS2 message includes the Disposition-Notification-To header, or in the configuration for the party as an AS2 Message Sender, the Override inbound message properties property is checked, the Generate MDN property is checked, and the Transmit MDN asynchronously property is cleared.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d8fde-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="d8fde-121">User Action</span></span>  
 <span data-ttu-id="d8fde-122">若要解决此错误，请将接收 AS2 消息的接收端口改为请求响应接收端口，而不是单向接收端口。</span><span class="sxs-lookup"><span data-stu-id="d8fde-122">To resolve this error, change the receive port that is receiving the AS2 message to be a request response receive port, rather than a one-way receive port.</span></span> <span data-ttu-id="d8fde-123">将请求响应接收位置的发送管道设置为 AS2EdiSend（对于 EDI 交换）或 AS2Send（对于非 EDI 交换）。</span><span class="sxs-lookup"><span data-stu-id="d8fde-123">Set the send pipeline of the request response receive location to be AS2EdiSend for an EDI interchange or AS2Send for a non-EDI interchange.</span></span>