---
title: 出现故障。 处理 X12 发送端口上的消息： 接收方和发件人标识符限定符对没有协议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72ae7926-f5c1-42f4-8c29-11f34c138dd4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 637cd174b2c9723f4391417392700e3a4f079b79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240853"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs"></a><span data-ttu-id="ad7eb-102">出现故障。 处理 X12 发送端口上的消息： 接收方和发件人标识符限定符对没有协议</span><span class="sxs-lookup"><span data-stu-id="ad7eb-102">A failure occurred in processing X12 message on send port: No agreement for receiver and sender identifier-qualifier pairs</span></span>
## <a name="details"></a><span data-ttu-id="ad7eb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ad7eb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ad7eb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ad7eb-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ad7eb-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ad7eb-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ad7eb-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ad7eb-106">Event ID</span></span>|-|  
|<span data-ttu-id="ad7eb-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ad7eb-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ad7eb-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ad7eb-108"> EDI</span></span>|  
|<span data-ttu-id="ad7eb-109">组件</span><span class="sxs-lookup"><span data-stu-id="ad7eb-109">Component</span></span>|<span data-ttu-id="ad7eb-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ad7eb-110">EDI Engine</span></span>|  
|<span data-ttu-id="ad7eb-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ad7eb-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="ad7eb-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="ad7eb-112">Message Text</span></span>|<span data-ttu-id="ad7eb-113">在发送端口 {0} 上处理 X12 消息时发生故障。</span><span class="sxs-lookup"><span data-stu-id="ad7eb-113">A failure occurred in processing X12 message on send port {0}.</span></span> <span data-ttu-id="ad7eb-114">没有协议的接收方和发件人标识符/限定符对 {1}、 {2}、 {3}、 \ {4 \ 存在。</span><span class="sxs-lookup"><span data-stu-id="ad7eb-114">No agreement exists for receiver and sender identifier/qualifier pairs for {1}, {2}, {3}, {4}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ad7eb-115">解释</span><span class="sxs-lookup"><span data-stu-id="ad7eb-115">Explanation</span></span>  
 <span data-ttu-id="ad7eb-116">此错误/警告/信息事件表示 BizTalk Server 无法解决当事方 EDIFACT 交换因为 BizTalk Server 无法匹配提升发件人限定符和标识符属性，并且提升收件人限定符和标识符属性，使用方的相应值。</span><span class="sxs-lookup"><span data-stu-id="ad7eb-116">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the EDIFACT interchange because BizTalk Server was unable to match promoted sender qualifier and identifier properties, and promoted receiver qualifier and identifier properties, with the corresponding values for a party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ad7eb-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="ad7eb-117">User Action</span></span>  
 <span data-ttu-id="ad7eb-118">若要解决此错误，请确保参与方的“EDI 属性”对话框的“ISA 段定义”页中定义的发送方限定符和标识符（ISA5 和 ISA6）以及接收方限定符和标识符（ISA7 和 ISA8）与交换的上下文中相对应的升级后的属性匹配。</span><span class="sxs-lookup"><span data-stu-id="ad7eb-118">To resolve this error, ensure that the sender qualifier and identifier (ISA5 and ISA6) and receiver qualifier and identifier (ISA7 and ISA8) defined in the party's ISA Segment Definition page of the EDI Properties dialog box match the corresponding promoted properties in the context of the interchange.</span></span>