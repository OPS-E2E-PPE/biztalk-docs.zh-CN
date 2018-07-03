---
title: 在发送端口上处理 Edifact 消息时发生故障： 不存在用于收件人和发件人标识符限定符对和不带名称的参与方协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11880c7c-6032-449b-b251-27fc2b2f0d72
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0b4e66ce918f59502125e77b7c19615cb281660
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009910"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs-and-no-party-with-name"></a><span data-ttu-id="5762f-102">在发送端口上处理 Edifact 消息时发生故障： 不存在用于收件人和发件人标识符限定符对和不带名称的参与方协议</span><span class="sxs-lookup"><span data-stu-id="5762f-102">A failure occurred in processing Edifact message on send port: No agreement for receiver and sender identifier-qualifier pairs and no party with name</span></span>
## <a name="details"></a><span data-ttu-id="5762f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5762f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5762f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5762f-104">Product Name</span></span>   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                        |
| <span data-ttu-id="5762f-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="5762f-105">Product Version</span></span> |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                    |
|    <span data-ttu-id="5762f-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5762f-106">Event ID</span></span>     |                                                                                                -                                                                                                 |
|  <span data-ttu-id="5762f-107">事件源</span><span class="sxs-lookup"><span data-stu-id="5762f-107">Event Source</span></span>   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5762f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="5762f-108"> EDI</span></span>                                                      |
|    <span data-ttu-id="5762f-109">组件</span><span class="sxs-lookup"><span data-stu-id="5762f-109">Component</span></span>    |                                                                                            <span data-ttu-id="5762f-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="5762f-110">EDI Engine</span></span>                                                                                            |
|  <span data-ttu-id="5762f-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="5762f-111">Symbolic Name</span></span>  |                                                                                                -                                                                                                 |
|  <span data-ttu-id="5762f-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="5762f-112">Message Text</span></span>   | <span data-ttu-id="5762f-113">在发送端口上处理 Edifact 消息时发生故障{0}。</span><span class="sxs-lookup"><span data-stu-id="5762f-113">A failure occurred in processing Edifact message on send port {0}.</span></span> <span data-ttu-id="5762f-114">不存在 {1}、{2}、{3}、{4} 的接收方和发送方标识符/限定符对的协议。</span><span class="sxs-lookup"><span data-stu-id="5762f-114">No agreement exists for receiver and sender identifier/qualifier pairs for {1}, {2}, {3}, {4}.</span></span> <span data-ttu-id="5762f-115">不存在名称为 {5} 的参与方。</span><span class="sxs-lookup"><span data-stu-id="5762f-115">No Party exists with name {5}.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="5762f-116">解释</span><span class="sxs-lookup"><span data-stu-id="5762f-116">Explanation</span></span>  
 <span data-ttu-id="5762f-117">此错误/警告/信息事件表明 BizTalk Server 无法解析 EDIFACT 交换的参与方，因为 BizTalk Server 无法通过某一方的相应值来匹配升级后的发送方限定符和标识符属性、升级后的接收方限定符和标识符属性。</span><span class="sxs-lookup"><span data-stu-id="5762f-117">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the EDIFACT interchange because it was unable to match promoted sender qualifier and identifier properties, and promoted receiver qualifier and identifier properties, with the corresponding values for a party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5762f-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="5762f-118">User Action</span></span>  
 <span data-ttu-id="5762f-119">若要解决此错误，请确保参与方的“EDI 属性”对话框的“UNB 段定义”页中定义的发送方限定符和标识符（UNB2.1 和 UNB2.2）以及接收方限定符和标识符（UNB3.1 和 UNB3.2）与交换的上下文中相对应的升级后的属性匹配。</span><span class="sxs-lookup"><span data-stu-id="5762f-119">To resolve this error, ensure that the sender qualifier and identifier (UNB2.1 and UNB2.2) and receiver qualifier and identifier (UNB3.1 and UNB3.2) defined in the party's UNB Segment Definition page of the EDI Properties dialog box match the corresponding promoted properties in the context of the interchange.</span></span>