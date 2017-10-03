---
title: "处理在发送端口上的 Edifact 消息时出现故障： 接收方和发件人标识符限定符对没有协议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cffc4705-164f-4779-8f04-c6a2a7f1bbda
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4cb2b0637c54f6fdd13dc5f0d17d71817ce4453
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs"></a><span data-ttu-id="5f2fc-102">处理在发送端口上的 Edifact 消息时出现故障： 接收方和发件人标识符限定符对没有协议</span><span class="sxs-lookup"><span data-stu-id="5f2fc-102">A failure occurred in processing Edifact message on send port: No agreement for receiver and sender identifier-qualifier pairs</span></span>
## <a name="details"></a><span data-ttu-id="5f2fc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5f2fc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5f2fc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5f2fc-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5f2fc-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="5f2fc-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="5f2fc-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5f2fc-106">Event ID</span></span>|-|  
|<span data-ttu-id="5f2fc-107">事件源</span><span class="sxs-lookup"><span data-stu-id="5f2fc-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5f2fc-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="5f2fc-108"> EDI</span></span>|  
|<span data-ttu-id="5f2fc-109">组件</span><span class="sxs-lookup"><span data-stu-id="5f2fc-109">Component</span></span>|<span data-ttu-id="5f2fc-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="5f2fc-110">EDI Engine</span></span>|  
|<span data-ttu-id="5f2fc-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="5f2fc-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="5f2fc-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="5f2fc-112">Message Text</span></span>|<span data-ttu-id="5f2fc-113">在发送端口 {0} 上处理 Edifact 消息时发生故障。</span><span class="sxs-lookup"><span data-stu-id="5f2fc-113">A failure occurred in processing Edifact message on send port {0}.</span></span> <span data-ttu-id="5f2fc-114">没有协议的接收方和发件人标识符/限定符对 {1}、 {2}、 {3}、 \ {4 \ 存在。</span><span class="sxs-lookup"><span data-stu-id="5f2fc-114">No agreement exists for receiver and sender identifier/qualifier pairs for {1}, {2}, {3}, {4}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5f2fc-115">解释</span><span class="sxs-lookup"><span data-stu-id="5f2fc-115">Explanation</span></span>  
 <span data-ttu-id="5f2fc-116">此错误/警告/信息事件表明 BizTalk Server 无法解析 EDIFACT 交换的参与方，因为 BizTalk Server 无法通过某一方的相应值来匹配升级后的发送方限定符和标识符属性、升级后的接收方限定符和标识符属性。</span><span class="sxs-lookup"><span data-stu-id="5f2fc-116">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the EDIFACT interchange because it was unable to match promoted sender qualifier and identifier properties, and promoted receiver qualifier and identifier properties, with the corresponding values for a party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5f2fc-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="5f2fc-117">User Action</span></span>  
 <span data-ttu-id="5f2fc-118">若要解决此错误，请确保参与方的“EDI 属性”对话框的“UNB 段定义”页中定义的发送方限定符和标识符（UNB2.1 和 UNB2.2）以及接收方限定符和标识符（UNB3.1 和 UNB3.2）与交换的上下文中相对应的升级后的属性匹配。</span><span class="sxs-lookup"><span data-stu-id="5f2fc-118">To resolve this error, ensure that the sender qualifier and identifier (UNB2.1 and UNB2.2) and receiver qualifier and identifier (UNB3.1 and UNB3.2) defined in the party's UNB Segment Definition page of the EDI Properties dialog box match the corresponding promoted properties in the context of the interchange.</span></span>